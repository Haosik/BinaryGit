## В этом уроке мы продолжаем знакомиться с webpack 2. А именно: с подключением стилей и работе с ними.
***
Два самых базовый плагина для работы с css в webpack - это __css-loader__ и __style-loader__. 
Давайте установим их:


`npm install css-loader style-loader --save-dev`


__Style-loader__ нужен нам для инджекта стилей в _head_, а __css-loader__ для того, 
чтобы мы могли импортировать `css` в `js`.

Теперь добавим в наш _webpack.config.js_ новое правило для _css_ файлов:

```javascript
{
  test: /\.css$/,
  use: [
    'style-loader',
    'css-loader'
  ]
}
```

***
Обратите внимание, что в __webpack 2__ можно задавать несколько лоадеров в виде массива, что очень удобно. 
В __webpack 1__ мы разделяли их восклицательным знаком.

Давайте добавим папку `css` и файл `app.css` внутри:

```css
.container {
  background: green;
}
```

И импортируем наш css в app.js

```javascript
import './css/app.css'
```

Это позволяет нам строить такие же цепочки подключений _css_ к проекту, как и _js_.

По умолчанию, весь импортированный css попадает в глобальный скоуп в _head_. 
Давайте к `p` добавим класс `container`:

```css
<p class="container"></p>
```

Также напоминаю, что webpack можно запускать в watch режиме, с помощью команды `webpack -w`.


© <https://monsterlessons.com/project/lessons/webpack-2-nastraivaem-css>