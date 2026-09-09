<div align="center">

# 🎮 ShooterGameUI

### A Polished Main Menu & Settings System for Unreal Engine 5.6

*Featuring a fully crafted 3D sci-fi environment backdrop, animated hero character,  
interactive UMG widgets with audio feedback, sliding transitions, and functional graphics settings.*

---

![Unreal Engine](https://img.shields.io/badge/Unreal_Engine-5.6-0E1128?style=for-the-badge&logo=unrealengine&logoColor=white)
![Blueprints](https://img.shields.io/badge/Blueprints-Visual_Scripting-137CBD?style=for-the-badge&logo=blueprint&logoColor=white)
![Platform](https://img.shields.io/badge/Platform-Windows-0078D6?style=for-the-badge&logo=windows&logoColor=white)
![DirectX](https://img.shields.io/badge/RHI-DirectX_12-brightgreen?style=for-the-badge)
![Ray Tracing](https://img.shields.io/badge/Ray_Tracing-Enabled-orange?style=for-the-badge)

</div>

---

## 📋 Table of Contents

- [Overview](#-overview)
- [Features](#-features)
- [Screenshots](#-screenshots)
- [Project Structure](#-project-structure)
- [Technical Details](#-technical-details)
- [Asset Packs Used](#-asset-packs-used)
- [Getting Started](#-getting-started)
- [Controls & Interaction](#-controls--interaction)
- [Configuration](#-configuration)
- [License](#-license)

---

## 🔍 Overview

**ShooterGameUI** is a standalone Unreal Engine 5.6 project focused entirely on delivering a **high-quality, production-ready main menu and settings system** for a shooter-style game. Rather than a gameplay prototype, this project showcases UI/UX design, environment art direction, and polished front-end systems — everything a player sees *before* the game begins.

The menu is built with **UMG (Unreal Motion Graphics)** and is backed by a fully constructed **3D sci-fi environment** that serves as a living, atmospheric backdrop. An animated **Paragon Twinblast** character stands in-scene, breathing life into the menu with idle animations, while carefully placed lighting, particle effects, and environmental details create a cinematic first impression.

---

## ✨ Features

### 🖥️ Main Menu
- **Animated Menu Transitions** — Smooth sliding animations when opening and closing menu panels
- **Hover & Click Audio Feedback** — Every button plays distinct sound effects on hover and click for tactile, responsive interaction
- **Touch & Hover Visual Responses** — Buttons react visually to mouse hover and touch input with highlights and scale effects
- **Custom Typography** — Styled with **Coalition v2** and **Michroma** fonts for a sleek, futuristic aesthetic
- **Blueprint Interface System** — Clean `BPI_UI` interface for decoupled communication between UI widgets and game logic

### ⚙️ Settings Menu
- **Graphics Quality Presets** — Fully functional quality settings with **Low**, **Medium**, **High**, and **Ultra** presets that apply real Scalability Group changes at runtime
- **Gamma / Brightness Control** — Slider-based gamma adjustment for player comfort
- **Difficulty Selection** — Dropdown-based difficulty picker with named presets
- **Resolution & Display Options** — Dropdown combo boxes for screen resolution and display mode
- **Interactive Dropdowns (Combo Boxes)** — Custom-styled dropdown selectors with hover and click audio responses
- **Sliders with Audio Feedback** — Value sliders that provide audio cues on interaction
- **Apply Settings Button** — Dedicated apply button that commits all changes, ensuring settings are only saved when the player confirms

### 🌍 3D Environment Backdrop
- **Modular Sci-Fi Mechanic Base** — A full environment assembled from modular sci-fi structural pieces, pipes, cables, props, and landscape elements
- **Sicka Environment Packs** — Additional environmental detail from Sicka Sci-Fi Interior, Sicka Sci-Fi Interior 2, and Sicka Ancient Kit asset packs, adding depth and visual variety
- **Paragon Twinblast Character** — The iconic dual-pistol hero stands in the menu scene with a full **Animation Blueprint**, idle animations, and select-screen poses
- **VFX & Particles** — Dust particle systems (`NS_DUST`) and Twinblast FX bring atmospheric depth to the scene
- **Cinematic Lighting** — Carefully authored lighting with Lumen Global Illumination, Virtual Shadow Maps, and local exposure tuning for a dramatic, moody aesthetic

### 🎧 Audio
- **Menu Ambient Sound** — Background music/ambience (`MenuSound`) that plays while the menu is active
- **UI Interaction Sounds** — Distinct hover and click sound effects across all interactive elements

### 📱 Input Support
- **Mouse & Keyboard** — Full desktop input with Enhanced Input System (`IMC_Default`, `IMC_MouseLook`)
- **Touch Interface** — Touch input support via `BPI_TouchInterface`, on-screen thumbstick, and simplified touch UI widgets

---

## 📸 Screenshots

<table>
  <tr>
    <td align="center"><b>Logo</b></td>
    <td align="center"><b>Splash Screen</b></td>
  </tr>
  <tr>
    <td><img src="Screenshots/Logo.png" alt="ShooterGameUI Logo" width="100%"></td>
    <td><img src="Screenshots/Splash Screen.png" alt="Splash Screen" width="100%"></td>
  </tr>
</table>

<!-- Add future screenshots below in 2-column rows:
<table>
  <tr>
    <td align="center"><b>Caption 1</b></td>
    <td align="center"><b>Caption 2</b></td>
  </tr>
  <tr>
    <td><img src="Screenshots/your_image_1.png" alt="Description" width="100%"></td>
    <td><img src="Screenshots/your_image_2.png" alt="Description" width="100%"></td>
  </tr>
</table>
-->

---

## 📁 Project Structure

```
ShooterGameUI/
├── Config/
│   ├── DefaultEngine.ini          # Renderer, RHI, Lumen, ray tracing, scalability
│   ├── DefaultGame.ini            # Game configuration
│   └── DefaultInput.ini           # Input bindings & Enhanced Input config
│
├── Content/
│   ├── Blueprints/
│   │   ├── GameMode/
│   │   │   └── BP_ShooterGameMode         # Custom Game Mode (menu entry point)
│   │   ├── Interfaces/
│   │   │   └── BPI_UI                     # Blueprint Interface for UI communication
│   │   └── UI/
│   │       ├── BP_MainMenu                # Main Menu actor blueprint
│   │       ├── WBP_MainMenu               # Main Menu UMG widget (buttons, animations)
│   │       └── WBP_SettingsMenu           # Settings Menu UMG widget (sliders, dropdowns)
│   │
│   ├── Characters/
│   │   └── Mannequins/                    # Default UE5 mannequin assets
│   │
│   ├── FirstPerson/
│   │   ├── Anims/                         # First-person animation assets
│   │   ├── Blueprints/                    # First-person blueprint logic
│   │   └── Lvl_FirstPerson.umap           # First-person test level
│   │
│   ├── Fonts/
│   │   ├── Coalition_v2_                  # Coalition v2 font (main headings)
│   │   └── Michroma-Regular               # Michroma font (body/UI text)
│   │
│   ├── Input/
│   │   ├── Actions/
│   │   │   ├── IA_Jump                    # Jump input action
│   │   │   ├── IA_Look                    # Camera look input action
│   │   │   ├── IA_MouseLook              # Mouse-specific look action
│   │   │   └── IA_Move                    # Movement input action
│   │   ├── IMC_Default                    # Default Input Mapping Context
│   │   ├── IMC_MouseLook                  # Mouse look Input Mapping Context
│   │   └── Touch/
│   │       ├── BPI_TouchInterface         # Touch interface blueprint
│   │       ├── UI_Thumbstick              # On-screen thumbstick widget
│   │       └── UI_TouchSimple             # Simplified touch UI widget
│   │
│   ├── Levels/
│   │   ├── Lvl_MainMenu.umap             # Main menu level (lightweight)
│   │   ├── Lvl_Menu.umap                 # Full menu level with 3D environment
│   │   └── Lvl_Menu_BuiltData.uasset     # Pre-built lighting data
│   │
│   ├── Modular_Scifi_Mechanic_Base/       # 🏗️ Modular sci-fi environment kit
│   │   ├── BP/                            # Environment blueprints
│   │   ├── Material/ (MF, MI, MM)         # Material functions, instances, masters
│   │   ├── Mesh/SM/                       # Static meshes (structures, cables, props)
│   │   ├── Texture/                       # Environment textures
│   │   ├── VFX/                           # Dust particles (NS_DUST, FXS_DUST)
│   │   └── Map/                           # Demo map
│   │
│   ├── ParagonTwinblast/                  # 🦸 Hero character assets
│   │   ├── Characters/Heroes/TwinBlast/
│   │   │   ├── Animations/ (211 anims)    # Full animation set (idle, combat, emotes)
│   │   │   ├── TwinblastPlayerCharacter   # Player character blueprint
│   │   │   ├── Twinblast_AnimBlueprint    # Animation Blueprint with state machine
│   │   │   ├── Materials/                 # Character materials & shaders
│   │   │   ├── Meshes/                    # Skeletal & static meshes
│   │   │   ├── Skins/                     # Character skin variants
│   │   │   ├── Sounds/                    # Character audio
│   │   │   └── Textures/                  # Character textures
│   │   └── FX/                            # Character particle effects
│   │
│   ├── Sicka_EnvPack2/                    # 🏛️ Additional environment kits
│   │   ├── Sicka_Ancient_Kit/             # Ancient-themed meshes & materials
│   │   ├── Sicka_Scifi_Interior/          # Sci-fi interior set 1
│   │   └── Sicka_Scifi_Interior2/         # Sci-fi interior set 2 (+ holograms)
│   │
│   └── Sounds/
│       └── MenuSound                      # Menu background music / ambience
│
├── ShooterGameUI.uproject                 # Project descriptor (UE 5.6)
└── .gitignore                             # Git ignore rules
```

---

## 🔧 Technical Details

| Feature | Implementation |
|---|---|
| **Engine** | Unreal Engine 5.6 |
| **Rendering API** | DirectX 12 (SM6) |
| **Global Illumination** | Lumen (Dynamic GI) |
| **Reflections** | Lumen Reflections |
| **Shadows** | Virtual Shadow Maps |
| **Ray Tracing** | Enabled (hardware RT support) |
| **Lighting** | Fully dynamic (no static/precomputed lighting) |
| **Input System** | Enhanced Input (Input Actions + Mapping Contexts) |
| **UI Framework** | UMG (Unreal Motion Graphics) |
| **Scripting** | 100% Blueprint Visual Scripting |
| **Plugins** | ModelingToolsEditorMode, GameplayStateTree |
| **Target Hardware** | Desktop (Maximum quality preset) |

### Renderer Configuration

The project is configured for maximum visual fidelity:

- **Lumen GI & Reflections** for real-time bounce lighting and screen-space reflections
- **Virtual Shadow Maps** for high-resolution, per-pixel shadow detail
- **Ray Tracing** enabled with RT proxies for enhanced reflections and shadows
- **Mesh Distance Fields** generated for Lumen and ambient occlusion
- **Local Exposure** tuned (highlight & shadow contrast at 0.8) for cinematic contrast
- **Auto Exposure** with extended luminance range for HDR scene support
- **Skin Cache Shaders** compiled for high-quality character skin rendering
- **First-person self-shadowing** enabled for added visual depth

---

## 📦 Asset Packs Used

| Asset Pack | Usage |
|---|---|
| **Paragon: Twinblast** | Hero character model, 211+ animations, Animation Blueprint, FX, materials, and skins |
| **Modular Sci-Fi: Mechanic Base** | Core environment kit — modular structures, cables/pipes, props, landscape elements, materials, and dust VFX |
| **Sicka Environment Pack 2** | Supplementary environment detail — Sci-Fi Interior 1 & 2 (including holograms), Ancient Kit |
| **UE5 Mannequins** | Default character mannequins (reference/prototyping) |
| **Level Prototyping** | Blockout meshes, interactables, and prototyping materials |

---

## 🚀 Getting Started

### Prerequisites

- **Unreal Engine 5.6** (installed via Epic Games Launcher)
- **Windows 10/11** with DirectX 12 compatible GPU
- **GPU with Ray Tracing support** (recommended for full visual quality)
- Minimum **8 GB VRAM** recommended for Ultra quality settings

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/Prasham-Desai/ShooterGameUI.git
   ```

2. **Open the project**
   - Launch Unreal Engine 5.6
   - Open `ShooterGameUI.uproject`
   - Wait for shaders to compile on first launch (this may take several minutes)

3. **Play the menu**
   - The project defaults to `Lvl_Menu` as the startup map
   - Press **Play in Editor (PIE)** or **Standalone Game** to experience the full menu
   - The custom `BP_ShooterGameMode` is set as the global default Game Mode

### Build (Optional)

```bash
# Package for Windows (from UE5 Editor)
# Platforms > Windows > Package Project
```

---

## 🎮 Controls & Interaction

| Input | Action |
|---|---|
| **Mouse Hover** | Highlights buttons with visual feedback + plays hover sound |
| **Mouse Click** | Activates menu item + plays click sound |
| **Touch Tap** | Same as mouse click (touch-enabled devices) |
| **Touch Drag** | Virtual thumbstick navigation (if applicable) |
| **Dropdown Click** | Opens combo box options with audio feedback |
| **Slider Drag** | Adjusts value (gamma, volume, etc.) with audio cue |
| **Apply Settings** | Commits all changed settings to the engine |

---

## ⚙️ Configuration

### Graphics Quality Presets

The settings menu applies real Unreal Engine Scalability Groups:

| Preset | Description |
|---|---|
| **Low** | Reduced draw distance, simplified shadows, lower texture resolution, minimal post-processing |
| **Medium** | Balanced quality and performance with moderate shadow quality and textures |
| **High** | High-quality shadows, textures, and post-processing with full draw distance |
| **Ultra** | Maximum quality — Lumen GI at full resolution, Virtual Shadow Maps, ray tracing, maximum draw distance |

### Engine Settings

Key rendering settings can be found in [`DefaultEngine.ini`](Config/DefaultEngine.ini):

- `r.DynamicGlobalIlluminationMethod=1` — Lumen GI
- `r.ReflectionMethod=1` — Lumen Reflections
- `r.Shadow.Virtual.Enable=1` — Virtual Shadow Maps
- `r.RayTracing=True` — Hardware ray tracing
- `DefaultGraphicsRHI=DefaultGraphicsRHI_DX12` — DirectX 12

---

## 🗺️ Level Map

| Level | Purpose |
|---|---|
| `Lvl_Menu` | **Primary menu level** — Full 3D environment with character, lighting, VFX, and the UMG menu overlay |
| `Lvl_MainMenu` | Lightweight menu level variant |
| `Lvl_FirstPerson` | First-person gameplay test level |
| `Map` | Additional map asset |

The default startup map is set to `Lvl_Menu` in both the editor and packaged builds.

---

## 📝 License

This project is for **educational and portfolio purposes**. Asset packs (Paragon Twinblast, Modular Sci-Fi, Sicka Environment Pack) are subject to their respective licenses from the Unreal Engine Marketplace and Epic Games.

---

<div align="center">

**Built with ❤️ in Unreal Engine 5.6**

*Main Menu • Settings System • Environment Art • UI/UX Design*

</div>
