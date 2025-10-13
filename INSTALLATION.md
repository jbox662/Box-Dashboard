# Installation Guide - HACS Version

## Prerequisites

- ✅ Home Assistant 2023.1 or newer
- ✅ HACS installed and configured
- ✅ Access to edit `configuration.yaml`

---

## Step-by-Step Installation

### Step 1: Install via HACS

#### Option A: Default HACS Repository (Once Published)

1. Open **HACS** in Home Assistant
2. Click on **"Frontend"** tab
3. Click the **"+ Explore & Download Repositories"** button
4. Search for **"Auto Dashboard"**
5. Click on **"Auto Dashboard"**
6. Click **"Download"**
7. Wait for download to complete

#### Option B: Custom Repository (For Testing)

1. Open **HACS** in Home Assistant
2. Click the **three dots** menu (⋮) in the top right
3. Select **"Custom repositories"**
4. Add repository URL: `https://github.com/YOUR_USERNAME/ha-auto-dashboard`
5. Select category: **"Dashboard"** (or "Plugin")
6. Click **"Add"**
7. Find "Auto Dashboard" in the list
8. Click **"Download"**

---

### Step 2: Restart Home Assistant

1. Go to **Settings** → **System**
2. Click **"Restart"**
3. Wait for Home Assistant to restart (usually 1-2 minutes)

---

### Step 3: Add to Configuration

1. **Open your `configuration.yaml` file**
   - Via File Editor add-on
   - Via SSH/terminal
   - Via Samba share

2. **Add the following configuration:**

```yaml
panel_custom:
  - name: ha-auto-dashboard
    sidebar_title: Auto Dashboard
    sidebar_icon: mdi:view-dashboard
    url_path: auto-dashboard
    module_url: /hacsfiles/ha-auto-dashboard/ha-auto-dashboard.js
```

3. **Save the file**

**Important Notes:**
- The `module_url` MUST use `/hacsfiles/` (not `/local/`)
- The path is `/hacsfiles/ha-auto-dashboard/ha-auto-dashboard.js`
- Make sure indentation is correct (2 spaces per level)
- No tabs, only spaces

---

### Step 4: Check Configuration

1. Go to **Developer Tools** → **YAML**
2. Click **"Check Configuration"**
3. Fix any errors if shown
4. If valid, proceed to restart

---

### Step 5: Restart Again

1. Go to **Settings** → **System**
2. Click **"Restart"**
3. Wait for restart to complete

---

### Step 6: Access Your Dashboard

1. Look in the **sidebar** for **"Auto Dashboard"**
2. Click on it
3. **Done!** Your dashboard should load with all entities

---

## Configuration Examples

### Basic Configuration

```yaml
panel_custom:
  - name: ha-auto-dashboard
    sidebar_title: Auto Dashboard
    sidebar_icon: mdi:view-dashboard
    url_path: auto-dashboard
    module_url: /hacsfiles/ha-auto-dashboard/ha-auto-dashboard.js
```

### With Custom Title and Icon

```yaml
panel_custom:
  - name: ha-auto-dashboard
    sidebar_title: My Smart Home
    sidebar_icon: mdi:home
    url_path: smart-home
    module_url: /hacsfiles/ha-auto-dashboard/ha-auto-dashboard.js
```

### Admin Only Access

```yaml
panel_custom:
  - name: ha-auto-dashboard
    sidebar_title: Auto Dashboard
    sidebar_icon: mdi:view-dashboard
    url_path: auto-dashboard
    module_url: /hacsfiles/ha-auto-dashboard/ha-auto-dashboard.js
    require_admin: true
```

### Multiple Instances

```yaml
panel_custom:
  # Main dashboard
  - name: ha-auto-dashboard-main
    sidebar_title: Main Dashboard
    sidebar_icon: mdi:home
    url_path: main
    module_url: /hacsfiles/ha-auto-dashboard/ha-auto-dashboard.js
  
  # Lights dashboard
  - name: ha-auto-dashboard-lights
    sidebar_title: Lights
    sidebar_icon: mdi:lightbulb
    url_path: lights
    module_url: /hacsfiles/ha-auto-dashboard/ha-auto-dashboard.js
  
  # Sensors dashboard
  - name: ha-auto-dashboard-sensors
    sidebar_title: Sensors
    sidebar_icon: mdi:thermometer
    url_path: sensors
    module_url: /hacsfiles/ha-auto-dashboard/ha-auto-dashboard.js
```

---

## Troubleshooting

### Panel Not Showing

**Problem**: Dashboard doesn't appear in sidebar after restart

**Solutions:**

1. **Check HACS installation**
   - Go to HACS → Frontend
   - Verify "Auto Dashboard" is listed
   - Check it says "Installed"
   - Try reinstalling if needed

2. **Verify configuration**
   - Check `configuration.yaml` syntax
   - Use YAML validator online if needed
   - Ensure proper indentation (2 spaces)
   - No tabs, only spaces

3. **Check configuration is valid**
   - Developer Tools → YAML → Check Configuration
   - Fix any errors shown

4. **Verify module URL**
   - Must be `/hacsfiles/ha-auto-dashboard/ha-auto-dashboard.js`
   - NOT `/local/ha-auto-dashboard.js`
   - NOT `/hacsfiles/ha-auto-dashboard-bundle.js`

5. **Check Home Assistant logs**
   - Settings → System → Logs
   - Look for errors about panel_custom
   - Look for errors about loading JavaScript

6. **Clear browser cache**
   - Hard refresh: Ctrl+Shift+R (Windows/Linux)
   - Hard refresh: Cmd+Shift+R (Mac)
   - Or try incognito/private mode

7. **Try different url_path**
   - Must be unique across all panels
   - Try: `auto-dash` or `autodashboard`

---

### Blank Page

**Problem**: Panel opens but shows blank page

**Solutions:**

1. **Check browser console**
   - Press F12 to open developer tools
   - Go to Console tab
   - Look for error messages
   - Share errors when asking for help

2. **Verify file is accessible**
   - Open: `http://YOUR_HA_URL:8123/hacsfiles/ha-auto-dashboard/ha-auto-dashboard.js`
   - Should download or show JavaScript code
   - If 404 error, reinstall from HACS

3. **Clear browser cache**
   - Hard refresh the page
   - Or clear all browser data

4. **Try different browser**
   - Test in Chrome, Firefox, Safari
   - Some browsers may have issues

5. **Check HACS files**
   - Files should be in: `/config/www/community/ha-auto-dashboard/`
   - Check file exists and is readable

---

### Entities Not Showing

**Problem**: Dashboard loads but no entities appear

**Solutions:**

1. **Verify entities exist**
   - Go to Developer Tools → States
   - Check you have entities configured

2. **Check browser console**
   - Press F12 → Console
   - Look for errors

3. **Try filtering**
   - Click "All Entities" in sidebar
   - Try different area filters
   - Try different domain filters

4. **Refresh the page**
   - Hard refresh (Ctrl+Shift+R)

---

### After HACS Update

**Problem**: Dashboard stops working after updating HACS or Home Assistant

**Solutions:**

1. **Update Auto Dashboard**
   - Go to HACS → Frontend
   - Check for updates to Auto Dashboard
   - Update if available

2. **Clear browser cache**
   - Hard refresh (Ctrl+Shift+R)
   - Or clear all browser data

3. **Verify configuration**
   - Check `configuration.yaml` hasn't changed
   - Verify module_url is still correct

4. **Reinstall from HACS**
   - Remove from HACS
   - Reinstall
   - Restart Home Assistant
   - Clear browser cache

---

### Configuration Errors

**Problem**: Home Assistant won't start after adding configuration

**Solutions:**

1. **Check YAML syntax**
   - Indentation must be exactly 2 spaces per level
   - No tabs allowed
   - Proper spacing after colons
   - Use online YAML validator

2. **Common mistakes:**
   ```yaml
   # WRONG - missing dash
   panel_custom:
     name: ha-auto-dashboard
   
   # CORRECT - has dash
   panel_custom:
     - name: ha-auto-dashboard
   
   # WRONG - tabs instead of spaces
   panel_custom:
   	- name: ha-auto-dashboard
   
   # CORRECT - spaces only
   panel_custom:
     - name: ha-auto-dashboard
   ```

3. **Remove and recover**
   - If HA won't start, remove the panel_custom section
   - Restart Home Assistant
   - Fix the syntax
   - Add back carefully

---

## Updating

### Via HACS

1. Go to **HACS** → **Frontend**
2. Find **"Auto Dashboard"**
3. If update available, click **"Update"**
4. Wait for download
5. **Clear browser cache** (Ctrl+Shift+R)
6. **Reload the page**

**Note**: No Home Assistant restart needed for updates!

---

## Uninstalling

### Step 1: Remove from Configuration

1. Open `configuration.yaml`
2. Remove the `panel_custom` entry for Auto Dashboard
3. Save the file

### Step 2: Restart Home Assistant

Settings → System → Restart

### Step 3: Remove from HACS

1. Go to HACS → Frontend
2. Find "Auto Dashboard"
3. Click the three dots (⋮)
4. Select "Remove"
5. Confirm removal

---

## File Locations

### HACS Downloads To:
```
/config/www/community/ha-auto-dashboard/
└── ha-auto-dashboard.js
```

### Configuration File:
```
/config/configuration.yaml
```

### URL Paths:
- Module URL: `/hacsfiles/ha-auto-dashboard/ha-auto-dashboard.js`
- Direct access: `http://YOUR_HA_URL:8123/hacsfiles/ha-auto-dashboard/ha-auto-dashboard.js`
- Dashboard URL: `http://YOUR_HA_URL:8123/auto-dashboard` (or your custom url_path)

---

## Getting Help

### Before Asking for Help

1. Check this installation guide
2. Check the main README
3. Check browser console for errors (F12)
4. Check Home Assistant logs
5. Try the troubleshooting steps above

### When Asking for Help

Please provide:
- Home Assistant version
- HACS version
- Browser and version
- Error messages from browser console
- Error messages from Home Assistant logs
- Your `panel_custom` configuration (remove sensitive info)
- Steps to reproduce the issue
- Screenshots if applicable

### Where to Get Help

- GitHub Issues (preferred for bugs)
- Home Assistant Community Forum
- Home Assistant Discord
- Reddit r/homeassistant

---

## Tips

1. **Bookmark the dashboard** - Add to browser bookmarks for quick access
2. **Mobile home screen** - Add to mobile home screen for app-like experience
3. **Multiple instances** - Create different dashboards for different purposes
4. **Wall tablets** - Perfect for wall-mounted displays
5. **Kiosk mode** - Use with HA's kiosk mode for clean display

---

**Enjoy your new Auto Dashboard! 🎉**

