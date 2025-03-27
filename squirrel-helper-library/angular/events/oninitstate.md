---
description: 'onInitState(state: any): void'
---

# onInitState

```typescript
override onInitState(state: any): void {
    super.onInitState(state);
}
```

This is the end of the initialisation handshake with Squirrel.  The initState event contains the following properties

1. a copy of state
2. the size of the component
3. the position of the component on the Squirrel canvas
4. the size and colour of the Squirrel canvas
   * introduced in release 1.12.x
5. the runtime mode (i.e. whether Squirrel is in Design, Debug, Preview or live)
   * introduced in release 1.12.x

You can get a copy of these properties by calling their corresponding get method

1. [getCopyOfState()](../methods/getcopyofstate.md)
2. [getSize()](../methods/getsize.md)
3. [getPosition()](../methods/getposition.md)
4. [getCanvas()](../methods/getcanvas.md)
5. [getRuntimeMode()](../methods/getruntimemode.md)

If you super the base class onInitState method then it will add debug logs to your output

\
