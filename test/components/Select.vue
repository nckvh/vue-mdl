<template lang="jade">
div
  h1 Select
  h3 vue
  mdl-checkbox(:checked.sync='visible') Visible
  p Changed {{changes}}
  mdl-select#select(v-if='visible', label='Country', @change='changes++', :value.sync='country', :options='countriesArray')
  br
  mdl-select#select-val(v-ref:select-val label='Country', :value.sync='countryVal', :options='countries')
</template>

<script lang="babel">
export default {
  data () {
    return {
      country: 'Russia',
      countryVal: 'es',
      changes: 0,
      visible: true,
      countriesArray: ['Russia', 'Spain', 'France', 'China'],
      countries: [
        {
          name: 'Select One',
          value: ''
        },
        {
          name: 'Russia',
          value: 'ru'
        },
        {
          name: 'Spain',
          value: 'es'
        },
        {
          name: 'France',
          value: 'fr'
        },
        {
          name: 'China',
          value: 'cn'
        }
      ]
    }
  }
}
</script>
