# How to write business block logic

```js
// bundle relate logic together
const page = () => {
    //... some logic
    
    const { runAsync } = useRequest(serviceA,options);
    const handleEvent = () => {
        //...logic
        runAsync(params)
    }
    const someReactElement = <Component onEvent={handleEvent} />
    
    return <>
        { someReactElement }
        //... react component
    </>
```
