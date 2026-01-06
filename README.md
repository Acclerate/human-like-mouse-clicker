# Human-Like Mouse Clicker

Human-like mouse click simulator for Windows 11 with Python 3.12 - simulates natural human clicking behavior with variable intervals and position offsets.

## Features

- **Human-like clicking**: Random intervals and position offsets to mimic natural human behavior
- **Multiple click types**: Single click, double click, triple click
- **Configurable**: Adjust intervals, offsets, and click duration
- **Interactive mode**: Command-line interface for manual operations
- **Demo mode**: Automatic demonstration of clicking behavior
- **Loop clicking**: Support for various loop click patterns

## Requirements

- Windows 11
- Python 3.12+
- pyautogui >= 0.9.54

## Installation

```bash
pip install -r requirements.txt
```

## Usage

### Interactive Mode

```bash
python human_click.py
```

Commands:
- `click x y [button]` - Click at position (x, y)
- `double x y` - Double click at position (x, y)
- `area x1 y1 x2 y2` - Random click in area
- `scroll n` - Scroll n times
- `pos` - Show current mouse position
- `quit` - Exit

### Demo Mode

```bash
python human_click.py --demo
```

### Configuration

Edit `human_click.py` or create a `ClickConfig` object:

```python
from human_click import ClickConfig, create_clicker

config = ClickConfig(
    min_interval=0.5,      # Min interval between clicks (seconds)
    max_interval=1.5,      # Max interval between clicks (seconds)
    min_x_offset=-10,      # Min X offset (pixels)
    max_x_offset=10,       # Max X offset (pixels)
    min_y_offset=-8,       # Min Y offset (pixels)
    max_y_offset=8,        # Max Y offset (pixels)
    click_duration=0.15    # Mouse movement duration (seconds)
)

clicker = create_clicker(config)
clicker.click(500, 500)
```

## Files

- `human_click.py` - Main module with HumanLikeMouseClicker class
- `loop_click_example.py` - Loop clicking examples
- `demo_double_click.py` - Triple click demonstration
- `test_config.py` - Configuration testing script
- `requirements.txt` - Dependencies

## License

MIT
