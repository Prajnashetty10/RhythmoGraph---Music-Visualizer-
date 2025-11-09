# 🎵Rhythmograph-- Music Visualizer

A real-time audio visualization application built with Python that transforms music into stunning visual displays. Features multiple visualization modes including geometric shapes, graphs, Klein bottles, and 4D tesseract projections.



## ✨ Features

- **Real-time Audio Processing**: Uses librosa for advanced audio analysis
- **Multiple Visualization Modes**: 9 different visualization types
- **Interactive Controls**: Switch between visualizers on-the-fly
- **Resizable Window**: Adaptive display that scales with window size
- **Audio Controls**: Play, pause, and loop functionality

### Visualization Types

| Key | Visualizer | Description |
|-----|------------|-------------|
| `R` | Rectangle | Pulsating rectangle based on audio amplitude |
| `C` | Circle | Filled circle that grows/shrinks with the beat |
| `O` | Circle Outline | Outlined circle visualization |
| `L` | Line | Horizontal lines extending from center |
| `P` | Point Graph | Real-time point plotting (experimental) |
| `G` | Line Graph | Continuous waveform display |
| `K` | Klein Bottle | Mathematical Klein bottle scaling |
| `S` | Changing Shapes | Auto-switching between visualizations |
| `T` | Tesseract | 4D hypercube projection with rotation |

## 🚀 Quick Start

### Prerequisites

- Python 3.7+
- Audio file (MP3, WAV, etc.)

### Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd MusicVisualizer
   ```

2. **Install dependencies**
   ```bash
   pip install arcade librosa numpy scipy
   ```

3. **Run the visualizer**
   ```bash
   python music_visualizer.py
   ```

## 🎮 Controls

### Keyboard Shortcuts

- **ESC** - Exit the application
- **SPACE** - Pause/Resume playback
- **R** - Rectangle visualizer
- **C** - Circle visualizer
- **O** - Circle outline visualizer
- **L** - Line visualizer
- **P** - Point graph visualizer
- **G** - Line graph visualizer
- **K** - Klein bottle visualizer
- **S** - Changing shapes mode
- **T** - Tesseract (4D hypercube) visualizer

## ⚙️ Configuration

### Changing the Audio File

Edit the `SONG` variable in `music_visualizer.py`:

```python
SONG = "path/to/your/audio/file.mp3"
```

### Default Visualizer

Change the default visualizer in the `main()` function:

```python
music_visualizer = Visualizer(default=TESSERACT)  # Change to any visualizer constant
```

### Window Settings

Modify display settings:

```python
DEFAULT_WIDTH = 1100    # Window width
DEFAULT_HEIGHT = 700    # Window height
FPS = 60               # Refresh rate
```

## 🛠️ Technical Details

### Dependencies

- **arcade**: Graphics and window management
- **librosa**: Audio processing and analysis
- **numpy**: Numerical computations
- **scipy**: Signal processing (Savitzky-Golay filter)

### Audio Processing

The visualizer uses:
- Librosa for audio loading and analysis
- Savitzky-Golay filter for signal smoothing
- Real-time amplitude extraction for visualization scaling

### 4D Tesseract Visualization

The tesseract visualizer projects a 4D hypercube through multiple dimensional reductions:
1. 4D rotation in XY and ZW planes
2. 4D to 3D projection
3. 3D rotation
4. 3D to 2D projection for display

## 📁 Project Structure

```
MusicVisualizer/
├── music_visualizer.py    # Main application
├── playground.py          # Development/testing file
├── README.md             # This file
└── media/
    ├── Klein_bottle.png   # Klein bottle sprite
    ├── Klein_bottle.svg   # Vector version
    └── memphis-trap-wav-349366.mp3  # Sample audio
```

## 🎨 Adding New Visualizers

1. **Define a constant** in the options section
2. **Add keyboard mapping** in `on_key_press()`
3. **Create update logic** in `on_update()`
4. **Implement draw function** and add to `on_draw()`
5. **Update this README**

Example:
```python
# 1. Add constant
NEW_VISUALIZER = "new_viz"

# 2. Add key mapping
elif key == arcade.key.N:
    self.option = NEW_VISUALIZER

# 3. Add to on_draw()
elif self.option == NEW_VISUALIZER:
    self.draw_new_visualizer()

# 4. Implement draw function
def draw_new_visualizer(self):
    # Your visualization code here
    pass
```

## 🤝 Contributing

Contributions are welcome! Feel free to:
- Add new visualization modes
- Improve audio processing
- Enhance the user interface
- Fix bugs or optimize performance

## 📄 License

This project is open source. Please check the repository for license details.

---

**Enjoy the visual music experience! 🎶✨**
