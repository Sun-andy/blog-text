# JS对象基本用法

### 一、声明对象的两种语法

第一种写法
```
let obj = { 'name': 'andy', 'age': 18 }
```
第二种写法
```
let obj = new Object({'name': 'andy'})
```
第一种是简单写法，比较常用，第二种是正规写法

注意：

* 对象都是以键值对的形式出现
* 键名是字符串，不是标识符，可以包含任意字符串
* 引号可以省略，省略之后只能按标识符的规则写（数字除外）
* 就算引号省略了，键名也还是字符串
* 当键名有空格，中文等特殊符号是，必须加引号，否则会出错

### 二、如何删除对象的属性

```
let obj = {
    name: 'andy',
    age: '18',
    gender: 'woman'
}
obj.name = undefined // 把 name 属性值设置为 undefined
delete obj.name // 删除属性
```
用delete obj.xxx 或 delete obj['xxx']，即可删除 obj 的 xxx 属性，上述代码中请区分「属性值为 undefined」和「不含属性名」

* 不含属性名
```
'xxx' in obj === false
```
可以用上面代码验证对象是否含有此属性

* 含有属性名，但值为undefined
```
'xxx' in obj && obj.xxx === undefined
//  obj.name === undefined 不能判断 name 是否为 obj 的属性，所以要做一个 && 运算
```
可以用上面代码验证含有属性且属性的值为 undefined

<h4>注意：把属性设置为 undefined 不是删除此属性，只是改变了属性的值，这个要和 delete 区分开</h4>

### 三、如何查看对象的属性

* 查看自身所有属性
```
let obj = {
    name: 'andy',
    age: 18
}
Object.keys(obj) // 查看所有键
Object.values(obj) // 查看所有值
Object.entries(obj) // 查看键和值
```

* 查看自身和共有属性
```
console.dir(obj)
Object.keys(obj.__proto__) // 不推荐用这种方法
```

* 判断一个属性是自身还是共有的
```
obj.hasOwnProperty('toString')
```
如果返回值为 false，那么这个属性就不是自身的属性。反之，返回 true 的话这个属性就是自身的属性

* 查看单个属性

```
中括号语法：obj['key'] //新手推荐使用
点语法：obj.key
坑新人语法：obj[key] // 变量 key 值一般不为 'key'
```
### 四、如何修改或增加对象的属性

<h4>增和改（写属性）</h4>

* 直接赋值
```
let obj = {
    'name': 'frank'
}
obj.name = 'andy' // 修改属性
obj.age = 13 // 增加属性
// 如果对象有此属性就为修改，没有此属性就为增加
```

* 批量赋值
```
let obj = {}
Object.assign( obj, {'name':'andy', 'age': '18'})
```

<h4>修改隐藏属性（原型）</h4>

1. 不推荐使用 __proto__
```
let obj = {name:'frank'}
let obj2 = {name: 'jack'}
let common = {kind: 'human'}
obj.__proto__ = common
obj2.__proto__ = common
```
2. 推荐使用 Object.create
```
let obj = Object.create(common)
obj.name = 'frank'
let obj2 = Object.create(common)
obj2.name = 'jack'
```
### 五、'name' in obj和obj.hasOwnProperty('name') 的区别

1. 'name' in obj： 'name'是obj的自身属性或者共有属性，都会返回true
2. 而obj.hasOwnProperty('name')： 只有在'name'为自身属性时才会返回true，共有属性会返回false




























