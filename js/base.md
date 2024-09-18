**js多维对象数组内删除内部指定对象**
```js
function handleData(array) {
    return array.reduce((prev, item, index) => {
        if (item.children.length == 0) {
            delete item.children
        }
        prev[index] = item
        if (item.children) {
            prev[index].children = handleData(item.children)
        }
        return prev
    }, [])
}
```