<script>
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
</script>
