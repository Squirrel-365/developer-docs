---
description: onSetSize(e)
---

# onSetPosition

```typescript
onSetPosition(e){
  const position = e.detail.position;
}
```

Called when a setPosition event is received from Squirrel. The x and y coordinates of the component on the canvas is passed into this callback. If you need to get the position at any time you can call the [getPosition()](../methods/getposition.md) method,

The event is fired when ever the component's position is changed on the canvas.  This could be when the component is manually moved, or when the x / y property is updated via a spreadsheet binding or property change.

If you super the base class onSetPosition method then it will add debug logs to your output

\


\
