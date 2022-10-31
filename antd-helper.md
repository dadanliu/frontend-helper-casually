# and design helper

## Datepicker

```js
// 格式化 moment 为 后端需要的string 类型
// good case
<Item
  label='成交时间'
  required
  {/* 可以抽成统一的props */}
  normalize={value => {
    let ret = value?.format('YYYY-MM-DD hh:mm:ss')
    return ret
  }}
  getValueProps={(value) => {
    if (!value) return value
    return { value: moment(value) as unknown as any }
  }}
  >
  <DatePicker
    placeholder={"请选择成交时间"}
    style={{ width: 330 }}
    showTime
  />
</Item>

// bad case 
1. receive string time from request; do format, do set form value 
// ... component logic
2. do transfer to string; submit moment format; 
```
