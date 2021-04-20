# Vue 3 Plugin for Bootstrap 5

Supported version is: Vue 3, Bootstrap 5.


# ALPHA ALPHA ALPHA ALPHA ALPHA ALPHA ALPHA ALPHA

This plugin is designed to add directives to Vue 3 that can be used to create and control Bootstrap 5 JavaScript 
objects.

## Install

In your main.js:
```javascript

import { createVbPlugin, VbModal, VbOffcanvas, VbTooltip } from "vue3-plugin-bootstrap5"

const createVbPlugin = createVbPlugin({ VbModal, VbOffcanvas, VbTooltip })

app.use(createVbPlugin)

```


## Modal

On the button replace the Bootstrap attributes
    `<button data-bs-toggle="modal" data-bs-target="#exampleModal" ...`

With `<button v-vb-toggle:modal data-bs-target="#exampleModal" ...`

See [ModalExamples.vue](examples/basic/src/components/ModalExamples.vue)


# Offcanvas

On the button replace the Bootstrap attributes
`<button data-bs-toggle="offcanvas" data-bs-target="#exampleOffcanvas" ...`

With `<button v-vb-toggle:offcanvas data-bs-target="#exampleOffcanvas" ...`

See [OffcanvasExamples.vue](examples/basic/src/components/OffcanvasExamples.vue)


# Tooltip

Replace this `<button data-bs-toggle="tooltip" title="Hello World" ...`

With `<button v-vb-toggle:tooltip="'Hello World'" ...`

See [TooltipExamples.vue](examples/basic/src/components/TooltipExamples.vue)


# Access to raw Bootstrap JavaScript objects

When `v-vb-is` is added to an element this plugin will add a `$vb` property to it with the raw Bootstrap
object.

```javascript

    // use $vb like this:
    this.$refs.modalExample.$vb.modal.hide()

    // or when `v-vb-is` is used on the root element of a component:
    this.$el.$vb.modal.hide()

    // note, this is same as doing this:    
    bootstrap.Modal.getInstance(this.$refs.modalExample).hide()

```