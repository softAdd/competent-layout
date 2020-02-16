# Кнопки. Статьи: [css-tricks.com](https://css-tricks.com/a-complete-guide-to-links-and-buttons/), [medium.com](https://medium.com/@baradusov/стилизуем-кнопки-правильно-6ea5abc278b1)

Базовый вид кнопки в HTML:
```html
<button>Buy Now</button>
```

Использование кнопок в формах:
```html
<form action="/" method="POST">
  <input type="text" name="name" id="name">
  <button>Submit</button>

  <!-- If you want to be more explicit... -->
  <button type="submit">Submit</button>

  <!-- ...or clear the form inputs back to their initial values -->
  <button type="reset">Reset</button>

  <!-- This prevents a `submit` action from firing which may be useful sometimes inside a form -->
  <button type="button">Non-submitting button</button>
</form>

<form action="/" method="get">

  <!-- override the action -->
  <button formaction="/elsewhere/" type="submit">Submit to elsewhere</button>

  <!-- override encytype -->
  <button formenctype="multipart/form-data" type="submit"></button>

  <!-- override method -->
  <button formmethod="post" type="submit"></button>

  <!-- do not validate fields -->
  <button formnovalidate type="submit"></button>

  <!-- override target e.g. open in new tab -->
  <button formtarget="_blank" type="submit"></button>

</form>
```

Кнопки могут содержать дочерние элементы:
```html
<button>
   <svg aria-hidden="true" focusable="false">
     <path d="..." />
   </svg>
   <span class="callout">Big</span>
   Sale!
</button>

<button type="button">
  <span role="img" aria-label="Fox">
    🦊
  </span>
  Button
</button>
```

## Стилизация кнопок

Кнопки должны выглядеть так, чтобы было заметно, что на них возможно нажать. Посмотреть примеры стилизации кнопок можно по ссылке - [the CodePen Topic on Buttons.](https://codepen.io/topic/buttons/picks).

Убрать стили по умолчанию для всех кнопок:
```css
button {
  font-family: inherit; /* For all browsers */
  font-size: 100%; /* For all browsers */
  line-height: 1.15; /* For all browsers */
  margin: 0; /* Firefox and Safari have margin */
  overflow: visible; /* Edge hides overflow */
  text-transform: none; /* Firefox inherits text-transform */
  -webkit-appearance: button; /* Safari otherwise prevents some styles */
}

button::-moz-focus-inner {
  border-style: none;
  padding: 0;
}

button:-moz-focusring {
  outline: 1px dotted ButtonText;
}
```

Другой, чуть менее эффективный способ сброса - кнопки становятся в виде текста. Такой способ лучше использовать, например, как миксин, в случае использования препроцессоров (Sass, Less или еще каких-нибудь).
```css
/**
 * Сброс стилей у кнопки.
 * Придётся немного поработать, чтобы получить нейтральный вид.
*/
button {
  padding: 0;
  border: none;
  font: inherit;
  color: inherit;
  background-color: transparent;
/* отображаем курсор в виде руки при наведении; некоторые
  считают, что необходимо оставлять стрелочный вид для кнопок */
  cursor: pointer;
}
```
```html
@mixin button-reset {
   padding: 0;
   border: none;
   font: inherit;
   color: inherit;
   background-color: transparent;
   cursor: pointer;
}
  
.my-custom-button {
   @include button-reset;
   padding: 10px;
   background-color: skyblue;
}
<button type="button">
   У меня браузерные стили по-умолчанию.
</button>
<button type="button" class="my-custom-button">
   А я использую собственные стили.
</button>
```

В дополнение к использованию отмены базовых стилей для кнопок, можно добавить свой консистентный класс, задающий основу для всех кнопок:
```css
.button {
  border: 0;
  border-radius: 0.25rem;
  background: #1E88E5;
  color: white;
  font-family: -system-ui, sans-serif;
  font-size: 1rem;
  line-height: 1.2;
  white-space: nowrap;
  text-decoration: none;
  padding: 0.25rem 0.5rem;
  margin: 0.25rem;
  cursor: pointer;
}
```

Состояния кнопок, которые можно стилизовать:
```css
button:hover { }
button:focus { }
button:active { }
button:visited { }
```

Пример базовых стилей для кнопки:
```css
.btn {
    /* по-умолчанию для <button>, но пригодится для <a> */
    display: inline-block;
    text-align: center;
    text-decoration: none;
    /* создаём маленькие отступы, если кнопки перенесутся на две строки */
    margin: 2px 0;
    /* невидимая граница (понадобится для цвета при наведении/фокусе) */
    border: solid 1px transparent;
    border-radius: 4px;
    /* размер строится из текста и отступов (без width/height) */
    padding: 0.5em 1em;
    /* убедитесь, что достаточно контраста! */
    color: #ffffff;
    background-color: #9555af;
}
```

## Больше информации в следующих источниках: [css-tricks.com](https://css-tricks.com/a-complete-guide-to-links-and-buttons/), [medium.com](https://medium.com/@baradusov/стилизуем-кнопки-правильно-6ea5abc278b1)