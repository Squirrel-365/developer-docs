---
description: onSetSize(e)
---

# onSetSize

```typescript
onSetSize(e){
 const size = e.detail.size;
}
```

Called when a setSize event is received from Squirrel. The size object of type [SquirrelSize ](../classes/squirrelsize.md)is passed into this callback.  If you need to get the size of the component at any time you can call the [getSize()](../methods/getsize.md) method,

The event could either be called when the component is manually resized by the resize handles in Squirrel, or when the height / width is updated via a spreadsheet binding or property change.

If you super the base class onSetSize method then it will add debug logs to your output

\


\
