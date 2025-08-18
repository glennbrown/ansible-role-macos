# Ansible Role: macOS Setup

This role will configure macOS defaults and additionally install oh-my-zsh.

## Requirements

- macOS (Should work with any modern version)

## Role Variables

```YAML
macos_default_settings:
  # General UI/UX
  # Expand save panel by default
  - domain: NSGlobalDomain
    key: NSNavPanelExpandedStateForSaveMode
    type: bool
    value: true
  # Expand print panel by default
  - domain: NSGlobalDomain
    key: PMPrintingExpandedStateForPrint
    type: bool
    value: true
  # Disable smart quotes as they’re annoying when typing code
  - domain: NSGlobalDomain
    key: NSAutomaticQuoteSubstitutionEnabled
    type: bool
    value: true
  # Disable smart dashes as they’re annoying when typing code
  - domain: NSGlobalDomain
    key: NSAutomaticDashSubstitutionEnabled
    type: bool
    value: true
  # Automatically quit printer app once the print jobs complete
  - domain: com.apple.print.PrintingPrefs
    key: "Quit When Finished"
    type: bool
    value: true
```

```YAML
macos_services:
  - Dock
  - Finder
  - SystemUIServer
```
