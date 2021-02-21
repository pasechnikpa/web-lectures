---
marp: true
html: true
size: 4:3
paginate: true
style: |
    body, p{font: Arial; font-weight: normal}
    *{margin-bottom: 0;}
    h1 {font-size:200%; margin-bottom: 0!important;line-height: 1}
    h2 {font-size:150%;}
    h3 {font-size:150%}
    p, li {font-size:140%; margin: 0}
    li li {font-size:100%}
    section::after {
        font-weight: bold; font-size: 45px;
    }
    pre, .code{border: 1px solid black; border-radius: 2px; margin-bottom: 2px; font-size: 26px; font-family: "Arial"}
    .code{padding: 10px 29px; font-weight: normal}
    .code p{font-size: 26px;}
    h5 strong{color: black!important; font-weight: 900;}
    .mt{margin-top:10px;}
---

# Тема 2. CSS (каскадные таблицы стилей)
— формальный язык описания внешнего вида документа, написанного с использованием языка разметки

---

# Преимущества
- централизованное управление отображением множества документов;
- упрощенный контроль внешнего вида веб-страниц;
- наличие разработанных дизайнерских техник;
- возможность использования различных стилей для одного документа, в зависимости от устройства.

---

# Общий вид CSS-правила

```CSS
селектор {
  свойство: значение;
  свойство: значение;
  свойство: значение;
}
селектор, селектор, селектор {
  свойство: значение;
}
```

---

# Селектор (selector)
это часть CSS-правила, которая сообщает браузеру, к какому элементу (или элементам) веб-страницы будет применён стиль

---

# Простейшие селекторы

Селектор "тег"
```css
div{}
```
Селектор "класс"
```css
.test{}
```
```html
<div class="test"></div>
```

---

# Основные единицы измерения

|Единица измерения|Обозначение
|---|---
|Пиксели|px
|Размер литеры 'm' текущего шрифта	|em
|Корневой em  |rem
|Процент от размера родительского элемента	|%
|0.01 ширины или высоты окна|vw, vh


---

# Единицы измерения

|Единица измерения|Обозначение
|---|---
|**Применяются для печати**
|Пункты, пики, сантиметры, миллиметры, дюймы	|pt, pc,cm, mm, in
|**Применяются редко**
|Размер литеры 'x' текущего шрифта, корневой	|ex, rex
|**Проблемы поддержки**
|0.01 от меньшей (большей) стороны  окна |vmin, vmax


---

# Цвет

- #00FF00
- #00FF007F
- rgb(0,255,0)
- green
- hsl(120,100%,100%)
- rgba(0,255,0,.5)
- hsla(120,100%,100%,0.1)
---

# Цвет

<strong>
<div style="color:green">

- green
- #00FF00
- rgb(0,255,0)
- hsl(120,100%,100%)

</div>
<div style="color:green;opacity:.7">

- #00FF007F
- rgba(0,255,0,.5)
- hsla(120,100%,100%,0.5)

</div>
</strong>

---

# **Блок** - блочный элемент разметки
**Блочный элемент** - элемент разметки, который обладает следующими свойствами:
- занимает всю ширину страницы
- не обтекается другими элементами
- имеет регулируемые размеры и отступы

---

# 2.1 Блочная модель
## 
<img style="width: 90vw; height: 60vw;" src="data:image/png;base64,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" />

---

# Простой способ подключения CSS

```html
<head>
    ...
    <style>
    .test{
        background-color: #cccccc;
    }
    </style>
    ...
</head>
<body>
    <div class="test">
        ZZZZZZ ZZZZZZZZ zzzzzzz zzzzzzz zzzz .test
    </div>
</body>
```

<style>
    .test{ 
        color: blue;
    }
</style>
<hr>

<div class="test">
ZZZZZZ ZZZZZZZZ zzzzzzz zzzzzzz zzzz .test
</div>

---

# Цвет фона background, <br> цвет текста color

```css
    .test{
        color: blue;
    }
```

<hr>

<div class="test">
ZZZZZZ ZZZZZZZZ zzzzzzz zzzzzzz zzzz .test
</div>

---

# Границы блока

```css
    .test{
        color: blue;
        border-style: solid;
    }
```

<hr>

<div style="
    color: blue;
    /* border-width: 4px; */
    border-style: solid;
">
ZZZZZZ ZZZZZZZZ zzzzzzz zzzzzzz zzzz .test
</div>

---

<div class="mt" style="border-style: dotted;">border-style: dotted;</div>
<div class="mt" style="border-style: dashed;">border-style: dashed;</div>
<div class="mt" style="border-style: double;">border-style: double;</div>
<div class="mt" style="border-style: groove;">border-style: groove;</div>
<div class="mt" style="border-style: ridge;">border-style: ridge;</div>
<div class="mt" style="border-style: inset ;">border-style: inset ;</div>
<div class="mt" style="border-style: outset;">border-style: outset;</div>

---

# Границы блока 1 значение

```css
    .test{
        color: blue;
        border-style: solid;
        border-color: red;
        border-width: 30px;
    }
```

<hr>

<div style="
    color: blue;
    /* border-width: 4px; */
    border-style: solid;
    border-color: red;
    border-width: 30px;
">
ZZZZZZ ZZZZZZZZ zzzzzzz zzzzzzz zzzz .test
</div>

---

# Границы блока 1 значение с указанием сторон

```css
    .test{
        color: blue;
        border-style: solid;
        border-color: red;
        border-left-width: 30px;
        border-right-width: 10px;
    }
```

<hr>

<div style="
    color: blue;
    /* border-width: 4px; */
    border-style: solid;
    border-color: red;
    border-left-width: 30px;
    border-right-width: 10px;
">
ZZZZZZ ZZZZZZZZ zzzzzzz zzzzzzz zzzz .test
</div>

---

# Несколько значений свойства для разных сторон

<div class="mt" style="
    color: blue;
    border-style: solid;
    border-color: red;
    border-width: 30px;
">
border-color: red;
</div>
<div class="mt" style="
    color: blue;
    border-style: solid;
    border-color: red green;
    border-width: 30px;
">border-color: red green;</div>
<div class="mt" style="
    color: blue;
    border-style: solid;
    border-color: red green blue;
    border-width: 30px;
">border-color: red green blue;</div>
<div class="mt" style="
    color: blue;
    border-style: solid;
    border-color: red green blue cyan;
    border-width: 30px;
">border-color: red green blue cyan;</div>

    Справедливо для других блочных свойств

---

# Сокращенная запись границ

```css
    .test{
        color: blue;
        border: 30px 2px solid red;
    }
```

<hr>

<div style="
    color: blue;
    border: 30px solid red;
">
ZZZZZZ ZZZZZZZZ zzzzzzz zzzzzzz zzzz .test
</div>

Не допускает нескольких значений для разных свойств, но можно заменить на border-left, border-right ...

---

<style>
    .border-2{
        color: blue;
    }
</style>
<div class="mt border-2" style="border-top: 30px solid red;">border-top: 30px solid red;</div>
<div class="mt border-2" style="border-right: 30px solid red;">border-right: 30px solid red;</div>
<div class="mt border-2" style="border-left: 30px solid red;">border-left: 30px solid red;</div>
<div class="mt border-2" style="border-bottom: 30px solid red;">border-bottom: 30px solid red;</div>

    Справедливо для других блочных свойств

---

# Внутренний отступ

```css
    .test{
        color: blue;
        border: 30px 2px solid red;
        padding: 40px 30px 10px;
    }
```

<div style="
    color: blue;
    border: 30px solid red;
    padding: 40px 30px 10px;
">
<span style="background: green;">ZZZZZZ ZZZZZZZZ zzzzzzz zzzzzzz zzzz .test</span>
</div>

    Зелёным цветом выделена область занимаемая текстом!!!
    Допустимы padding-left, padding-right ...

---

# Внешний отступ

```css
    .test{
        color: blue;
        border: 30px 2px solid red;
        padding: 40px 30px 10px;
        margin: 20px 30px;
    }
```

<div style="
    color: blue;
    border: 30px solid red;
        padding: 40px 30px 10px;
    margin: 5px 30px;
">
ZZZZZZ ZZZZZZZZ zzzzzzz zzzzzzz zzzz .test
</div>

    Также допустимы margin-left, margin-right ...

---

# Размеры

```css
    .test{
        color: blue;
        border: 30px 2px solid red;
        padding: 40px 30px 10px;
        margin: 20px 30px;
        width: 600px; 
        height: 300px;
    }
```

<div style="
    color: blue;
    border: 30px solid red;
        padding: 40px 30px 10px;
    margin: 5px 30px;
    width: 600px; height: 250px;
">
ZZZZZZ ZZZZZZZZ zzzzzzz zzzzzzz zzzz .test
</div>

---

# margin: X auto

```css
    .test{
        color: blue;
        border: 30px 2px solid red;
        padding: 40px 30px 10px;
        margin: 20px auto;
        width: 600px; 
        height: 300px;
    }
```

<div style="
    color: blue;
    border: 30px solid red;
        padding: 40px 30px 10px;
    margin: 5px auto;
    width: 600px; height: 250px;
">
ZZZZZZ ZZZZZZZZ zzzzzzz zzzzzzz zzzz .test
</div>

---

# Визуальный рамер элемента

<div class="mt" style="width:700px;background:#88ff88;box-sizing:content;">width: 700px;</div>
<div class="mt" style="width:700px;background:#88ff88;border:15px solid red;box-sizing:content-box;">width: 700px; border: 15px solid red;</div>
<div class="mt" style="width:700px;background:#88ff88;border:15px solid red;box-sizing:content-box;padding:15px;">width: 700px; border: 15px solid red; padding: 15px;</div>

---

# border-radius

```css
    .test{
        color: blue;
        border: 30px 2px solid red;
        padding: 40px 30px 10px;
        margin: 20px auto;
        width: 600px; 
        height: 300px;
        border-radius: 30px;
    }
```

<div style="
    color: blue;
    border: 30px solid red;
        padding: 40px 30px 10px;
    margin: 5px auto;
    width: 600px; height: 250px;
    border-radius: 31px;
">
ZZZZZZ ZZZZZZZZ zzzzzzz zzzzzzz zzzz .test
</div>

---

<style>
    .border-radius{
        color: blue;
        border: 40px solid red;
        padding: 10px;
        margin: 5px auto;
        width: 600px; 
    }
</style>
<div class="border-radius" style="border-radius: 31px;">border-radius: 30px;</div>
<div class="border-radius" style="border-radius: 60px;">border-radius: 60px;</div>
<div class="border-radius" style="border-radius: 30px 60px;">border-radius: 30px 60px;</div>
<div class="border-radius" style="border-top-left-radius: 30px 60px;">border-top-left-radius: 30px 60px;</div>

---


# overflow

```css
    .test{
        color: blue;
        border: 30px 2px solid red;
        padding: 40px 30px 10px;
        margin: 20px auto;
        width: 600px; 
        height: 170px;
        border-radius: 30px;
    }
```

<div style="
    color: blue;
    border: 30px solid red;
    padding: 40px 30px 10px;
    margin: 5px auto;
    width: 600px; height: 170px;
    border-radius: 31px;
">
без указания<br>
ZZZZZZ ZZZZZZZZ zzzzzzz zzzzzzz zzzz .test
</div>

---

<div style="
    color: blue;
    border: 30px solid red;
    padding: 40px 30px 10px;
    margin: 5px auto;
    width: 600px; height: 170px;
    border-radius: 31px;
    overflow: hidden;
">
overflow: hidden;<br>
ZZZZZZ ZZZZZZZZ zzzzzzz zzzzzzz zzzz .test
</div>

<div style="
    color: blue;
    border: 30px solid red;
    padding: 40px 30px 10px;
    margin: 5px auto;
    width: 600px; height: 170px;
    border-radius: 31px;
    overflow: scroll;
">
overflow: scroll;<br>
ZZZZZZ ZZZZZZZZ zzzzzzz zzzzzzz zzzz .test
</div>

<div style="
    color: blue;
    border: 30px solid red;
    padding: 40px 30px 10px;
    margin: 5px auto;
    width: 600px; height: 170px;
    border-radius: 31px;
    overflow: auto;
">
overflow: auto;<br>
ZZZZZZ ZZZZZZZZ zzzzzzz zzzzzzz zzzz .test
</div>

---

- visible - значение, используемое браузером по умолчанию
- scroll - добавляет к элементу полосы прокрутки по вертикали и горизонтали
- auto - добавляет полосы прокрутки при необходимости
- hidden - скрывает часть содержимого, которое выходит за границы блочного элемента

---

    overflow-x: scroll 

Добавляет пролосу прокрутки только для **горизонтальной** оси
 
    overflow-y: scroll 

Добавляет пролосу прокрутки только для **вертикальной** оси


---

# 2.2 Фоны

- background-color
- background-image
- background-repeat
- background-position

Применяется не только для блочных элементов

---

# background-color

```CSS
.test{
    background-color: #aaffaa;
    height: 200px;
}
```

<div style="background-color: #aaffaa;
    height: 200px;
">

---

# background-image

```CSS
.test{
    background-color: #aaffaa;
    background-image: url('images/2-logo.png');
    height: 200px;
    border: 1px solid green;
}
```

<div style="
    background-color: #aaffaa;
    background-image: url('images/2-logo.png');
    height: 200px;
    border: 1px solid green;
">

---

# background-repeat: repeat-x;

```CSS
.test{
    background-color: #aaffaa;
    background-image: url('images/2-logo.png');
    background-repeat: repeat-x;
    height: 200px;
    border: 1px solid green;
}
```

<div style="
    background-color: #aaffaa;
    background-image: url('images/2-logo.png');
    background-repeat: repeat-x;
    height: 200px;
    border: 1px solid green;
">

---

# background-repeat: repeat-y;

```CSS
.test{
    background-color: #aaffaa;
    background-image: url('images/2-logo.png');
    background-repeat: repeat-y;
    height: 200px;
    border: 1px solid green;
}
```

<div style="
    background-color: #aaffaa;
    background-image: url('images/2-logo.png');
    background-repeat: repeat-y;
    height: 200px;
    border: 1px solid green;
">

---

# background-repeat: no-repeat;

```CSS
.test{
    background-color: #aaffaa;
    background-image: url('images/2-logo.png');
    background-repeat: no-repeat;
    height: 200px; 
    border: 1px solid green;
}
```

<div style="
    background-color: #aaffaa;
    background-image: url('images/2-logo.png');
    background-repeat: no-repeat;
    height: 200px;
    border: 1px solid green;
">

---

# background-position

```CSS
.test{
    background-color: #aaffaa;
    background-image: url('images/2-logo.png');
    background-repeat: no-repeat;
    height: 200px; 
    border: 1px solid green;
    background-position: 50% 40px;
}
```

<div style="
    background-color: #aaffaa;
    background-image: url('images/2-logo.png');
    background-repeat: no-repeat;
    height: 200px;
    border: 1px solid green;
    background-position: 50% 40px;
">

---

# background-position

```CSS
.test{
    background-image: url('images/2-logo.png');
    background-repeat: no-repeat;
    height: 200px; 
    border: 1px solid green;
    background-position: bottom right;
}
```

<div style="
    background-color: #aaffaa;
    background-image: url('images/2-logo.png');
    background-repeat: no-repeat;
    height: 200px;
    border: 1px solid green;
    background-position: bottom right;
">

---

# background-size

```CSS
.test{
    background-color: #aaffaa;
    background-image: url('images/2-logo.png');
    background-repeat: no-repeat;
    height: 200px; 
    border: 1px solid green;
    background-position: bottom right;
}
```

<div style="
    background-color: #aaffaa;
    background-image: url('images/2-logo.png');
    background-repeat: no-repeat;
    height: 200px;
    border: 1px solid green;
    background-position: bottom right;
    background-size: 300px;
">

---

# background-size

```CSS
.test{
    background-color: #aaffaa;
    background-image: url('images/2-logo.png');
    background-repeat: no-repeat;
    height: 200px; 
    border: 1px solid green;
    background-position: bottom right;
    background-size: 300px 150px;
}
```

<div style="
    background-color: #aaffaa;
    background-image: url('images/2-logo.png');
    background-repeat: no-repeat;
    height: 200px;
    border: 1px solid green;
    background-position: bottom right;
    background-size: 300px 150px;
">

---

# background (сокращенная запись)

```CSS
.test{
    background: #aaffaa url('images/2-logo.png') 
            no-repeat bottom right;
    height: 200px; 
    border: 1px solid green;
    background-size: 200px;
}
```

<div style="
    background: #aaffaa url('images/2-logo.png') 
            no-repeat bottom right;
    height: 200px;
    border: 1px solid green;
    background-size: 200px;
">

---

# background (сокращенная запись)

```CSS
.test{
    background: url('images/2-logo.png') 
            no-repeat bottom right,
        url('images/2-logo.png') 
            no-repeat bottom left;
    height: 200px; 
    border: 1px solid green;
    background-size: 200px, 100px;
}
```

<div style="
    background: url('images/2-logo.png') 
            no-repeat bottom right,
        url('images/2-logo.png') 
            no-repeat bottom left;
    height: 200px;
    border: 1px solid green;
    background-size: 200px, 100px;
">


---

# background-attachment

- fixed - делает фоновое изображение элемента неподвижным.
- scroll - Позволяет перемещаться фону вместе с содержимым.
- local - Фон фиксируется с учётом поведения элемента. Если элемент имеет прокрутку, то фон будет прокручиваться вместе с содержимым, но фон выходящий за рамки элемента остаётся на месте.

---

# 2.3 Базовая работа с текстом
## "Красная строка"
```CSS
.test{
    background-color: #aaffaa;
    padding: 15px;
    text-indent: 50px;
}
```

<div style="
    background-color: #aaffaa;
    padding: 15px;
    text-indent: 50px;
">Стандартный вид текста не всегда подходит, как по внешнему виду, так и по цвету, CSS предоставляет обширные возможности, с помощью которых, вы можете кардинально изменить ваш текст, например задав ему цвет, меняя межстрочный интервал, расстояние между буквами или размер текста и многое другое.</div>

---

# Выключка

<div style="
    background-color: #aaffaa;
    padding: 15px;
    margin: 15px;
    text-align: right;
">
<strong>text-align: right; </strong>
Стандартный вид текста не всегда подходит, как по внешнему виду, ...</div>
<div style="
    background-color: #aaffaa;
    padding: 15px;
    margin: 15px;
    text-align: center;
"><strong>text-align: center;</strong> Стандартный вид текста не всегда подходит, как по внешнему виду,...</div>
<div style="
    background-color: #aaffaa;
    padding: 15px;
    margin: 15px;
    text-align: left;
"><strong>text-align: left;</strong> Стандартный вид текста не всегда подходит, как по внешнему виду, ...</div>
<div style="
    background-color: #aaffaa;
    padding: 15px;
    margin: 15px;
    text-align: justify;
"><strong>text-align: justify;</strong> Стандартный вид текста не всегда подходит, как по внешнему виду, ...</div>

---

# Размер и цвет
```CSS
.test{
    background-color: #aaffaa;
    padding: 15px;
    color:red;
    font-size: 50px;
}
```

<div style="
    background-color: #aaffaa;
    padding: 15px;
    color:red;
    font-size: 50px;
">Стандартный вид текста...</div>

---

# Тень
```CSS
.test{
    background-color: #aaffaa;
    padding: 15px;
    color:red;
    font-size: 50px;
    text-shadow: 5px 7px 3px #000;
}
```

<div style="
    background-color: #aaffaa;
    padding: 15px;
    color:red;
    font-size: 50px;
    text-shadow: 5px 7px 3px #000;
">Стандартный вид текста...</div>

- 5px - смещение вправо
- 7px - смещение вниз
- 3px - смещение размытие
- #000 - цвет
---

# Шрифт
```CSS
.test{
    background-color: #aaffaa;
    padding: 15px;
    color:red;
    font-size: 50px;
    font-family: 'Times New Roman', Times, serif;
}
```

<div style="
    background-color: #aaffaa;
    padding: 15px;
    color:red;
    font-size: 50px;
    font-family: 'Times New Roman', Times, serif;
">Стандартный вид текста...</div>

---

# Наборы шрифтов

- sans-serif - шрифты без засечек, считается что они лучше читаются на экране компьютера, чем шрифты семейства serif
- serif - семейство шрифтов с засечками
- monospace - моноширинные шрифты
- cursive - рукописные шрифты
- fantasy - художественные и декоративные шрифты

---

### Стиль шрифта

<div style="
    background-color: #aaffaa;
    padding: 15px;
    color:red;
    font-size: 50px;
    font-family: 'Times New Roman', Times, serif;
    font-style:italic;
">font-style:italic;</div>
<div style="
    background-color: #aaffaa;
    padding: 15px;
    color:red;
    font-size: 50px;
    font-family: 'Times New Roman', Times, serif;
    font-style:oblique ;
">font-style:oblique;</div>
<div style="
    background-color: #aaffaa;
    padding: 15px;
    color:red;
    font-size: 50px;
    font-family: 'Times New Roman', Times, serif;
    font-style:none;
">font-style:none;</div>

---

### Начертание шрифта

<div style="
    background-color: #aaffaa;
    padding: 15px;
    color:red;
    font-size:  40px;
    font-weight: normal;
">font-weight: normal; (по умолчанию)</div>
<div style="
    background-color: #aaffaa;
    padding: 15px;
    color:red;
    font-size:  40px;
    font-weight: bold;
">font-weight: bold;</div>
<div style="
    background-color: #aaffaa;
    padding: 15px;
    color:red;
    font-size:  40px;
    font-weight: 900;
">font-weight: 900;</div>
<div style="
    background-color: #aaffaa;
    padding: 15px;
    color:red;
    font-size:  40px;
    font-weight: 100;
">font-weight: 100;</div>

---

# Дополнительное оформление текста

<div style="
    background-color: #aaffaa;
    padding: 15px;
    color:red;
    font-size:  40px;
    text-decoration: none;
">text-decoration: none;</div>
<div style="
    background-color: #aaffaa;
    padding: 15px;
    color:red;
    font-size:  40px;
    text-decoration: underline;
">text-decoration: underline;</div>
<div style="
    background-color: #aaffaa;
    padding: 15px;
    color:red;
    font-size:  40px;
    text-decoration: line-through;
">text-decoration: line-through;</div>
<div style="
    background-color: #aaffaa;
    padding: 15px;
    color:red;
    font-size:  40px;
    text-decoration: overline;
">text-decoration: overline;</div>

---

# Регистр букв

<div style="
    background-color: #aaffaa;
    padding: 15px;
    color:red;
    font-size:  40px;
    text-transform: uppercase;
">text-transform: uppercase;</div>
<div style="
    background-color: #aaffaa;
    padding: 15px;
    color:red;
    font-size:  40px;
    text-transform: lowercase;
">text-transform: lowercase;</div>
<div style="
    background-color: #aaffaa;
    padding: 15px;
    color:red;
    font-size:  40px;
    text-transform: capitalize;
">text-transform: capitalize;</div>

---

## Высота строки (интервал)

```CSS
.test{
    
}
```
<p style="">
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
</p>

---

## Высота строки (интервал)
Множитель
```CSS
.test{
    line-height:2;
    
}
```
<p style="line-height:2;
    ">
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
</p>

---

## Высота строки (интервал)
В пикселях
```CSS
.test{
    line-height:100px;
    
}
```
<p style="line-height:100px;
    ">
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
</p>

---

## Ширина между символами

```CSS
.test{
    
}
```
<p style="">
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
</p>

---

## Ширина между символами

```CSS
.test{
    letter-spacing:2px;
    
}
```
<p style="letter-spacing:2px;
    ">
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
</p>

---

## Ширина между символами

```CSS
.test{
    letter-spacing:-1px;
    
}
```
<p style="letter-spacing:-1px;
    ">
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
</p>

---
#  2.4 Изменение расположения и взаимодействия объектов

---

```html
    <div class="container">
        <div class="block1">block1</div>
        <div class="block2">block2</div>
        <div class="block3">block3</div>
    </div>
```


<div>
    <div style="background:#cccccc;">
        <div style="width:120px;height:120px;background:green;">block1
        </div>
        <div style="width:150px;height:60px;background:blue;">block2
        </div>
        <div style="width: 300px;height:40px;background:yellow;">block3</div>
    </div>
</div>

---

<div style="display:flex;width: 100%;">

```css
.container{
    background:#cccccc;
}
.block1{
    width:120px; 
    height:120px; 
    background:green;
}
```

```CSS
.block2{
    width:150px;
    height:60px;
    background:blue;
}
.block2{
    width: 300px;
    height:40px;
    background:yellow;
}
```
</div>
<div>
    <div style="background:#cccccc;">
        <div style="width:120px;height:120px;background:green;">block1
        </div>
        <div style="width:150px;height:60px;background:blue;">block2
        </div>
        <div style="width: 300px;height:40px;background:yellow;">block3</div>
    </div>
</div>

---

## Обтекание

<div style="display:flex;width: 100%;">

```CSS
.block1{
    }
.block2{
    }
```

```CSS
.block3{
    }
.container{
    }
```

</div>
<div>
    <div style="background:#cccccc;">
        <div style="width:120px;height:120px;background:green;">block1
        </div>
        <div style="width:150px;height:60px;background:blue;">block2
        </div>
        <div style="width: 300px;height:40px;background:yellow;">block3</div>
    </div>
</div>

<div style="clear:both"></div>

---

## Обтекание
z-index не работает
<div style="display:flex;width: 100%;">

```CSS
.block1{
    float:left;
    }
.block2{
    }
```

```CSS
.block3{
    }
.container{
    }
```

</div>
<div>
    <div style="background:#cccccc;">
        <div style="width:120px;height:120px;background:green;float:left;
    ">block1
        </div>
        <div style="width:150px;height:60px;background:blue;">block2
        </div>
        <div style="width: 300px;height:40px;background:yellow;">block3</div>
    </div>
</div>

<div style="clear:both"></div>

---

## Обтекание

<div style="display:flex;width: 100%;">

```CSS
.block1{
    float:right;
    }
.block2{
    }
```

```CSS
.block3{
    }
.container{
    }
```

</div>
<div>
    <div style="background:#cccccc;">
        <div style="width:120px;height:120px;background:green;float:right;
    ">block1
        </div>
        <div style="width:150px;height:60px;background:blue;">block2
        </div>
        <div style="width: 300px;height:40px;background:yellow;">block3</div>
    </div>
</div>

<div style="clear:both"></div>

---

## Обтекание

<div style="display:flex;width: 100%;">

```CSS
.block1{
    float:left;
    }
.block2{
    float:left;
    }
```

```CSS
.block3{
    }
.container{
    }
```

</div>
<div>
    <div style="background:#cccccc;">
        <div style="width:120px;height:120px;background:green;float:left;
    ">block1
        </div>
        <div style="width:150px;height:60px;background:blue;float:left;
    ">block2
        </div>
        <div style="width: 300px;height:40px;background:yellow;">block3</div>
    </div>
</div>

<div style="clear:both"></div>

---

## Обтекание

<div style="display:flex;width: 100%;">

```CSS
.block1{
    float:left;
    }
.block2{
    float:left;
    }
```

```CSS
.block3{
    clear:both}
.container{
    }
```

</div>
<div>
    <div style="background:#cccccc;">
        <div style="width:120px;height:120px;background:green;float:left;
    ">block1
        </div>
        <div style="width:150px;height:60px;background:blue;float:left;
    ">block2
        </div>
        <div style="width: 300px;height:40px;background:yellow;clear:both">block3</div>
    </div>
</div>

<div style="clear:both"></div>

---

## Обтекание

<div style="display:flex;width: 100%;">

```CSS
.block1{
    float:right;
    }
.block2{
    clear:both;
    }
```

```CSS
.block3{
    }
.container{
    }
```

</div>
<div>
    <div style="background:#cccccc;">
        <div style="width:120px;height:120px;background:green;float:right;
    ">block1
        </div>
        <div style="width:150px;height:60px;background:blue;clear:both;
    ">block2
        </div>
        <div style="width: 300px;height:40px;background:yellow;">block3</div>
    </div>
</div>

<div style="clear:both"></div>

---

## Позиционирование

<div style="display:flex;width: 100%;">

```CSS
.block1{
    }
.block2{
    }
```

```CSS
.block3{
    }
.container{
    }
```

</div>
<div>
    <div style="background:#cccccc;">
        <div style="width:120px;height:120px;background:green;">block1
        </div>
        <div style="width:150px;height:60px;background:blue;">block2
        </div>
        <div style="width: 300px;height:40px;background:yellow;">block3</div>
    </div>
</div>

<div style="clear:both"></div>

---

## Позиционирование

<div style="display:flex;width: 100%;">

```CSS
.block1{
    position:relative;
    }
.block2{
    }
```

```CSS
.block3{
    }
.container{
    }
```

</div>
<div>
    <div style="background:#cccccc;">
        <div style="width:120px;height:120px;background:green;position:relative;
    ">block1
        </div>
        <div style="width:150px;height:60px;background:blue;">block2
        </div>
        <div style="width: 300px;height:40px;background:yellow;">block3</div>
    </div>
</div>

<div style="clear:both"></div>

---

## Позиционирование

<div style="display:flex;width: 100%;">

```CSS
.block1{
    position:relative;
    left: 20px;
    top:10px;
    }
.block2{
    }
```

```CSS
.block3{
    }
.container{
    }
```

</div>
<div>
    <div style="background:#cccccc;">
        <div style="width:120px;height:120px;background:green;position:relative;
    left: 20px;
    top:10px;
    ">block1
        </div>
        <div style="width:150px;height:60px;background:blue;">block2
        </div>
        <div style="width: 300px;height:40px;background:yellow;">block3</div>
    </div>
</div>

<div style="clear:both"></div>

---

## Позиционирование

<div style="display:flex;width: 100%;">

```CSS
.block1{
    position:relative;
    right: 20px;
    bottom:10px;
    }
.block2{
    }
```

```CSS
.block3{
    }
.container{
    }
```

</div>
<div>
    <div style="background:#cccccc;">
        <div style="width:120px;height:120px;background:green;position:relative;
    right: 20px;
    bottom:10px;
    ">block1
        </div>
        <div style="width:150px;height:60px;background:blue;">block2
        </div>
        <div style="width: 300px;height:40px;background:yellow;">block3</div>
    </div>
</div>

<div style="clear:both"></div>

---

## Позиционирование

<div style="display:flex;width: 100%;">

```CSS
.block1{
    position:absolute;
    }
.block2{
    }
```

```CSS
.block3{
    }
.container{
    }
```

</div>
<div>
    <div style="background:#cccccc;">
        <div style="width:120px;height:120px;background:green;position:absolute;
    ">block1
        </div>
        <div style="width:150px;height:60px;background:blue;">block2
        </div>
        <div style="width: 300px;height:40px;background:yellow;">block3</div>
    </div>
</div>

<div style="clear:both"></div>

---

## Позиционирование

<div style="display:flex;width: 100%;">

```CSS
.block1{
    position:absolute;
    left: 20px;
    top:10px;
    }
.block2{
    }
```

```CSS
.block3{
    }
.container{
    }
```

</div>
<div>
    <div style="background:#cccccc;">
        <div style="width:120px;height:120px;background:green;position:absolute;
    left: 20px;
    top:10px;
    ">block1
        </div>
        <div style="width:150px;height:60px;background:blue;">block2
        </div>
        <div style="width: 300px;height:40px;background:yellow;">block3</div>
    </div>
</div>

<div style="clear:both"></div>

---

## Позиционирование

<div style="display:flex;width: 100%;">

```CSS
.block1{
    position:absolute;
    right: 20px;
    bottom:10px;
    }
.block2{
    }
```

```CSS
.block3{
    }
.container{
    }
```

</div>
<div>
    <div style="background:#cccccc;">
        <div style="width:120px;height:120px;background:green;position:absolute;
    right: 20px;
    bottom:10px;
    ">block1
        </div>
        <div style="width:150px;height:60px;background:blue;">block2
        </div>
        <div style="width: 300px;height:40px;background:yellow;">block3</div>
    </div>
</div>

<div style="clear:both"></div>

---

## Позиционирование

<div style="display:flex;width: 100%;">

```CSS
.block1{
    position:absolute;
    right: 0;
    bottom:0;
    }
.block2{
    }
```

```CSS
.block3{
    }
.container{
    position:relative;
    }
```

</div>
<div>
    <div style="background:#cccccc;position:relative;
    ">
        <div style="width:120px;height:120px;background:green;position:absolute;
    right: 0;
    bottom:0;
    ">block1
        </div>
        <div style="width:150px;height:60px;background:blue;">block2
        </div>
        <div style="width: 300px;height:40px;background:yellow;">block3</div>
    </div>
</div>

<div style="clear:both"></div>

---

## Позиционирование

<div style="display:flex;width: 100%;">

```CSS
.block1{
    position:absolute;
    bottom:0;
    }
.block2{
    }
```

```CSS
.block3{
    }
.container{
    position:relative;
    }
```

</div>
<div>
    <div style="background:#cccccc;position:relative;
    ">
        <div style="width:120px;height:120px;background:green;position:absolute;
    bottom:0;
    ">block1
        </div>
        <div style="width:150px;height:60px;background:blue;">block2
        </div>
        <div style="width: 300px;height:40px;background:yellow;">block3</div>
    </div>
</div>

<div style="clear:both"></div>

---

## Позиционирование

<div style="display:flex;width: 100%;">

```CSS
.block1{
    position:fixed;
    }
.block2{
    }
```

```CSS
.block3{
    }
.container{
    }
```

</div>
<div>
    <div style="background:#cccccc;">
        <div style="width:120px;height:120px;background:green;position:fixed;
    ">block1
        </div>
        <div style="width:150px;height:60px;background:blue;">block2
        </div>
        <div style="width: 300px;height:40px;background:yellow;">block3</div>
    </div>
</div>

<div style="clear:both"></div>

---

## Позиционирование

<div style="display:flex;width: 100%;">

```CSS
.block1{
    position:scroll;
    }
.block2{
    }
```

```CSS
.block3{
    }
.container{
    }
```

</div>
<div>
    <div style="background:#cccccc;">
        <div style="width:120px;height:120px;background:green;position:scroll;
    ">block1
        </div>
        <div style="width:150px;height:60px;background:blue;">block2
        </div>
        <div style="width: 300px;height:40px;background:yellow;">block3</div>
    </div>
</div>

<div style="clear:both"></div>

---

## Наложение

<div style="display:flex;width: 100%;">

```CSS
.block1{
    position:relative;
    top:20px;
    }
.block2{
    position:relative;
    }
```

```CSS
.block3{
    }
.container{
    }
```

</div>
<div>
    <div style="background:#cccccc;">
        <div style="width:120px;height:120px;background:green;position:relative;
    top:20px;
    ">block1
        </div>
        <div style="width:150px;height:60px;background:blue;position:relative;
    ">block2
        </div>
        <div style="width: 300px;height:40px;background:yellow;">block3</div>
    </div>
</div>

<div style="clear:both"></div>

---

## Наложение

<div style="display:flex;width: 100%;">

```CSS
.block1{
    position:relative;
    top:20px;
    z-index:10;
    }
.block2{
    position:relative;
    }
```

```CSS
.block3{
    }
.container{
    }
```

</div>
<div>
    <div style="background:#cccccc;">
        <div style="width:120px;height:120px;background:green;position:relative;
    top:20px;
    z-index:10;
    ">block1
        </div>
        <div style="width:150px;height:60px;background:blue;position:relative;
    ">block2
        </div>
        <div style="width: 300px;height:40px;background:yellow;">block3</div>
    </div>
</div>

<div style="clear:both"></div>

---

## Видимость

<div style="display:flex;width: 100%;">

```CSS
.block1{
    visibility:hidden;
    }
.block2{
    }
```

```CSS
.block3{
    }
.container{
    }
```

</div>
<div>
    <div style="background:#cccccc;">
        <div style="width:120px;height:120px;background:green;visibility:hidden;
    ">block1
        </div>
        <div style="width:150px;height:60px;background:blue;">block2
        </div>
        <div style="width: 300px;height:40px;background:yellow;">block3</div>
    </div>
</div>

<div style="clear:both"></div>

---

## Свойства отображения

<div style="display:flex;width: 100%;">

```CSS
.block1{
    display: none;
    }
.block2{
    }
```

```CSS
.block3{
    }
.container{
    }
```

</div>
<div>
    <div style="background:#cccccc;">
        <div style="width:120px;height:120px;background:green;display: none;
    ">block1
        </div>
        <div style="width:150px;height:60px;background:blue;">block2
        </div>
        <div style="width: 300px;height:40px;background:yellow;">block3</div>
    </div>
</div>

<div style="clear:both"></div>

---

## Свойства отображения

<div style="display:flex;width: 100%;">

```CSS
.block1{
    display: inline-block;
    }
.block2{
    }
```

```CSS
.block3{
    }
.container{
    }
```

</div>
<div>
    <div style="background:#cccccc;">
        <div style="width:120px;height:120px;background:green;display: inline-block;
    ">block1
        </div>
        <div style="width:150px;height:60px;background:blue;">block2
        </div>
        <div style="width: 300px;height:40px;background:yellow;">block3</div>
    </div>
</div>

<div style="clear:both"></div>

---

## Свойства отображения. Flexbox
Flexbox
<div style="display:flex;width: 100%;">

```CSS
.block1{
    }
.block2{
    }
```

```CSS
.block3{
    }
.container{
    display: flex;
    }
```

</div>
<div>
    <div style="background:#cccccc;display: flex;
    ">
        <div style="width:120px;height:120px;background:green;">block1
        </div>
        <div style="width:150px;height:60px;background:blue;">block2
        </div>
        <div style="width: 300px;height:40px;background:yellow;">block3</div>
    </div>
</div>

<div style="clear:both"></div>

---

## Свойства отображения. Flexbox
Flexbox
<div style="display:flex;width: 100%;">

```CSS
.block1{
    }
.block2{
    }
```

```CSS
.block3{
    }
.container{
    display: inline-flex;
    }
```

</div>
<div>
    <div style="background:#cccccc;display: inline-flex;
    ">
        <div style="width:120px;height:120px;background:green;">block1
        </div>
        <div style="width:150px;height:60px;background:blue;">block2
        </div>
        <div style="width: 300px;height:40px;background:yellow;">block3</div>
    </div>
</div>

<div style="clear:both"></div>

---

## Свойства отображения. Flexbox
Направление
<div style="display:flex;width: 100%;">

```CSS
.block1{
    }
.block2{
    }
```

```CSS
.block3{
    }
.container{
    display: flex;
     flex-direction: row;
    }
```

</div>
<div>
    <div style="background:#cccccc;display: flex;
     flex-direction: row;
    ">
        <div style="width:120px;height:120px;background:green;">block1
        </div>
        <div style="width:150px;height:60px;background:blue;">block2
        </div>
        <div style="width: 300px;height:40px;background:yellow;">block3</div>
    </div>
</div>

<div style="clear:both"></div>

---

## Свойства отображения. Flexbox

<div style="display:flex;width: 100%;">

```CSS
.block1{
    }
.block2{
    }
```

```CSS
.block3{
    }
.container{
    display: flex;
     flex-direction: row-reverse;
    }
```

</div>
<div>
    <div style="background:#cccccc;display: flex;
     flex-direction: row-reverse;
    ">
        <div style="width:120px;height:120px;background:green;">block1
        </div>
        <div style="width:150px;height:60px;background:blue;">block2
        </div>
        <div style="width: 300px;height:40px;background:yellow;">block3</div>
    </div>
</div>

<div style="clear:both"></div>

---

## Свойства отображения. Flexbox

<div style="display:flex;width: 100%;">

```CSS
.block1{
    }
.block2{
    }
```

```CSS
.block3{
    }
.container{
    display: flex;
     flex-direction: column;
    }
```

</div>
<div>
    <div style="background:#cccccc;display: flex;
     flex-direction: column;
    ">
        <div style="width:120px;height:120px;background:green;">block1
        </div>
        <div style="width:150px;height:60px;background:blue;">block2
        </div>
        <div style="width: 300px;height:40px;background:yellow;">block3</div>
    </div>
</div>

<div style="clear:both"></div>

---

## Свойства отображения. Flexbox

<div style="display:flex;width: 100%;">

```CSS
.block1{
    }
.block2{
    }
```

```CSS
.block3{
    }
.container{
    display: flex;
     flex-direction: column-reverse;
    }
```

</div>
<div>
    <div style="background:#cccccc;display: flex;
     flex-direction: column-reverse;
    ">
        <div style="width:120px;height:120px;background:green;">block1
        </div>
        <div style="width:150px;height:60px;background:blue;">block2
        </div>
        <div style="width: 300px;height:40px;background:yellow;">block3</div>
    </div>
</div>

<div style="clear:both"></div>

---

## Свойства отображения. Flexbox
При нехватке места блоки равномерно уменьшается их ширина
<div style="display:flex;width: 100%;">

```CSS
.block1{
    }
.block2{
    }
```

```CSS
.block3{
    }
.container{
    display:flex;
    width:400px;
    }
```

</div>
<div>
    <div style="background:#cccccc;display:flex;
    width:400px;
    ">
        <div style="width:120px;height:120px;background:green;">block1
        </div>
        <div style="width:150px;height:60px;background:blue;">block2
        </div>
        <div style="width: 300px;height:40px;background:yellow;">block3</div>
    </div>
</div>

<div style="clear:both"></div>

---

## Свойства отображения. Flexbox
Режим переноса блоков
<div style="display:flex;width: 100%;">

```CSS
.block1{
    }
.block2{
    }
```

```CSS
.block3{
    }
.container{
    display:flex;
    width:400px;
    flex-wrap:wrap;
    }
```

</div>
<div>
    <div style="background:#cccccc;display:flex;
    width:400px;
    flex-wrap:wrap;
    ">
        <div style="width:120px;height:120px;background:green;">block1
        </div>
        <div style="width:150px;height:60px;background:blue;">block2
        </div>
        <div style="width: 300px;height:40px;background:yellow;">block3</div>
    </div>
</div>

<div style="clear:both"></div>

---

## Свойства отображения. Flexbox
flex-direction + flex-wrap
<div style="display:flex;width: 100%;">

```CSS
.block1{
    }
.block2{
    }
```

```CSS
.block3{
    }
.container{
    display:flex;
    width:400px;
    flex-flow: row wrap;
    }
```

</div>
<div>
    <div style="background:#cccccc;display:flex;
    width:400px;
    flex-flow: row wrap;
    ">
        <div style="width:120px;height:120px;background:green;">block1
        </div>
        <div style="width:150px;height:60px;background:blue;">block2
        </div>
        <div style="width: 300px;height:40px;background:yellow;">block3</div>
    </div>
</div>

<div style="clear:both"></div>

---

## Свойства отображения. Flexbox
Изменение порядка
<div style="display:flex;width: 100%;">

```CSS
.block1{
    order: 1}
.block2{
    }
```

```CSS
.block3{
    }
.container{
    display:flex;
    }
```

</div>
<div>
    <div style="background:#cccccc;display:flex;
    ">
        <div style="width:120px;height:120px;background:green;order: 1">block1
        </div>
        <div style="width:150px;height:60px;background:blue;">block2
        </div>
        <div style="width: 300px;height:40px;background:yellow;">block3</div>
    </div>
</div>

<div style="clear:both"></div>

---

## Свойства отображения. Flexbox
Изменение порадка
<div style="display:flex;width: 100%;">

```CSS
.block1{
    }
.block2{
    }
```

```CSS
.block3{
    order: -1}
.container{
    display:flex;
    }
```

</div>
<div>
    <div style="background:#cccccc;display:flex;
    ">
        <div style="width:120px;height:120px;background:green;">block1
        </div>
        <div style="width:150px;height:60px;background:blue;">block2
        </div>
        <div style="width: 300px;height:40px;background:yellow;order: -1">block3</div>
    </div>
</div>

<div style="clear:both"></div>

---

## Свойства отображения. Flexbox
Изменение порадка
<div style="display:flex;width: 100%;">

```CSS
.block1{
    }
.block2{
    }
```

```CSS
.block3{
    order: -1}
.container{
    display:flex;
    }
```

</div>
<div>
    <div style="background:#cccccc;display:flex;
    ">
        <div style="width:120px;height:120px;background:green;">block1
        </div>
        <div style="width:150px;height:60px;background:blue;">block2
        </div>
        <div style="width: 300px;height:40px;background:yellow;order: -1">block3</div>
    </div>
</div>

<div style="clear:both"></div>

---

## Свойства отображения. Flexbox
Распределение элементов вдоль направления
<div style="display:flex;width: 100%;">

```CSS
.block1{
    }
.block2{
    }
```

```CSS
.block3{
    }
.container{
    display:flex;
    justify-content: flex-start;
    }
```

</div>
<div>
    <div style="background:#cccccc;display:flex;
    justify-content: flex-start;
    ">
        <div style="width:120px;height:120px;background:green;">block1
        </div>
        <div style="width:150px;height:60px;background:blue;">block2
        </div>
        <div style="width: 300px;height:40px;background:yellow;">block3</div>
    </div>
</div>

<div style="clear:both"></div>

---

## Свойства отображения. Flexbox
Распределение элементов вдоль направления
<div style="display:flex;width: 100%;">

```CSS
.block1{
    }
.block2{
    }
```

```CSS
.block3{
    }
.container{
    display:flex;
    justify-content: flex-end;
    }
```

</div>
<div>
    <div style="background:#cccccc;display:flex;
    justify-content: flex-end;
    ">
        <div style="width:120px;height:120px;background:green;">block1
        </div>
        <div style="width:150px;height:60px;background:blue;">block2
        </div>
        <div style="width: 300px;height:40px;background:yellow;">block3</div>
    </div>
</div>

<div style="clear:both"></div>

---

## Свойства отображения. Flexbox
Распределение элементов вдоль направления
<div style="display:flex;width: 100%;">

```CSS
.block1{
    }
.block2{
    }
```

```CSS
.block3{
    }
.container{
    display:flex;
    justify-content: center;
    }
```

</div>
<div>
    <div style="background:#cccccc;display:flex;
    justify-content: center;
    ">
        <div style="width:120px;height:120px;background:green;">block1
        </div>
        <div style="width:150px;height:60px;background:blue;">block2
        </div>
        <div style="width: 300px;height:40px;background:yellow;">block3</div>
    </div>
</div>

<div style="clear:both"></div>

---

## Свойства отображения. Flexbox
Распределение элементов вдоль направления
<div style="display:flex;width: 100%;">

```CSS
.block1{
    }
.block2{
    }
```

```CSS
.block3{
    }
.container{
    display:flex;
    justify-content: justify;
    }
```

</div>
<div>
    <div style="background:#cccccc;display:flex;
    justify-content: justify;
    ">
        <div style="width:120px;height:120px;background:green;">block1
        </div>
        <div style="width:150px;height:60px;background:blue;">block2
        </div>
        <div style="width: 300px;height:40px;background:yellow;">block3</div>
    </div>
</div>

<div style="clear:both"></div>

---

## Свойства отображения. Flexbox
Распределение элементов вдоль направления
<div style="display:flex;width: 100%;">

```CSS
.block1{
    }
.block2{
    }
```

```CSS
.block3{
    }
.container{
    display:flex;
    justify-content: space-between;
    }
```

</div>
<div>
    <div style="background:#cccccc;display:flex;
    justify-content: space-between;
    ">
        <div style="width:120px;height:120px;background:green;">block1
        </div>
        <div style="width:150px;height:60px;background:blue;">block2
        </div>
        <div style="width: 300px;height:40px;background:yellow;">block3</div>
    </div>
</div>

<div style="clear:both"></div>

---

## Свойства отображения. Flexbox
Распределение элементов вдоль направления
<div style="display:flex;width: 100%;">

```CSS
.block1{
    }
.block2{
    }
```

```CSS
.block3{
    }
.container{
    display:flex;
    justify-content: space-around;
    }
```

</div>
<div>
    <div style="background:#cccccc;display:flex;
    justify-content: space-around;
    ">
        <div style="width:120px;height:120px;background:green;">block1
        </div>
        <div style="width:150px;height:60px;background:blue;">block2
        </div>
        <div style="width: 300px;height:40px;background:yellow;">block3</div>
    </div>
</div>

<div style="clear:both"></div>

---

## Свойства отображения. Flexbox
Распределение элементов поперёк направления
<div style="display:flex;width: 100%;">

```CSS
.block1{
    }
.block2{
    }
```

```CSS
.block3{
    }
.container{
    display:flex;
    align-items: flex-start;
    }
```

</div>
<div>
    <div style="background:#cccccc;display:flex;
    align-items: flex-start;
    ">
        <div style="width:120px;height:120px;background:green;">block1
        </div>
        <div style="width:150px;height:60px;background:blue;">block2
        </div>
        <div style="width: 300px;height:40px;background:yellow;">block3</div>
    </div>
</div>

<div style="clear:both"></div>

---

## Свойства отображения. Flexbox
Распределение элементов поперёк направления
<div style="display:flex;width: 100%;">

```CSS
.block1{
    }
.block2{
    }
```

```CSS
.block3{
    }
.container{
    display:flex;
    align-items: flex-end;
    }
```

</div>
<div>
    <div style="background:#cccccc;display:flex;
    align-items: flex-end;
    ">
        <div style="width:120px;height:120px;background:green;">block1
        </div>
        <div style="width:150px;height:60px;background:blue;">block2
        </div>
        <div style="width: 300px;height:40px;background:yellow;">block3</div>
    </div>
</div>

<div style="clear:both"></div>

---

## Свойства отображения. Flexbox
Распределение элементов поперёк направления
<div style="display:flex;width: 100%;">

```CSS
.block1{
    }
.block2{
    }
```

```CSS
.block3{
    }
.container{
    display:flex;
    align-items: center;
    }
```

</div>
<div>
    <div style="background:#cccccc;display:flex;
    align-items: center;
    ">
        <div style="width:120px;height:120px;background:green;">block1
        </div>
        <div style="width:150px;height:60px;background:blue;">block2
        </div>
        <div style="width: 300px;height:40px;background:yellow;">block3</div>
    </div>
</div>

<div style="clear:both"></div>

---

## Свойства отображения. Flexbox
Распределение элементов поперёк направления
<div style="display:flex;width: 100%;">

```CSS
.block1{
    }
.block2{
    }
```

```CSS
.block3{
    height:auto;
    }
.container{
    display:flex;
    align-items: stretch;
    }
```

</div>
<div>
    <div style="background:#cccccc;display:flex;
    align-items: stretch;
    ">
        <div style="width:120px;height:120px;background:green;">block1
        </div>
        <div style="width:150px;height:60px;background:blue;">block2
        </div>
        <div style="width: 300px;height:40px;background:yellow;height:auto;
    ">block3</div>
    </div>
</div>

<div style="clear:both"></div>

---

## Свойства отображения. Flexbox
Распределение элементов поперёк направления
<div style="display:flex;width: 100%;">

```CSS
.block1{
    }
.block2{
    align-self:flex-end;
    }
```

```CSS
.block3{
    height:auto;
    }
.container{
    display:flex;
    align-items: stretch;
    }
```

</div>
<div>
    <div style="background:#cccccc;display:flex;
    align-items: stretch;
    ">
        <div style="width:120px;height:120px;background:green;">block1
        </div>
        <div style="width:150px;height:60px;background:blue;align-self:flex-end;
    ">block2
        </div>
        <div style="width: 300px;height:40px;background:yellow;height:auto;
    ">block3</div>
    </div>
</div>

<div style="clear:both"></div>

---

## Свойства отображения. Flexbox
Растягивание при наличии свободного места
<div style="display:flex;width: 100%;">

```CSS
.block1{
    }
.block2{
    }
```

```CSS
.block3{
    flex-grow:1;
    }
.container{
    display:flex;
    }
```

</div>
<div>
    <div style="background:#cccccc;display:flex;
    ">
        <div style="width:120px;height:120px;background:green;">block1
        </div>
        <div style="width:150px;height:60px;background:blue;">block2
        </div>
        <div style="width: 300px;height:40px;background:yellow;flex-grow:1;
    ">block3</div>
    </div>
</div>

<div style="clear:both"></div>

---

## Свойства отображения. Flexbox
Растягивание при наличии свободного места
<div style="display:flex;width: 100%;">

```CSS
.block1{
    }
.block2{
    flex-grow:1;
    }
```

```CSS
.block3{
    flex-grow:1;
    }
.container{
    display:flex;
    }
```

</div>
<div>
    <div style="background:#cccccc;display:flex;
    ">
        <div style="width:120px;height:120px;background:green;">block1
        </div>
        <div style="width:150px;height:60px;background:blue;flex-grow:1;
    ">block2
        </div>
        <div style="width: 300px;height:40px;background:yellow;flex-grow:1;
    ">block3</div>
    </div>
</div>

<div style="clear:both"></div>

---

## Свойства отображения. Flexbox
Растягивание при наличии свободного места
<div style="display:flex;width: 100%;">

```CSS
.block1{
    }
.block2{
    flex-grow:1;
    }
```

```CSS
.block3{
    flex-grow:2;
    }
.container{
    display:flex;
    }
```

</div>
<div>
    <div style="background:#cccccc;display:flex;
    ">
        <div style="width:120px;height:120px;background:green;">block1
        </div>
        <div style="width:150px;height:60px;background:blue;flex-grow:1;
    ">block2
        </div>
        <div style="width: 300px;height:40px;background:yellow;flex-grow:2;
    ">block3</div>
    </div>
</div>

<div style="clear:both"></div>

---

## Свойства отображения. Flexbox
Сжатие при нехватке свободного места
<div style="display:flex;width: 100%;">

```CSS
.block1{
    }
.block2{
    }
```

```CSS
.block3{
    }
.container{
    display:flex;
    width:400px;
    }
```

</div>
<div>
    <div style="background:#cccccc;display:flex;
    width:400px;
    ">
        <div style="width:120px;height:120px;background:green;">block1
        </div>
        <div style="width:150px;height:60px;background:blue;">block2
        </div>
        <div style="width: 300px;height:40px;background:yellow;">block3</div>
    </div>
</div>

<div style="clear:both"></div>

---

## Свойства отображения. Flexbox
Сжатие при нехватке свободного места
<div style="display:flex;width: 100%;">

```CSS
.block1{
    flex-shrink:0;
    }
.block2{
    }
```

```CSS
.block3{
    }
.container{
    display:flex;
    width:400px;
    }
```

</div>
<div>
    <div style="background:#cccccc;display:flex;
    width:400px;
    ">
        <div style="width:120px;height:120px;background:green;flex-shrink:0;
    ">block1
        </div>
        <div style="width:150px;height:60px;background:blue;">block2
        </div>
        <div style="width: 300px;height:40px;background:yellow;">block3</div>
    </div>
</div>

<div style="clear:both"></div>

---

## Свойства отображения. Flexbox
Сжатие при нехватке свободного места
<div style="display:flex;width: 100%;">

```CSS
.block1{
    flex-shrink:0;
    }
.block2{
    }
```

```CSS
.block3{
    flex-shrink:4}
.container{
    display:flex;
    width:400px;
    }
```

</div>
<div>
    <div style="background:#cccccc;display:flex;
    width:400px;
    ">
        <div style="width:120px;height:120px;background:green;flex-shrink:0;
    ">block1
        </div>
        <div style="width:150px;height:60px;background:blue;">block2
        </div>
        <div style="width: 300px;height:40px;background:yellow;flex-shrink:4">block3</div>
    </div>
</div>

<div style="clear:both"></div>

---

## Свойства отображения. Grid
Распределение элементов по сетке
<div style="display:flex;width: 100%;">

```CSS
.block1{
    }
.block2{
    }
```

```CSS
.block3{
    }
.container{
    display:grid;
    grid-template-rows:100px 100px;
     grid-template-columns: 200px 50%;
    }
```

</div>
<div>
    <div style="background:#cccccc;display:grid;
    grid-template-rows:100px 100px;
     grid-template-columns: 200px 50%;
    ">
        <div style="width:120px;height:120px;background:green;">block1
        </div>
        <div style="width:150px;height:60px;background:blue;">block2
        </div>
        <div style="width: 300px;height:40px;background:yellow;">block3</div>
    </div>
</div>

<div style="clear:both"></div>

---

## Свойства отображения. Grid
Распределение элементов по сетке
<div style="display:flex;width: 100%;">

```CSS
.block1{
    grid-area: block1}
.block2{
    grid-area: block2}
```

```CSS
.block3{
    grid-area: block3}
.container{
    display:grid;
    grid-template-rows:100px 100px;
     grid-template-columns: 200px 50%;
    grid-template-areas: 'block1 block3' 'block2 block3'}
```

</div>
<div>
    <div style="background:#cccccc;display:grid;
    grid-template-rows:100px 100px;
     grid-template-columns: 200px 50%;
    grid-template-areas: 'block1 block3' 'block2 block3'">
        <div style="width:120px;height:120px;background:green;grid-area: block1">block1
        </div>
        <div style="width:150px;height:60px;background:blue;grid-area: block2">block2
        </div>
        <div style="width: 300px;height:40px;background:yellow;grid-area: block3">block3</div>
    </div>
</div>

<div style="clear:both"></div>

---

## Свойства отображения. Grid
Распределение элементов по сетке
<div style="display:flex;width: 100%;">

```CSS
.block1{
    grid-area: block1}
.block2{
    grid-area: block2}
```

```CSS
.block3{
    grid-area: block3}
.container{
    display:grid;
    grid-template-rows:100px 100px;
     grid-template-columns: 1fr 2fr;
    grid-template-areas: 'block1 block3' 'block2 block3'}
```

</div>
<div>
    <div style="background:#cccccc;display:grid;
    grid-template-rows:100px 100px;
     grid-template-columns: 1fr 2fr;
    grid-template-areas: 'block1 block3' 'block2 block3'">
        <div style="width:120px;height:120px;background:green;grid-area: block1">block1
        </div>
        <div style="width:150px;height:60px;background:blue;grid-area: block2">block2
        </div>
        <div style="width: 300px;height:40px;background:yellow;grid-area: block3">block3</div>
    </div>
</div>

<div style="clear:both"></div>

---

## Свойства отображения. Grid
Распределение элементов по сетке
<div style="display:flex;width: 100%;">

```CSS
.block1{
    width:auto;
    grid-area: block1}
.block2{
    width:auto;
    grid-area: block2}
```

```CSS
.block3{
    width:auto;
    grid-area: block3}
.container{
    display:grid;
    grid-template-rows:100px 100px;
     grid-template-columns: 200px 50%;
    grid-template-areas: 'block1 block3' 'block2 block3'}
```

</div>
<div>
    <div style="background:#cccccc;display:grid;
    grid-template-rows:100px 100px;
     grid-template-columns: 200px 50%;
    grid-template-areas: 'block1 block3' 'block2 block3'">
        <div style="width:120px;height:120px;background:green;width:auto;
    grid-area: block1">block1
        </div>
        <div style="width:150px;height:60px;background:blue;width:auto;
    grid-area: block2">block2
        </div>
        <div style="width: 300px;height:40px;background:yellow;width:auto;
    grid-area: block3">block3</div>
    </div>
</div>

<div style="clear:both"></div>

---

## Свойства отображения. Grid
Распределение элементов по сетке
<div style="display:flex;width: 100%;">

```CSS
.block1{
    width:auto;
    grid-area: block1}
.block2{
    width:auto;
    grid-area: block2}
```

```CSS
.block3{
    width:auto;
    grid-area: block3}
.container{
    display:grid;
    grid-template-rows:100px 100px;
     grid-template-columns: 200px 1fr;
    grid-template-areas: 'block1 block3' 'block2 block3'}
```

</div>
<div>
    <div style="background:#cccccc;display:grid;
    grid-template-rows:100px 100px;
     grid-template-columns: 200px 1fr;
    grid-template-areas: 'block1 block3' 'block2 block3'">
        <div style="width:120px;height:120px;background:green;width:auto;
    grid-area: block1">block1
        </div>
        <div style="width:150px;height:60px;background:blue;width:auto;
    grid-area: block2">block2
        </div>
        <div style="width: 300px;height:40px;background:yellow;width:auto;
    grid-area: block3">block3</div>
    </div>
</div>

<div style="clear:both"></div>

---