**vue2生命周期**
```js
// 创建前
beforeCreate(){
    console.log('创建实例之前')
}
// 创建后
created(){
    console.log('创建实例之后')
}
// 挂载前
beforeMount(){
    console.log('挂载实例之前')
}
// 挂载后
mounted(){
    console.log('挂载实例之后')
}
// 更新前
beforeUpdate(){
    console.log('更新实例之前')
}
// 更新后
updated(){
    console.log('更新实例之后')
}
// 销毁前
beforeDestroy(){
    console.log('销毁实例之前')
}
// 销毁后
destroyed(){
    console.log('销毁实例之后')
}
```
**vue3生命周期**
```js
// 挂载前
onBeforeMount(){
    console.log('挂载实例之前')
}
// 挂载后
onMounted(){
    console.log('挂载实例之后')
}
// 更新前
onBeforeUpdate(){
    console.log('更新实例之前')
}
// 更新后
onUpdated(){
    console.log('更新实例之后')
}
// 销毁前
onBeforeUnmount(){
    console.log('销毁实例之前')
}
// 销毁后
unMounted(){
    console.log('销毁实例之后')
}
```