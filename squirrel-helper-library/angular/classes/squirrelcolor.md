---
description: Used to reflect the x and y position of the component on the Squirrel canvas.
---

# SquirrelColor



```typescript
export class SquirrelColor {
    color: string;
    alpha: number;

    constructor(color: string, alpha: number) {
        if (color != null) { this.color = color; }
        if (alpha != null) { this.alpha = alpha; }
    }
}
```

