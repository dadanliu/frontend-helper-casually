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
```
