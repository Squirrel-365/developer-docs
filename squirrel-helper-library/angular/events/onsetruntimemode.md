---
description: 'onSetRuntimeMode(mode: string): void'
---

# onSetRuntimeMode

```typescript
override onSetRuntimeMode(mode: string): void {
  super.onSetRuntimeMode(mode);
}
```

Called when a setRuntimeMode event is received from Squirrel. This can occur when switching bewteen Design, Debug and Preview.

A list of the available runtime modes can be found [here](../methods/getruntimemode.md)

If you super the base class onSetPosition method then it will add debug logs to your output
