# 正则表达式
## 模板解析
```js
const str = "我的名字叫:{{name}} {{age}}"
const data = {
    name : "thomaslok",
    age : 25
}
const function = (str,data) => {
    return str.replace(/{{(\w+)}}/g,(match,p1)=>{
        return data[p1]
    })
}
```
## - 转 驼峰命名
```js
function toCamel(str){
    return str.replace(/-(\w)/g,(match,p1)=>{
        return p1.toUpperCase()
    })
}
```
## 驼峰命名 转 -
```js
function fromCamel(str){
    return str.replace(/[A-Z]/g,(match)=>{
        return '-'+match.toLowerCase()
    })
}
```
## 数字分割
```js
const number = 123456789
function splitNumber(str){
    return str.replace(/(\d)(?=(\d{3})+$)/g,(match,p1)=>{
        return p1+"."
    })
}
```
## 解析url

```js
const url = "html?a=1&b=2"
function getURL(str){
    const obj = {};
    const reg = /([a-zA-Z0-9])=([a-zA-Z0-9])/g
    str.replace(reg,(match,p1,p2)=>{
        obj[p1] = p2
    })
    return obj
}
console.log(getURL('html?a=1&b=2'))
```

练习js正则表达式好用的网站：
https://regexlearn.com/zh-cn