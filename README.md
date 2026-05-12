# Transmission 3.x Integration

Custom Home Assistant integration for Transmission BitTorrent client version 3.x.

This integration supports Transmission 3.0.0 which is unsupported in official Transmission integration. For Transmission 4.x, better use the official integration included in Home Assistant.

## Features
Same as official integration.  
It's much better when use Transmission  integration with [Transmission-Card](https://github.com/amaximus/transmission-card)

## Installation - HACS

1. Add this repository as a custom repository in HACS:
   - Type: Integration
   - Repository: `headsoft-mikhail/ha-transmission3`

2. Click "Download" to install

3. Restart Home Assistant

4. Go to Settings > Devices & Services > Add Integration and select "Transmission 3.x"

## Configuration

When adding the integration, you will need:

- **Host**: IP address or hostname of your Transmission instance
- **Port**: Port number (default: 9091)
- **Path**: RPC path (default: `/transmission/rpc`)
- **SSL**: Enable if using HTTPS
- **Username**: (optional) For authentication
- **Password**: (optional) For authentication


## License

MIT License
