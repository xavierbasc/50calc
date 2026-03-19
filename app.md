---
title: app
permalink: /app/
layout: page
description: DM50 calculator app — emulator/simulator with SDL2 GUI, supports macOS, Linux, Windows, iOS, Android and STM32.
comments: false
---

DM50 is a calculator emulator/simulator with a graphical SDL2 interface. It features a monochrome 132×64 LCD display with a color housing skin. Supported platforms: macOS, Linux, Windows, iOS (desktop and mobile), Android, and STM32 (embedded).

**[Download from GitHub](https://github.com/xavierbasc/dm50-app)** — source code, prebuilt binaries and CI artifacts available.

---

## Calculator modes

The main menu offers 10 modes, selectable by icon or by pressing the corresponding digit:

| # | Mode | Description |
|---|------|-------------|
| 0 | **CAS** | Algebraic calculator with expression evaluator (correct precedence, parentheses, powers) |
| 1 | **Matrices** | 2×2 matrix operations: determinant, inverse, sum, product, trace |
| 2 | **Base conversion** | Decimal, binary, octal and hexadecimal converter (16-bit integers) |
| 3 | **Equations** | Linear (ax+b=0) and quadratic (ax²+bx+c=0) equations, including complex roots |
| 4 | **Inequalities** | Linear inequalities (ax+b > 0, <, ≥, ≤) |
| 5 | **RPN** | HP-style RPN calculator with 4-level stack (T, Z, Y, X) |
| 6 | **Complex** | Complex number operations: sum, subtraction, product, division, modulus |
| 7 | **Vectors** | 3D vector calculations: sum, subtraction, dot product, cross product, modulus |
| 8 | **Statistics** | Data set analysis: mean, standard deviation, min, max, sum |
| 9 | **Settings** | Angle, coordinates, number format, precision, LCD refresh, sound/haptic |

---

## Keyboard (desktop)

| Key | Action |
|-----|--------|
| `ESC` | Go back |
| `9` | HOME — main menu |
| `↑ ↓ ← →` | Navigate menu / fields |
| `Enter` | Confirm / evaluate |
| `Backspace` | Delete last character |
| `F1`–`F6` | Function buttons |

| Mode | F1 | F2 | F3 | F4 | F5 | F6 |
|------|----|----|----|----|----|----|
| CAS | `+` | `-` | `*` | `/` | `^` | CLR |
| Matrices | Det(A) | Inv(A) | A+B | A×B | Tr(A) | CLR |
| Base conv. | DEC | BIN | OCT | HEX | — | CLR |
| Equations | Lin | Quad | — | — | Solve | CLR |
| Inequalities | `>` | `<` | `≥` | `≤` | Solve | CLR |
| RPN | ENTR | DEL | `+` | `-` | `*` | `/` |
| Complex | A+B | A-B | A×B | A/B | \|A\| | CLR |
| Vectors | A+B | A-B | A·B | A×B | \|A\| | CLR |
| Statistics | ADD | DEL | STAT | — | — | CLR |
| Settings | ANGL | COOR | NUMB | PREC | — | OK |

---

## Build

```shell
# Auto-detect platform and build
make

# Specific platform
make PLATFORM=macos
make PLATFORM=linux
make PLATFORM=windows
make PLATFORM=stm32

# Build and run (desktop)
make run
```

### Requirements

| Platform | Requirements |
|----------|-------------|
| macOS | gcc (Xcode CLT), make, `brew install sdl2` |
| Linux | gcc, make, `sudo apt install libsdl2-dev` |
| Windows | MSYS2/MinGW64, `pacman -S mingw-w64-x86_64-gcc mingw-w64-x86_64-SDL2 make` |
| iOS | Xcode 15+, iOS SDK, sdl2 submodule |
| Android | Android Studio + NDK, JDK 17+, sdk.dir in `android/local.properties` |
| STM32 | arm-none-eabi-gcc |

---

## CI / Prebuilt binaries

The repository includes a GitHub Actions workflow that builds for all platforms and uploads binaries as downloadable artifacts.

```shell
# Trigger build manually
gh workflow run build.yml --repo xavierbasc/dm50-app --ref main

# List runs
gh run list --repo xavierbasc/dm50-app --workflow build.yml

# Download artifacts from the latest successful run
gh run download --repo xavierbasc/dm50-app
```

Artifacts are also available in the **Actions** tab of the repository → select a run → **Artifacts** section.
