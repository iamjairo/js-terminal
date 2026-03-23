**JS - Terminal** — a web-based terminal for Synology NAS, powered by [ttyd](https://github.com/tsl0922/ttyd) and rendered with xterm.js (WebGL).

Opens directly as an app window inside DSM, or via browser at `http(s)://<ip>:<port>/terminal/`

## Installation

1. Download the `.spk` from [Releases](../../releases)
2. In DSM go to **Package Center > Manual Install** and select the `.spk`
3. The install will fail to start — this is expected. SSH into your NAS and run:
   ```sh
   sudo sed 's/package/root/g' -i /var/packages/terminal/conf/privilege
   sudo synopkg start terminal
   ```
4. Open **JS - Terminal** from the DSM desktop

## Configuration

Config file: `/var/packages/terminal/target/etc/terminal_ttyd.conf`

Restart after changes:
```sh
sudo synopkg restart terminal
```

## Tmux key bindings reference (C = Ctrl, M = Alt)

| Key | Action |
|-----|--------|
| C-b " | Split window vertically |
| C-b % | Split window horizontally |
| C-b c | New window |
| C-b d | Detach client |
| C-b n / p | Next / previous window |
| C-b x | Kill active pane |
| C-b z | Zoom active pane |
| C-b [ | Enter copy mode |
| C-b ? | List all key bindings |

## License

MIT

