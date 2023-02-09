# js

### change attr field to another
case
```js
let changedData = getReportRuleListData?.map((item:any)=>{
       let {children,...rest}=item;
       children=children?.map((item)=>{
         return {
           ...item,
           key:item.id
         }
       })
       return {...rest,child:children, key:item?.ruleId.toString()}})

// improved

arr.reduce( (acc, { children, ...rest }) => [...acc, { ...rest, child: children }], [] )

// ramda improved
import { map, compose, dissoc, assoc, prop, curry } from "ramda";
let a = [{ children: 1, t: "a" }];
let switchField = curry((fieldB, fieldA, item) => {
  return compose(
    dissoc(fieldB), 
    assoc(fieldA, prop(fieldB)(item))
  )(item);
});
let copyChildrenToChild = switchField("children", "child");
let b = map(copyChildrenToChild, a);
```

### css

```js
style={formData.noticeStatus?{}:{position:'relative',top:'-4px'}}
这里使用classname 那个包，去看看
classname({className:formData.noticeStatus},baseClassName)
```
