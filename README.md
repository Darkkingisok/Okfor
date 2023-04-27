# Okfor
Myanmarhacker
import os

# Define color codes
BLACK = '30'
RED = '31'
GREEN = '32'
YELLOW = '33'
BLUE = '34'
MAGENTA = '35'
CYAN = '36'
WHITE = '37'

# Define color themes
THEMES = {
    'default': {
        'foreground': WHITE,
        'background': BLACK
    },
    'monokai': {
        'foreground': GREEN,
        'background': BLACK
    },
    'ocean': {
        'foreground': CYAN,
        'background': BLUE
    }
}

# Set the default theme
current_theme = THEMES['default']

# Prompt the user to choose a theme
print('Choose a theme:')
for name in THEMES:
    print(f'- {name}')

chosen_theme = input('> ')
if chosen_theme in THEMES:
    current_theme = THEMES[chosen_theme]
else:
    print('Invalid theme name. Using default.')

# Set the color scheme
os.system(f'termux-color set {current_theme["foreground"]} {current_theme["background"]}')
