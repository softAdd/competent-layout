# Кнопки. Статья: [ishadeed.com](https://ishadeed.com/article/styling-the-good-old-button/)

Начальные стили, взятые из google chrome
```css
.c-button {
    -webkit-writing-mode: horizontal-tb !important;
    -webkit-appearance: button;
    border-color: rgb(216, 216, 216) rgb(209, 209, 209) rgb(186, 186, 186);
    border-style: solid;
    border-width: 1px;
    padding: 1px 7px 2px;
    text-rendering: auto;
    color: initial;
    display: inline-block;
    text-align: start;
    margin: 0em;
    font: 400 11px system-ui;
}
```
Базовые стили для кнопки
```css
.c-button {
  appearance: none;
  border: 0;
  border-radius: 5px;
  background: #4676D7;
  color: #fff;
  padding: 8px 16px;
  font-size: 16px;
}
```
Хорошо также добавить минимальную ширину
```css
.c-button {
    min-width: 100px;
    /* other styles */
}
```
Далее необходимо позаботиться о состояних кнопки: hover, focused и disabled
```css
.c-button:hover {
  background: #1d49aa;
}

.c-button:focus {
  outline: none;
  box-shadow: 0 0 0 4px #cbd6ee;
}

.c-button[disabled] {
    color: #d2d5db;
    background: #6c7589;
    cursor: not-allowed;
}
```
Полный css:
```css
.c-button {
  min-width: 100px;
  font-family: inherit;
  appearance: none;
  border: 0;
  border-radius: 5px;
  background: #4676d7;
  color: #fff;
  padding: 8px 16px;
  font-size: 1rem;
  cursor: pointer;
}

.c-button:hover {
  background: #1d49aa;
}

.c-button:focus {
  outline: none;
  box-shadow: 0 0 0 4px #cbd6ee;
}

.c-button[disabled] {
    color: #d2d5db;
    background: #6c7589;
    cursor: not-allowed;
}
```

## Кнопки с иконками, многострочные кнопки и т.д. в статье: [ishadeed.com](https://ishadeed.com/article/styling-the-good-old-button/)