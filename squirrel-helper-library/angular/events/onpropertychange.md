---
description: 'onPropertyChange(property: string, value: any): void'
---

# onPropertyChange

```typescript
override onPropertyChange(property: string, value: any): void{
  super.onSetSize(property, value);
}
```

Called whenever a property value has changed in Squirrel, state is automatically updated to reflect the new value and this callback is designed to allow you to process that change if needed. The full [dot notation](../../dot-notation.md) name of the property is provided as well as the new, incoming, value.

If you super the base class onPropertyChange method then it will add debug logs to your output

\


\
