# Auto Dashboard

A modern, professional dashboard that automatically discovers and displays all your Home Assistant entities with zero configuration.

## Quick Setup

After installation via HACS, add this to your `configuration.yaml`:

```yaml
panel_custom:
  - name: ha-auto-dashboard
    sidebar_title: Auto Dashboard
    sidebar_icon: mdi:view-dashboard
    url_path: auto-dashboard
    module_url: /hacsfiles/ha-auto-dashboard/ha-auto-dashboard.js
```

Then restart Home Assistant and look for "Auto Dashboard" in your sidebar!

## Features

- ✅ **Auto-discovery** - Finds all entities automatically
- ✅ **Smart organization** - Grouped by areas and domains
- ✅ **Real-time updates** - Live state changes
- ✅ **Modern design** - Professional dark theme
- ✅ **Responsive** - Works on desktop, tablet, mobile
- ✅ **Touch-friendly** - Optimized for tablets

## Supported Entities

- Lights (toggle, brightness)
- Switches (on/off)
- Sensors (temperature, humidity, power, etc.)
- Binary Sensors (motion, doors, windows)
- Climate (thermostats, AC)
- Covers (blinds, garage doors)

## Important Note

Make sure to use `/hacsfiles/` in your module_url, not `/local/`!

## Need Help?

Check the full README for detailed documentation and troubleshooting.

