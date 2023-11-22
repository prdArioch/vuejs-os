# vuejs-os
tuto vuejs pour OpenStudio

{{ variable }}

## Directives
v-once
v-if
v-else
v-else-if
v-show

## Binding
v-bind -> :
    -- on peut binder style par exemple
v-on -> @
    click
    focus
    ...
v-model

## Modifier
v-on:click.prevent = "onclick"


## script
- partie data
- partie computed
    -- Geter et setter
- partie watch

v-for -> maping
Avec un array
<div v-for="item of items" v-bind:key="item.id">
  <!-- content -->
</div>
Avec un objet
<div v-for="(value, name, index) in object" >
  <!-- content -->
</div>

ses propres event

#emit

props avec type complexe
as PropType<T>

typer le data data: ():XXX => ({})

this.$refs -> as InstanceType<typeof X> -> permet d'accéder aux méthodes de X