# Timezone Display Plugin for xbar

A comprehensive timezone display plugin for [xbar](https://xbarapp.com/) that shows current time across multiple timezones with full Daylight Saving Time (DST) support.

## Features

- 🌍 **Multi-timezone Display**: Shows time for 16 major cities/timezones worldwide
- 🔄 **Dynamic Primary Timezone**: Click any timezone to set it as your menu bar display
- ⏰ **DST Support**: Automatic DST calculation for North America, Europe, Australia, and New Zealand
- 📅 **Date Display**: Shows both time and date for each timezone
- 🎨 **Clean Interface**: Monaco font with color-coded primary timezone
- ⚡ **Real-time Updates**: Refreshes every 30 seconds

## Supported Timezones

### Americas
- New York (EST/EDT)
- Chicago (CST/CDT)
- Denver (MST/MDT)
- Los Angeles (PST/PDT)
- Toronto (EST/EDT)
- Vancouver (PST/PDT)
- São Paulo (BRT)

### Europe
- London (GMT/BST)
- Paris (CET/CEST)
- Berlin (CET/CEST)

### Asia & Middle East
- Tokyo (JST)
- Shanghai (CST)
- Mumbai/Delhi (IST)
- Dubai (GST)

### Oceania
- Sydney (AEST/AEDT)
- Melbourne (AEST/AEDT)
- Auckland (NZST/NZDT)

### Universal
- UTC

## Installation

1. Download [`timezone-display.30s.py`](timezone-display.30s.py)
2. Make it executable:
   ```bash
   chmod +x timezone-display.30s.py
   ```
3. Move it to your xbar plugins directory (typically `~/Library/Application Support/xbar/plugins/`)
4. Refresh xbar or restart the application

## Usage

### Menu Bar Display
- The menu bar shows the time for your selected primary timezone
- Default primary timezone is UTC

### Changing Primary Timezone
1. Click on the menu bar item
2. Navigate to "🔄 Change Timezone"
3. Click on any timezone to set it as your primary display
4. The menu bar will immediately update to show the new timezone

### Viewing All Timezones
- Click the menu bar item to see all supported timezones
- Times are displayed in 12-hour format with AM/PM
- DST indicators show (DST) or (STD) where applicable
- Primary timezone is marked with a checkmark (✓) and highlighted in blue

## Configuration

The plugin automatically creates a configuration directory at `~/.config/xbar-timezone/` to store your primary timezone preference. This setting persists across xbar restarts.

## DST Rules

The plugin implements accurate DST rules for:

- **North America**: Second Sunday in March to First Sunday in November
- **Europe**: Last Sunday in March to Last Sunday in October  
- **Australia**: First Sunday in October to First Sunday in April (next year)
- **New Zealand**: Last Sunday in September to First Sunday in April (next year)

DST calculations are accurate for years 2020 and beyond.

## Requirements

- Python 3.x
- xbar application
- macOS

## File Structure

```
timezone-display.30s.py
├── TIMEZONES dictionary - timezone configurations
├── DST calculation functions
├── Configuration management
└── xbar menu generation
```

## Technical Details

- **Update Interval**: 30 seconds (indicated by `.30s.` in filename)
- **Dependencies**: Python 3 standard library only
- **Configuration Storage**: `~/.config/xbar-timezone/primary_timezone.txt`
- **DST Calculation**: Custom implementation with region-specific rules

## Troubleshooting

### Plugin Not Appearing
- Ensure the file is executable: `chmod +x timezone-display.30s.py`
- Check that Python 3 is installed: `python3 --version`
- Verify the file is in the correct xbar plugins directory

### Incorrect Times
- The plugin uses system UTC time as reference
- Ensure your system clock is accurate
- DST rules are current as of 2020+

### Configuration Issues
- Configuration is stored in `~/.config/xbar-timezone/`
- Delete the config directory to reset to defaults
- Primary timezone defaults to UTC if config is corrupted

## Contributing

This plugin is part of the [xbar-plugins](https://github.com/matryer/xbar-plugins) repository. To contribute:

1. Fork the repository
2. Make your changes
3. Test thoroughly with different timezones and DST transitions
4. Submit a pull request

## Author

- **Ameya Bapat** - [@ameyabap](https://github.com/ameyabap)

## License

This plugin is distributed under the same license as the xbar-plugins repository.

## Version History

- **v1.0** - Initial release with full DST support and timezone switching