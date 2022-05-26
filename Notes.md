# Presentation


## Demos

### **Find text**

```python
import os

files = os.listdir()

for file in files:
    f = open(file, 'r')
    content = f.read()
    if "This one is the good one" in content:
        os.rename(file, "good.txt")
    f.close()
```

### **File nightmare**

```python
import os

files = os.listdir()

for file in files:
    name, extension = os.path.splitext(file)
    if name != "good":
        os.remove(file)
```

### **Asciimatics**

For last, I have one more demo for you guys. This is probably the least functional of all, but it's one of my favorites. Mainly because it is the one I had must fun doing.

```python 
from asciimatics.screen import Screen
from asciimatics.scene import Scene
from asciimatics.effects import Cycle, Stars
from asciimatics.renderers import FigletText

def thankYou(screen):
    effects = [
        Cycle(
            screen,
            FigletText("Q&A", font='big'),
            screen.height // 2 - 5),
        Stars(screen, (screen.width + screen.height) // 2)
    ]
    screen.play([Scene(effects, 500)])


Screen.wrapper(thankYou)
```