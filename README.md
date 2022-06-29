# README
# Stimulus 

Là một javasctript framework dùng để tích hợp vào rails dùng để thao tác Html Dom để ứng dụng có thêm tính tương tác

Cài đặt stimulus
```ruby
{
  yarn add stimulus
}
```
Tạo folder controller

>app/javascript/controllers 

Cấu hình stimulus 
> app/javascript/controllers/index.js

```js
{
  import { Application } from "stimulus"
  import { definitionsFromContext } from "stimulus/webpack-helpers"

  const application = Application.start(document.documentElement)
  const context = require.context('.', true, /_controller\.js$/)
  application.load(definitionsFromContext(context)) 
}
{
  require 'controller' là có thể sử dụng stimulus
}
```
Để xử lí ở ngoài views thì cần tạo thêm một controller abc_controller gì đó.
```js
{
  Muốn sử dụng controller đó thì: data-controler= "abc"
  Với "abc" chính là controller đã tạo trước đó
}
```
Ex:
```html
<div data-controller="abc">
  ..../
</div>
```
```js
static get targets(){
    return ['x', 'y']
  }
targets: là một mảng các target dùng để xử lí ngoài views
```
```js
Để tương tác với các element: data-action.
Cấu trúc
  >> data-action => keyup->abc#methodx
keyup: tên của sự kiện
abc: tên của controller
methodx: tên của phương thức sẽ xử lí sự kiện trong controller
```












