# js

### change target field to other field and remove target field
```js
let arr = [{ children: 1, t: "a" }];

// improved
arr.reduce( (acc, { children, ...rest }) => [...acc, { ...rest, child: children }], [] )

// ramda improved
import { map, compose, dissoc, assoc, prop, curry } from "ramda";

let switchField = curry((fieldB, fieldA, item) => {
  return compose(
    dissoc(fieldB), 
    assoc(fieldA, prop(fieldB)(item))
  )(item);
});
let copyChildrenToChild = switchField("children", "child");
let b = map(copyChildrenToChild, a);
```
