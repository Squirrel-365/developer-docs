---
description: Used for communication to and from Squirrel
---

# SquirrelMessage

```typescript
export class SquirrelMessage {
    name: string;
    id?: string;
    value: any;

    constructor(id: string | null, name: string | null, value: string | null | any[]) {
        if (id != null) { this.id = id; }
        if (name != null) { this.name = name; }
        if (value != null) { this.value = value; }
    }
}
```

