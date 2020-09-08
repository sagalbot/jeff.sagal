---
title: Renderless Vue.js Tailwind Abstractions
tags:
  - Vue.js
  - TailwindCSS
  - Renderless Components
---

Tailwind CSS works incredibly well with component based templating languages. Today we'll take a look at how you can leverage "renderless" components in Vue to create super portable component abstractions. Let's break it down.

```js
export default {
  functional: true,
  props: {
    tag: {
      type: String,
      default: 'h2',
    },
  },
  render(createElement, { props, slots, data, listeners }) {
    const boundClasses = data.class || {}
    const staticClasses = data.staticClass || ''
    const defaultClasses = `text-2xl font-black text-purple-900 ${staticClasses}`

    return createElement(
      props.tag,
      {
        class: {
          [defaultClasses]: true,
          ...boundClasses,
        },
        attrs: {
          ...data.attrs,
        },
        on: { ...listeners },
      },
      slots().default
    )
  },
}
```
