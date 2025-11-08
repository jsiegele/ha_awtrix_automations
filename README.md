# HA\_AWTRIX\_Automations

A collection of Home Assistant (HA) automations, scripts, and blueprints specifically designed to control the AWTRIX display.

This repository provides pre-configured settings to display various information and notifications from Home Assistant on your AWTRIX clock.

## 🌟 Features (Must be adapted!)

The following are typical functionalities provided by the YAML files in this repository. **Please adjust this list to accurately reflect the actual automations and scripts you have included.**

*   **Weather Display:** Automatically switches to show the current temperature and weather conditions (e.g., every 5 minutes).
*   **Washing Machine Status:** Displays a notification on the AWTRIX when the washing machine cycle is finished.
*   **Urgent Alerts:** Triggers a high-priority, scrolling message for critical Home Assistant alerts (e.g., security status, smoke detection).
*   **Dynamic Brightness Control:** Adjusts the AWTRIX brightness based on the time of day or an external light sensor.
*   **Custom Tickers:** Displays dynamic text, like the number of open windows or today's date, via custom API.

## 📋 Prerequisites

To utilize these automations, you need the following components:

1.  **Home Assistant** (with a running configuration).
2.  **Ulanci TC001 Clock with** (with up-to-date Awtrix 3 firmware).
3.  **AWTRIX and Home Assistant Integration:** The AWTRIX must be configured to receive commands, via **MQTT services** 

## 🛠️ Installation and Configuration

Since I am providing the **raw automation YAML files** here, you must maintain the configuration manually by following these steps to integrate the YAML contents into your Home Assistant configuration.

### 1. Copy the YAML Content

Navigate to the desired YAML files in the GitHub repository (e.g., under `automations/`).

1.  Open the file (e.g., `awtrix_weather.yaml`).
2.  Click the **Raw** button to display the pure code.
3.  Copy the entire content of the file.

### 2. Insert Content into Home Assistant

Depending on your preferred method, paste the content into the corresponding location:

| Method | Location | Steps |
| :--- | :--- | :--- |
| **UI Editor** | Home Assistant → Settings → Automations & Scenes → Automations → "Create Automation" → **Three Dots** → "Edit in YAML" | Paste the copied YAML content directly into the editor, replacing all existing lines. |
| **YAML File** | Your configuration directory (`config/`) | Paste the content at the end of your main `automations.yaml` file or as a new file if you use the `!include_dir_merge_list` structure. |

### 3. Adapt Entities (CRITICAL!)

The included automations use entity names from my personal setup (e.g., `media_player.awtrix_clock`, `sensor.my_temperature`). **You must adapt these to your own entities.**

*   Open the pasted YAML code.
*   Search for entity IDs (e.g., `entity_id: ...`).
*   Replace them with your actual entity IDs (e.g., `entity_id: media_player.display_awtrix`).

### 4. Icon Reference

The automations often reference specific icons via their ID. The icons are **not** part of this repository. You can find and download (just use the ID to search for) them from here:

> **Icon Source:** https://developer.lametric.com/icons

### 5. Finalize Configuration

*   **If you used the UI Editor (Step 2):** Click "Save" in the automation editor.
*   **If you edited the YAML files manually (Step 2):**
    1.  Go to Home Assistant **Settings** → **System** → **Hardware**.
    2.  Click the **three dots** in the upper right corner and select **Reload YAML configuration** (or restart Home Assistant).
