---
description: onSetCanvas(e)
---

# onSetCanvas

```typescript
onSetCanvas(e){
  const canvas = e.detail.canvas;
}
```

Called when a setCanvas event is received from Squirrel. This occurs when the canvas size or colour are updated.&#x20;

If you super the base class onSetPosition method then it will add debug logs to your output
