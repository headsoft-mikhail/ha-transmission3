# Transmission 3.x Integration

Custom Home Assistant integration for Transmission BitTorrent client version 3.x.

This integration supports Transmission 3.0.0 and later versions. For Transmission 4.x, use the official integration included in Home Assistant.

## Features

- Monitor download/upload speeds
- Track torrent status and counts
- Session and cumulative statistics
- Torrent info attributes
- Start/stop all torrents
- Turtle mode (alternative speed)
- Add torrents via URL, magnet link, or file
- Get filtered list of torrents
- Remove torrents with optional data deletion

## Installation

### HACS (Recommended)

1. Add this repository as a custom repository in HACS:
   - Type: Integration
   - Repository: `headsoft-mikhail/transmission3`

2. Click "Download" to install

3. Restart Home Assistant

4. Go to Settings > Devices & Services > Add Integration and select "Transmission 3.x"

### Manual Installation

1. Copy the `transmission3` folder to your Home Assistant `custom_components` directory:
   ```
   /config/custom_components/transmission3/
   ```

2. Restart Home Assistant

3. Go to Settings > Devices & Services > Add Integration and select "Transmission 3.x"

## Configuration

When adding the integration, you will need:

- **Host**: IP address or hostname of your Transmission instance
- **Port**: Port number (default: 9091)
- **Path**: RPC path (default: `/transmission/rpc`)
- **SSL**: Enable if using HTTPS
- **Username**: (optional) For authentication
- **Password**: (optional) For authentication

## Services

### add_torrent
Adds a new torrent to download.

| Field | Required | Description |
|-------|----------|-------------|
| entry_id | Yes | ID of the Transmission entry |
| torrent | Yes | URL, magnet link or Base64 encoded file |
| download_path | No | Optional path for download directory |
| labels | No | Comma-separated list of labels |

### get_torrents
Gets a list of current torrents.

| Field | Required | Description |
|-------|----------|-------------|
| entry_id | Yes | ID of the Transmission entry |
| torrent_filter | Yes | Filter: all, active, started, paused, completed |

### remove_torrent
Removes a torrent.

| Field | Required | Description |
|-------|----------|-------------|
| entry_id | Yes | ID of the Transmission entry |
| id | Yes | ID of the torrent |
| delete_data | No | Delete torrent data (default: false) |

### start_torrent
Starts a torrent.

| Field | Required | Description |
|-------|----------|-------------|
| entry_id | Yes | ID of the Transmission entry |
| id | Yes | ID of the torrent |

### stop_torrent
Stops a torrent.

| Field | Required | Description |
|-------|----------|-------------|
| entry_id | Yes | ID of the Transmission entry |
| id | Yes | ID of the torrent |

## Troubleshooting

If you cannot connect to Transmission:

1. Verify Transmission is running and accessible
2. Check the host, port, and path settings
3. Verify username/password if authentication is enabled
4. For self-signed certificates, disable SSL verification

## Version Compatibility

| Transmission | Integration Version |
|--------------|---------------------|
| 3.0.0+ | This integration (transmission3) |
| 4.0.0+ | Official Home Assistant integration |

## License

MIT License
