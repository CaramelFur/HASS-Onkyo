# Onkyo Integration for Home Assistant

This integration provides support for Onkyo AV receivers in Home Assistant.

## Features

- Control Onkyo receivers via EISCP protocol
- Support for multiple zones (Main, Zone 2, Zone 3, Zone 4)
- Volume control with configurable resolution and maximum volume limits
- Input source selection
- Listening mode selection
- HDMI output control
- Audio and video information display
- Automatic discovery via SSDP and EISCP

## Installation

### HACS (Recommended)

1. Install [HACS](https://hacs.xyz/) if you haven't already
2. Go to HACS → Integrations
3. Click the three dots menu → Custom repositories
4. Add this repository
5. Search for "Onkyo" and install
6. Restart Home Assistant
7. Go to Settings → Devices & Services → Add Integration
8. Search for "Onkyo" and follow the setup

### Manual Installation

1. Copy the `onkyo` folder to your `custom_components` directory
2. Restart Home Assistant
3. Go to Settings → Devices & Services → Add Integration
4. Search for "Onkyo" and follow the setup

## Configuration

The integration supports automatic discovery via SSDP. You can also manually configure by entering the IP address or hostname of your receiver.

During setup, you'll be asked to:
- Select input sources supported by your receiver
- Select listening modes supported by your receiver
- Configure volume resolution (50, 80, 100, or 200 steps)

## Options

After installation, you can configure additional options:
- **Maximum Volume Limit**: Set the maximum volume percentage (1-100%)
- **Input Sources**: Customize input source names
- **Listening Modes**: Customize listening mode names

## Supported Devices

This integration supports Onkyo and Pioneer receivers that use the EISCP protocol.

## Device Class

Media player entities are configured with `device_class: receiver` for proper categorization in Home Assistant.

## Services

### `media_player.onkyo_select_hdmi_output`

Select HDMI output for the receiver.

| Parameter | Description |
|-----------|-------------|
| `entity_id` | Entity ID of the Onkyo media player |
| `hdmi_output` | HDMI output to select (`analog`, `both`, `hdbaset`, `no`, `out`, `out-sub`, `sub`, `yes`) |

## Troubleshooting

If you experience connection issues:
1. Ensure your receiver is on the same network as Home Assistant
2. Check that port 60128 (EISCP) is not blocked by a firewall
3. Try manually entering the IP address instead of using discovery

## Requirements

- Home Assistant 2024.1.0 or later
- `aioonkyo` library (automatically installed)
