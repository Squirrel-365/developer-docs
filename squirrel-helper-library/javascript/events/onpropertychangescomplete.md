---
description: onPropertyChangesComplete()
---

# onPropertyChangesComplete

```typescript
onPropertyChangesComplete(){
}
```

Called when all individual [onPropertyChange ](onpropertychange.md)events have been sent. For example if something has happened in Squirrel which causes one or more bindings to be updated these individual bindings are sent as [onPropertyChange ](onpropertychange.md)events. This onPropertyChangesComplete event is executed at the end to advise all changes have been sent to the addon.

This can be very useful if you need to wait for all changes to be received before processing the changes to state.

If you super the base class onPropertyChangesComplete method then it will add debug logs to your output\
