# Dark-Light Mode Toggle Script

This PowerShell script allows you to toggle between Dark and Light mode in Windows. It also restarts the Windows Explorer process to ensure that UI elements such as the taskbar and File Explorer reflect the changes.

## How It Works

- The script checks the current theme (Dark or Light) based on the Windows Registry values.
- If the system is in Light mode, it switches to Dark mode, and vice versa.
- After the theme is toggled, the script restarts the **explorer.exe** process to apply the changes system-wide.

## Prerequisites

- **PowerShell**: The script is designed to be executed using PowerShell. Make sure PowerShell is installed on your system.
- **Windows**: The script is compatible with Windows systems that support Dark and Light modes.

## Script Overview

The script performs the following steps:
1. Retrieves the current theme setting from the Windows Registry.
2. Toggles between Dark and Light modes by updating the Registry values.
3. Restarts the **explorer.exe** process to apply the changes.

### Registry Keys Used

- `HKCU:\Software\Microsoft\Windows\CurrentVersion\Themes\Personalize`
  - `AppsUseLightTheme`: Controls the theme for apps.
  - `SystemUsesLightTheme`: Controls the theme for the Windows system (e.g., taskbar, start menu).

## Installation

1. Download or copy the script from this repository.
2. Save the script with a `.ps1` extension, for example: `ToggleDarkLight.ps1`.

## Usage

### Manually

You can manually run the script using PowerShell:

<!-- 
```bash
powershell.exe -ExecutionPolicy Bypass -File "C:\path\to\your\script.ps1" 
-->

## Using PowerToys (Optional)
To create a keyboard shortcut for toggling Dark/Light mode:

1. Open PowerToys and go to Keyboard Manager.

2. Create a new shortcut (e.g., Win + D).

3. Set the action to Run Program.

4. In the Program field, enter: `powershell.exe`

5. In the Arguments field, enter: `-ExecutionPolicy Bypass -File "C:\path\to\your\script.ps1"`

6. Leave the Start in field empty or specify the directory where your script is located (optional).

7. Save and test your new keyboard shortcut.

## Script code 
# PowerShell script to toggle Dark/Light mode
<!-- 
$LightTheme = Get-ItemProperty -Path 'HKCU:\Software\Microsoft\Windows\CurrentVersion\Themes\Personalize' -Name 'AppsUseLightTheme'

if ($LightTheme.AppsUseLightTheme -eq 1) {
    Set-ItemProperty -Path 'HKCU:\Software\Microsoft\Windows\CurrentVersion\Themes\Personalize' -Name 'AppsUseLightTheme' -Value 0
    Set-ItemProperty -Path 'HKCU:\Software\Microsoft\Windows\CurrentVersion\Themes\Personalize' -Name 'SystemUsesLightTheme' -Value 0
} else {
    Set-ItemProperty -Path 'HKCU:\Software\Microsoft\Windows\CurrentVersion\Themes\Personalize' -Name 'AppsUseLightTheme' -Value 1
    Set-ItemProperty -Path 'HKCU:\Software\Microsoft\Windows\CurrentVersion\Themes\Personalize' -Name 'SystemUsesLightTheme' -Value 1
}

# Restart Windows Explorer to apply changes
Stop-Process -Name explorer -Force 
-->

## License
This project is licensed under the MIT License