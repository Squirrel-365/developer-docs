---
description: >-
  Used to receive height and width information from Squirrel. This could be used
  for component size as well as binding size.
---

# SquirrelSize

```typescript
export class SquirrelSize {
    height: number;
    width: number;

    constructor(width: number, height: number) {
        if (width != null) { this.width = width; }
        if (height != null) { this.height = height; }
    }
}
```

