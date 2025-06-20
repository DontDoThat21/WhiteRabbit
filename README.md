# Matrix Rain OLED Display

**Weatherproof 2.42" OLED display showing Matrix-style digital rain effect**

A high-performance, real-time Matrix rain animation designed for outdoor automotive installation. Features smooth 60 FPS acid-green cascading characters on a weatherproof OLED display.

## ✨ Features

- **Smooth 60 FPS animation** with optimized frame buffer rendering
- **Weatherproof design** suitable for exterior vehicle mounting
- **Low power consumption** with automatic sleep/wake functionality
- **Customizable rain parameters** - speed, density, character sets
- **Dual-core optimization** on ESP32 for consistent performance
- **OTA updates** via WiFi for remote configuration changes
- **Auto-brightness** adjustment based on ambient light

## 🛠️ Hardware Requirements

### Core Components
- **ESP32 DevKit** (dual-core for optimal performance)
- **2.42" OLED Display** (128x64, SSD1309 controller)
- **IP67 waterproof enclosure** with clear front panel
- **12V to 5V buck converter** for vehicle power integration
- **Ambient light sensor** (optional, for auto-brightness)

### Weatherproofing
- Marine-grade cable glands
- Conformal coating for PCB protection
- Gasket sealing for display mounting
- Heat shrink tubing for all connections

## 🚀 Performance Optimizations

- **Double buffering** for flicker-free animation
- **Dirty rectangle updates** - only redraws changed screen areas
- **Fixed-point mathematics** for faster calculations
- **DMA-accelerated SPI** transfers to display
- **Lookup tables** for pre-calculated fade effects
- **FreeRTOS task scheduling** for real-time performance

## 📦 Software Architecture

```
┌─────────────────┐
│ Main Loop       │ ← 60 FPS timer interrupt
├─────────────────┤
│ Matrix Engine   │ ← Rain drop physics & rendering
├─────────────────┤
│ Frame Buffer    │ ← 128x64 monochrome bitmap
├─────────────────┤
│ U8g2 Driver     │ ← Optimized OLED graphics library
└─────────────────┘
```

## 🎯 Installation

### Hardware Setup
1. Mount display in weatherproof enclosure
2. Route control cables through vehicle firewall
3. Connect ESP32 to vehicle 12V power system
4. Install controller in protected interior location

### Software Installation
```bash
git clone https://github.com/yourusername/matrix-rain-oled
cd matrix-rain-oled
# Open in Arduino IDE or PlatformIO
# Configure WiFi credentials in config.h
# Upload to ESP32
```

## ⚙️ Configuration

Customize rain effect parameters in `config.h`:

```cpp
#define RAIN_SPEED_MIN 1
#define RAIN_SPEED_MAX 4
#define RAIN_DENSITY 0.7
#define CHARACTER_SET MATRIX_KATAKANA
#define BRIGHTNESS_AUTO true
```

## 🔧 Libraries Used

- **U8g2** - High-performance OLED graphics
- **WiFi** - OTA updates and remote control
- **FreeRTOS** - Real-time task scheduling
- **ArduinoOTA** - Over-the-air firmware updates

## 📊 Performance Metrics

- **Frame Rate**: Consistent 60 FPS
- **Power Consumption**: ~150mA @ 5V during operation
- **Boot Time**: < 2 seconds
- **Memory Usage**: ~40KB RAM, ~200KB Flash

## 🌧️ Weather Resistance

- **Operating Temperature**: -20°C to +70°C
- **IP Rating**: IP67 (dust tight, waterproof)
- **UV Resistance**: Polycarbonate front panel
- **Vibration Tested**: Automotive grade components

## 🤝 Contributing

Contributions welcome! Please read [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

### Roadmap
- [ ] RGB color support for multi-color rain
- [ ] Multiple animation modes (binary, hex, custom)
- [ ] Mobile app for real-time configuration
- [ ] CAN bus integration for vehicle data display
- [ ] Solar panel charging option

## 📜 License

MIT License - see [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- Inspired by The Matrix (1999) digital rain effect
- U8g2 library by olikraus
- ESP32 community for optimization techniques

---

**⚠️ Installation Warning**: Ensure proper waterproofing before exterior mounting. Improper installation may damage vehicle electronics.
