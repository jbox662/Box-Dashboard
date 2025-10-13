# Home Assistant Auto Dashboard

[![hacs_badge](https://img.shields.io/badge/HACS-Custom-orange.svg)](https://github.com/custom-components/hacs)
![Version](https://img.shields.io/badge/version-1.0.0-blue)
![Home Assistant](https://img.shields.io/badge/Home%20Assistant-2023.1%2B-blue)

A modern, professional dashboard for Home Assistant that **automatically discovers and displays all your entities** with zero configuration.

![Dashboard Preview](https://img.shields.io/badge/Status-Ready-brightgreen)

---

## ✨ Features

### 🎯 Zero Configuration
- **Auto-discovery**: Automatically finds and displays all entities
- **No manual setup**: Just install via HACS and add to configuration
- **Smart organization**: Entities grouped by areas and domains
- **Real-time updates**: Live state changes

### 🏠 Smart Organization
- **Area filtering**: Group entities by rooms (Living Room, Bedroom, etc.)
- **Domain filtering**: Filter by entity type (Lights, Switches, Sensors, etc.)
- **Entity count badges**: See how many entities in each category
- **Instant filtering**: Click to filter, no page reload

### 🎨 Modern Design
- **Professional dark theme**: Optimized for smart home interfaces
- **Responsive layout**: Works on desktop, tablet, and mobile
- **Smooth animations**: Polished UI with hover effects
- **Touch-friendly**: Optimized for tablets and touch screens
- **Color-coded badges**: Quick visual identification

### 🎛️ Supported Entity Types
- ✅ **Lights** - Toggle on/off, brightness control
- ✅ **Switches** - Simple on/off control
- ✅ **Sensors** - Temperature, humidity, power, etc.
- ✅ **Binary Sensors** - Motion, doors, windows
- ✅ **Climate** - Thermostat and AC control
- ✅ **Covers** - Blinds and garage doors
- ✅ More entity types coming soon!

---

## 🚀 Installation

### Via HACS (Recommended)

1. **Open HACS** in your Home Assistant
2. Click on **"Frontend"**
3. Click the **"+"** button
4. Search for **"Auto Dashboard"**
5. Click **"Download"**
6. **Restart Home Assistant**

### Add to Configuration

After installation, add to your `configuration.yaml`:

```yaml
panel_custom:
  - name: ha-auto-dashboard
    sidebar_title: Auto Dashboard
    sidebar_icon: mdi:view-dashboard
    url_path: auto-dashboard
    module_url: /hacsfiles/ha-auto-dashboard/ha-auto-dashboard.js
```

**Important**: Note the `/hacsfiles/` path - this is different from manual installation!

### Restart Again

Go to **Settings** → **System** → **Restart**

### Done!

Look for **"Auto Dashboard"** in your sidebar and click to open!

---

## ⚙️ Configuration Options

### Basic Configuration

```yaml
panel_custom:
  - name: ha-auto-dashboard
    sidebar_title: Auto Dashboard        # Title shown in sidebar
    sidebar_icon: mdi:view-dashboard     # Icon in sidebar
    url_path: auto-dashboard             # URL path (must be unique)
    module_url: /hacsfiles/ha-auto-dashboard/ha-auto-dashboard.js
```

### Custom Icons

You can use any [Material Design Icon](https://pictogrammers.com/library/mdi/):
- `mdi:home` - Home icon
- `mdi:monitor-dashboard` - Monitor dashboard
- `mdi:view-grid` - Grid view
- `mdi:view-dashboard-variant` - Dashboard variant
- `mdi:tablet-dashboard` - Tablet dashboard

### Multiple Instances

Create multiple dashboards with different names:

```yaml
panel_custom:
  - name: ha-auto-dashboard-main
    sidebar_title: Main Dashboard
    sidebar_icon: mdi:home
    url_path: main-dashboard
    module_url: /hacsfiles/ha-auto-dashboard/ha-auto-dashboard.js
    
  - name: ha-auto-dashboard-lights
    sidebar_title: Lights
    sidebar_icon: mdi:lightbulb
    url_path: lights-dashboard
    module_url: /hacsfiles/ha-auto-dashboard/ha-auto-dashboard.js
```

### Admin Only Access

Restrict to admin users:

```yaml
panel_custom:
  - name: ha-auto-dashboard
    sidebar_title: Auto Dashboard
    sidebar_icon: mdi:view-dashboard
    url_path: auto-dashboard
    module_url: /hacsfiles/ha-auto-dashboard/ha-auto-dashboard.js
    require_admin: true
```

---

## 📸 Screenshots

### Main Dashboard
- All entities displayed in a clean grid layout
- Area and domain filters in sidebar
- Connection status and time in header
- Interactive entity cards with controls

### Entity Cards
- **Lights**: Toggle button with brightness slider
- **Switches**: Simple on/off toggle
- **Sensors**: Value display with units and icons
- **Binary Sensors**: State indicators (motion, doors, windows)
- **Climate**: Current/target temperature with +/- controls
- **Covers**: Open/close/stop buttons

### Responsive Design
- **Desktop**: 3-column grid layout
- **Tablet**: 2-column grid layout
- **Mobile**: 1-column grid layout
- Touch-optimized controls throughout

---

## 🔧 Troubleshooting

### Panel Not Showing in Sidebar

1. **Check configuration syntax**
   - Go to **Developer Tools** → **YAML** → **Check Configuration**
   - Fix any YAML errors

2. **Verify HACS installation**
   - Go to HACS → Frontend
   - Check that "Auto Dashboard" is installed
   - Try reinstalling if needed

3. **Check the module URL**
   - Must be `/hacsfiles/ha-auto-dashboard/ha-auto-dashboard.js`
   - Not `/local/` (that's for manual installation)

4. **Clear browser cache**
   - Hard refresh: Ctrl+Shift+R (Windows/Linux) or Cmd+Shift+R (Mac)

5. **Check Home Assistant logs**
   - Go to **Settings** → **System** → **Logs**
   - Look for errors related to panel_custom

### Blank Page or Loading Forever

1. **Check browser console**
   - Press F12 to open developer tools
   - Look for JavaScript errors in Console tab

2. **Verify file is accessible**
   - Visit: `http://YOUR_HA_URL:8123/hacsfiles/ha-auto-dashboard/ha-auto-dashboard.js`
   - Should download or show JavaScript code

3. **Clear browser cache**
   - Hard refresh the page

4. **Try different browser**
   - Test in Chrome, Firefox, or Safari

### Entities Not Showing

1. **Verify you have entities**
   - Go to **Developer Tools** → **States**
   - Confirm entities exist

2. **Check browser console**
   - Look for errors (F12 → Console)

3. **Try different filters**
   - Click "All Entities" in sidebar
   - Try different area or domain filters

4. **Refresh the page**

### After HACS Update

If the dashboard stops working after a HACS update:

1. **Clear browser cache** (Ctrl+Shift+R)
2. **Check configuration** still uses `/hacsfiles/` path
3. **Restart Home Assistant**
4. **Reinstall from HACS** if needed

---

## 🔄 Updating

### Via HACS

1. Go to **HACS** → **Frontend**
2. Find **"Auto Dashboard"**
3. Click **"Update"** if available
4. **Clear browser cache** (Ctrl+Shift+R)
5. **Reload the page**

No Home Assistant restart needed for updates!

---

## 📱 Mobile Support

Works perfectly on mobile devices:
- Responsive design adapts to screen size
- Touch-optimized controls
- Works in Home Assistant mobile app
- Works in mobile browsers
- Add to home screen for app-like experience

---

## 🎯 Use Cases

### Perfect For
- ✅ Quick Home Assistant setup
- ✅ Wall-mounted tablets
- ✅ Family members who want simple interface
- ✅ Testing new entities
- ✅ Mobile control
- ✅ Guest access
- ✅ Kiosk mode displays

### Not Ideal For
- ❌ Highly customized layouts
- ❌ Complex automation controls
- ❌ Custom card types
- ❌ Specific design requirements

For advanced customization, use standard Home Assistant dashboards.

---

## 🆚 Comparison

### vs. Standard Home Assistant Dashboards

| Feature | Auto Dashboard | Standard Dashboards |
|---------|---------------|---------------------|
| **Setup** | Zero configuration | Manual card configuration |
| **Discovery** | Automatic | Manual entity selection |
| **Organization** | Auto-grouped | Manual grouping |
| **Updates** | Auto-updates | Manual updates needed |
| **Learning Curve** | ⭐ Easy | ⭐⭐ Medium |

### vs. Dwains Dashboard

| Feature | Auto Dashboard | Dwains Dashboard |
|---------|---------------|------------------|
| **Installation** | HACS one-click | HACS + extensive config |
| **Configuration** | 5 lines YAML | Extensive YAML |
| **Maintenance** | Zero | Ongoing |
| **Learning Curve** | ⭐ Easy | ⭐⭐⭐ Hard |
| **Customization** | Limited | Extensive |

---

## 🔐 Security

- Uses Home Assistant's built-in authentication
- No separate login required
- Respects user permissions
- Runs entirely in browser
- No external connections
- No data collection

---

## 🐛 Known Issues

None currently. Please report issues on GitHub!

---

## 🚀 Roadmap

Future enhancements:
- [ ] Entity history graphs
- [ ] Custom color themes
- [ ] Entity search functionality
- [ ] Favorite entities
- [ ] Scene controls
- [ ] Automation triggers
- [ ] Voice control integration
- [ ] Custom entity grouping

---

## 🤝 Contributing

Contributions are welcome! Please:
1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

---

## 📄 License

This project is open source and available under the MIT License.

---

## 🙏 Acknowledgments

- **Home Assistant** - Amazing smart home platform
- **HACS** - Community Store
- **React** - UI framework
- **Tailwind CSS** - Styling
- **shadcn/ui** - Component library
- **Lucide** - Icons

---

## 📞 Support

### Getting Help
- Check this README
- Check [Troubleshooting](#troubleshooting) section
- Search existing GitHub issues
- Create a new GitHub issue
- Ask on Home Assistant Community Forum
- Ask on Home Assistant Discord

### Reporting Issues

When reporting issues, please include:
- Home Assistant version
- HACS version
- Browser and version
- Error messages from browser console
- Error messages from Home Assistant logs
- Steps to reproduce
- Screenshots if applicable

---

## ⭐ Show Your Support

If you like this project, please give it a ⭐ on GitHub!

---

**Made with ❤️ for the Home Assistant community**

**Enjoy your auto-generated dashboard! 🏠✨**

