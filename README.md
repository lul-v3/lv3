# LV3 Framework

<div align="center">

![Version](https://img.shields.io/badge/version-0.1.2--alpha-red?style=for-the-badge)
![C++](https://img.shields.io/badge/C++-20-blue?style=for-the-badge&logo=cplusplus)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Pre--release-orange?style=for-the-badge)

**Lightweight C++20 framework for desktop applications and games.**

*Simplicity over complexity. Control over bloat.*

</div>


## Important Notice

> **This repository is currently in private / pre-release status.**
>
> The code is not yet public as I am actively working on:
> - Implementing core features
> - Code cleanup and refactoring
> - Documentation and examples
> - Ensuring API stability
>
> **Expected public release:** Q3/Q4 2026 (timeline depends on development progress and available time)
>
> Follow me on [GitHub](https://github.com/lul-v3) for updates!


## About

**LV3** (pronounced "Level Three") is a modern, lightweight C++20 framework designed for building desktop applications and games from scratch.

Born from frustration with bloated engines and overcomplicated abstractions, LV3 focuses on clean code, performance, and giving you full control over your software. It's not another "everything-included" framework — it's a solid foundation that you can extend as you need.

### Philosophy

- **Minimal dependencies** — Only GLFW3, OpenGL, and glm
- **No bloat** — You decide what features you need
- **Modern C++** — RAII, smart pointers, constexpr where it makes sense
- **Cross-platform** — Windows & Linux (macOS planned)


## Features (Current)

### Core Modules

| Module | Description | Status |
|--------|-------------|--------|
| **Window** | GLFW-based window creation with OpenGL context |   Stable |
| **Input** | Keyboard & mouse handling with state tracking |   Stable |
| **Logger** | Multi-level logging with file output and colors |   Stable |
| **GameTime** | Delta time, FPS counter, time scale support |   Stable |
| **App** | Application lifecycle management (init, update, render) |   Stable |

### Window Features
- Resizable windows
- VSync toggle
- Windowed / Fullscreen / Borderless modes
- OpenGL 4.6 core context

### Input Features
- Keyboard key states (down, pressed, released)
- Mouse button states
- Mouse delta movement (raw input style)
- Cursor locking (FPS camera style)
- Cursor visibility toggle

### Logger Features
- Multiple log levels (DEBUG, INFO, WARN, ERROR, FATAL)
- File output with timestamps
- Colored console output
- File & line information for errors
- Debug/release aware macros


## Roadmap

### v0.1.x (Current - Pre-release)
- [x] Window creation & management
- [x] Input system (keyboard + mouse)
- [x] Logger with file output
- [x] GameTime & delta time utilities
- [x] Application base class

### v0.2.x (Next — Public beta)
- [ ] OpenGL renderer abstraction
- [ ] Shader management
- [ ] Texture loading & management
- [ ] Sprite rendering (2D)
- [ ] Camera system (orthographic & perspective)
- [ ] Resource manager

### v0.3.x (Future)
- [ ] Audio system (miniaudio / OpenAL)
- [ ] ECS architecture
- [ ] Scene / node system
- [ ] Serialization (JSON/TOML)

### v1.0 (Long-term)
- [ ] Full documentation & tutorials
- [ ] Example game projects
- [ ] Template project generator
- [ ] Basic 3D primitive rendering
- [ ] Vulkan backend
- [ ] ImGui integration (debug UI)


## Quick Example (Future API)

```cpp
#include <lv3/App.h>
#include <lv3/Logger.h>
#include <lv3/Input.h>

using namespace lv3::core;

class MyGame : public App {
public:
    virtual bool OnInit() override {
        ENGINE_INFO("Game initialized!");
        return true;
    }
    
    virtual void OnUpdate() override {
        if (Input::IsKeyDown(Key::SPACE)) {
            ENGINE_DEBUG("Space pressed!");
        }
        
        float dt = GameTime::GetDeltaTime();
        // update game logic here...
    }
    
    virtual void OnRender() override {
        // rendering code here
    }
};

int main() {
    MyGame game;
    AppInformation info;
    info.WindowInfo.Title = "My LV3 Game";
    info.WindowInfo.Width = 1280;
    info.WindowInfo.Height = 720;
    info.WindowInfo.VSync = true;
    
    game.Run(info);
    return 0;
}
```


## Coming Soon
This README will be updated with:
- Build instructions
- Installation guide
- Full API documentation
- Example projects
- Tutorial series


## Support & Community
- **GitHub**: [@lul-v3](https://github.com/lul-v3) — Follow for release announcements
- **Ko-fi**: [ko-fi.com/lulv3](https://ko-fi.com/lulv3) — Support the development


## License
MIT License — see [LICENSE](https://github.com/lul-v3/lv3/blob/main/LICENSE) file for details.

<br>
<br>
<div align="center">

Made with curiosity, C++, and ☕ by lulv3
</div>
