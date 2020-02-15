# Ссылки

## HTML

**Базовый вид ссылки**:<br>
`<a href="https://css-tricks.com">CSS-Tricks</a>`

**Зависимая ссылка**:<br>
`<a href="/pages/about.html">About</a>`

Ссылка обращается к текущему домену по указанному пути (/pages/about.html).

**"Прыгающая" ссылка**:<br>
```html
<a href="#section-2">Section Two</a>
<!-- will jump to... -->
<section id="section-2"></section>
```

Экран пользователя прокрутится до обозначенного элемента (`<section id="section-2"></section>`).

**"Выключенная" ссылка**:<br>
```css
a:not[href] {
  /* style a "disabled" link */
}
```

Поведение ссылки станет похожим на `<span>`. Может быть полезно для ссылок, которые должны быть временно недоступны, например, по причине того,<br>
что надо сначала зарегистрироваться/войти. Чтобы получить ссылку такого вида необходимо не указывать атрибут `href`.

**Ссылки на новые вкладки**:
```html
<a href="https://css-tricks.com" target="_blank" rel="noopener noreferrer">
  CSS-Tricks
</a>
```