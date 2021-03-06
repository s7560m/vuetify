<template lang="pug">
  component-view(v-bind:doc="doc" id="fab-view")
    v-alert(color="info" icon="info" value) For more information on all the options available for the <code>v-btn</code> component, please navigate to the <router-link to="/components/buttons" class="white--text">Button documentation</router-link>.
</template>

<script>
  export default {
    name: 'fabs-view',

    data () {
      return {
        doc: {
          component: 'VBtn',
          edit: 'FabsView',
          title: 'Buttons: Floating Action Button',
          desc: `The <code>v-btn</code> component can be used as a Floating action button. This provides an application a main point of action. Combined with the <code>v-speed-dial</code> component, you can create a diverse set of functions available for your users.`,
          examples: [
            { header: "Promoted action", file: "fabs/promoted-action", desc: `Floating action buttons can be attached to material to signify a promoted action in your application. The default size will be used in most cases, whereas the <code>small</code> variant can be used to maintain continuity with similar sized elements.` },
            { header: "Small variant", file: "fabs/small", desc: `For better visual appeal, we use a small button to match our list avatars.` },
            { header: "Display animation", file: "fabs/display-animation", desc: `When displaying for the first time, a floating action button should animate onto the screen. Here we use the <code>v-fab-transition</code> with v-show. You can also use any custom transition provided by Vuetify or your own.` },
            { header: "Lateral screens", file: "fabs/lateral-screens", desc: `When changing the default action of your button, it is recommended that you display a transition to signify a change. We do this by binding the <code>key</code> prop to a piece of data that can properly signal a change in action to the Vue transition system. While you can use a custom transition for this, ensure that you set the <code>mode</code> prop to <strong>out-in</strong>.` },
            { header: "FAB with speed-dial", file: "fabs/speed-dial", desc: `The speed-dial component has an very robust api for customizing your FAB experience exactly how you want.` },
          ],
          props: {
            'speed-dial': {
              shared: ['positionable'],
              model: {
                type: ['Boolean'],
                default: 'False',
                description: 'Used to link the speed-dial state to a button (fab).'
              },
              params: [
                ['direction', `String ['top', 'right', 'bottom', 'left']`, 'top', 'Controls the direction that the speed dial list will open.'],
                ['hover', 'Boolean', 'False', 'Open the speed dial when the button is hovered over.'],
                ['transition', 'String', 'scale-transition', 'The default transition to be used for the list animation.']
              ]
            }
          },
          slots: {
            'speed-dial': {
              shared: ['default'],
              params: [
                ['activator', 'The element that will activate the menu']
              ]
            }
          }
        }
      }
    }
  }
</script>

<style lang="stylus">
  #fab-view
    .btn--floating.btn--absolute
      z-index: 0 !important
</style>
