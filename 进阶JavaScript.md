## 1.根据css选择器来获取DOM元素

### 1.选择匹配第一个元素

```javascript
document.querySelector(`css选择器`)
```

### 2.选择匹配多个元素

```javascript
document.querySelectorAll(`css选择器`)
```

## 2.操作元素内容

### 1，元素innerText属性

将文字内容添加/更新到任意标签

显示纯文本，不解析标签

```javascript
    <div class="box">我是文字内容</div>
    <script>
        //1.获取元素
        const box = document.querySelector(`.box`)
        //2.修改文字内容 对象.innerText属性
        console.log(box.innerText);//获取文字内容
        box.innerText = `文字内容2` //修改文字内容
    </script>
```

### 2,元素innerHTML属性

将文字内容添加/更新到任意标签

会解析标签，多标签建议使用模板字符

```javascript
    <div class="box">我是文字内容</div>
    <script>
        //1.获取元素
        const box = document.querySelector(`.box`)
        //2.修改文字内容 对象.innerText属性
        console.log(box.innerText);//获取文字内容
        box.innerHTML = `<strong>文字内容2</strong>`
        //修改文字内容,加粗字体
    </script>
```

## 3.操作元素属性

### 1.操作元素常用属性

通过JS设置/修改标签元素属性

常见的属性：href,title,src等

```javascript
对象.属性 = 值
//获取元素
const pic = document.querySelector(`img`)
//操作元素
pic.src = `./images/b02.jpg`
pic.title = `刘德华黑马演唱会`
```

### 2.操作元素样式属性

#### 1.通过style属性操作css

```javascript
对象.style.样式属性 = 值

<style>
    .box{
        width: 200px;
        height: 200px;
        background-color: blue;
    }
</style>
<body>
    <div class="box"></div>
    <script>
        const box = document.querySelector(`.box`)
        box.style.width = `400px`
        box.style.backgroundColor = `pink`//如果中间有横杠链接采用小驼峰命名法
        box.style.border = `2px solid blue`
    </script>
```

### 2.操作类名（className）操作CSS

```javascript
//active 是一个css类名
元素.className = `active`
```

### 3.通过classList操作类控制CSS

```javascript
//追加一个类
元素.classList.add(`类名`)
//删除一个类
元素.classList.remove(`类名`)
//切换一个类
元素.classList.toggle(`类名`)
```

## 4.操作表单元素

### 1.操作表单

```javas
表单.value = `用户名`
表单.type = `password`
```

### 2.操作checked(复选框)

```javascript
<input type="checkbox" checked>
    <script>
    //获取表单
     	const ipt = document.querySelector(`input`)
//修改表单中checked中的值（true时为勾选状态，false时不选中）
		ipt.checked = true
	</script>
```

### 3.disabled按钮

```javascript
 <button disabled>点击</button>

 // 1.获取
        const but = document.querySelector(`button`)
//disabled默认属性为false（按钮可以点击）
//	当disabled属性为true时（按钮无法点击）
        but.disabled = false
```

## 5.自定义标签

```html
//（data-** = 名） 为开头的都是自定义标签
<div data-id="1">1</div>
```

## 6.定时器-间接函数

作用：每个一段时间调用这个函数

间隔时间单位是毫秒

### 打开定时器：

```javascript
setInterval(函数,间隔时间)
//实例		
		function a1(){
           console.log(`打印1次`);
        }
		setInterval(a1,1000)
```

### 关闭定时器：

```javascript
let 变量名 = setInterval(函数,间隔时间)
clearInterval(变量名)
//实例
        function a2(){
            console.log(`打印1次`);           
        }
        let time = setInterval(a2,1000)
        //关闭定时器
        clearInterval(time)
```

## 7.事件监听

### 语法

```javascript
元素对象.addEventListener(`事件类型`,要执行的函数)
```

### 事件监听三要素：

事件源：哪个dom元素被事件触发了，就获取哪个dom元素

事件类型：用什么方式触发：比如鼠标点击(click)，鼠标经过(mouseover)

事件调用的函数：要做什么事
