@fp51/store-devtools
=======================

Devtools for `@fp51/store`, a lightweight Javascript store library.

Use `@fp51/store-devtools` to debug your store with [ReduxDevtools
extension](https://github.com/zalmoxisus/redux-devtools-extension).

[📖 Documentation](https://fp51.github.io/store-library/packages/store-devtools/)

# Usage

```
npm install @fp51/store @fp51/store-devtools
```

`@fp51/store` is a peer-dependency

# Example

```typescript
import * as Store from '@fp51/store';
import { withDevtools } from '@fp51/store-devtools';

const store = withDevtools({
  name: 'my store',
})(Store.create(() => 2)());
```

Instead of classic `Redux` action type, it will try to use the reducer function
name to log the change.

```typescript
store.apply(
  function multiplyByTwo(state: number) {
    return state * 2;
  }
)();
```

Devtools will use `multiplyByTwo` as change type here.
