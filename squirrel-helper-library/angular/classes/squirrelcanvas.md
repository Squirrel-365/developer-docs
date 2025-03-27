---
description: Used to reflect the x and y position of the component on the Squirrel canvas.
---

# SquirrelCanvas



```typescript
export class SquirrelCanvas {
    size: SquirrelSize;
    color: SquirrelColor;

    constructor(size: SquirrelSize, color: SquirrelColor) {
        if (size != null) { this.size = size; }
        if (color != null) { this.color = color; }
    }
}
```

