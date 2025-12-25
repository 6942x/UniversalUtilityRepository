<< UniversalUtility >> 

UniversalUtility is a modular Roblox utility hub that combines common quality-of-life features into a single interface.
The project is designed to be clean, readable, and easy to expand.

It includes systems for Anti-AFK, automation, FPS and network monitoring, auto rejoining, and script execution.


<< Features >>

Modern UI
Animated and draggable interface
Modular layout with reusable components
Configurable UI toggle key

Anti-AFK
Automatic jumping
Automatic clicking (current position, center, or random)
Adjustable delays

Auto Key Spam
Custom key selection
Configurable spam interval
Safe key validation

FPS and Network Monitoring
FPS unlock (executor dependent)
Live FPS tracking (current, average, minimum, maximum)
Ping estimation with network quality rating

Auto Rejoin
Automatically rejoins the game after disconnects or kicks

Executor
Built-in loadstring executor
Optional script auto-save

Persistent Configuration
Settings are saved locally and restored on load (executor dependent)


<< Project Structure >>

UniversalUtility/
│
├── init.lua                    # Main entry point
│
├── core/
│   ├── Config.lua              # Configuration management
│   ├── Utils.lua               # Utility/helper functions
│   ├── ThreadManager.lua       # Thread handling and cleanup
│   └── Storage.lua             # Data persistence (readfile/writefile)
│
├── ui/
│   ├── Interface.lua           # Main UI creation
│   ├── Components.lua          # Reusable UI components
│   ├── Sections.lua            # Section layouts
│   └── Animations.lua          # Tween/animation presets
│
├── features/
│   ├── AntiAFK.lua             # Anti-AFK system
│   ├── AutoSpam.lua            # Key spam automation
│   ├── FPSManager.lua          # FPS unlock & monitoring
│   ├── NetworkMonitor.lua      # Ping & network tracking
│   ├── AutoRejoin.lua          # Reconnection system
│   └── Executor.lua            # Script execution system


---- PERMISSION AND USAGE RIGHTS ----

You are free to copy the entire codebase.
You are free to modify it.
You are free to use it in your own projects.
You are free to learn from it or redistribute modified versions.

No credit is required.
This project is provided as-is for personal and educational use.
