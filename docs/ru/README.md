# Введение

### Что такое `vue-loader`?

`vue-loader` – это загрузчик для Webpack, который преобразует Vue компоненты, написанные в следующем формате в обычные JavaScript модули:

![screenshot](http://blog.evanyou.me/images/vue-component.png)

`vue-loader` предлагает множество полезных возможностей:

- Поддержка ES2015 по умолчанию;
- Позволяет использовать разные загрузчики Webpack для разных частей Vue компонента, например, SASS для `<style>` и Jade для `<template>`;
- Обращается со статическими ресурсами, указанными в `<style>` и `<template>`, как с зависимостями модуля, и обрабатывает их Webpack загрузчиками;
- Может эмулировать scoped CSS для компонентов;
- Поддерживает горячую замену модулей.

В двух словах, сочетание Webpack и `vue-loader` предоставляет вам современный, гибкий и невероятно эффективный подход к написанию клиентских приложений на Vue.js.

### Что такое Webpack?

Если вы уже знакомы с Webpack, можете пропустить дальнейшее объяснение. Для тех же, кому Webpack в новинку, вот краткая вводная:

[Webpack](http://webpack.github.io/) – это сборщик модулей. Он берёт кучу файлов, рассматривая каждый как модуль, разрешает зависимости между ними и собирает их в статические ресурсы, готовые к развёртыванию.

![webpack](http://webpack.github.io/assets/what-is-webpack.png)

В качестве простого примера, представим, что у нас есть набор модулей CommonJS. Они не могут запускаться прямо в браузере, так что нам нужно "собрать" их в единый файл, который можно будет вставить на страницу через тег `<script>`. Webpack может сделать это за нас, следуя инструкциям `require()`.

Но Webpack может делать и больше. С "загрузчиками", мы можем научить Webpack преобразовывать любые типы файлов любым нужным нам образом, прежде чем выдать финальную сборку. Например:

- Скомпилировать ES2015, CoffeeScript или TypeScript модули в обычные ES5 CommonJS модули;
- Пропустить код через статический анализатор, прежде чем приступать к компиляции;
- Скомпилировать Jade шаблоны в обычный HTML и добавить его на страницу в виде строки JavaScript;
- Скомпилировать SASS файлы в обычный CSS, затем конвертировать его в JS скрипт, который будет добавлять полученный CSS как тег `<style>`;
- Обработать файлы изображений, указанные в HTML или CSS, переместить их в нужное место, согласно файлу конфигурации, и переименовать, используя их md5 хеш.

Webpack настолько крут, что когда вы поймете, как он работает, он значительно улучшит ваш процесс разработки клиентской части. Его основным недостатком является многословная и сложная конфигурация; но с этим руководством вы сможете найти решения для большинства задач, возникающих при работе с Webpack в сочетании с Vue.js и `vue-loader`.