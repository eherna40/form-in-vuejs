<template lang="pug">
  #app
    div.container
      div.row
        div(class="col l4 m5 s12 offset-s0 offset-l4 offset-m4 form")
          form.form-register
            div.center
              img(src="./assets/logo.jpg" class="center responsive-img")
            h2.center Registro estación Platzi
            template(v-for='campo in formRegister')
              label(v-bind:for='campo.value') {{campo.nombre}}
              input(type='text', v-bind:id='campo.value', v-bind:value='campo.value')
            label Cargo
            select(v-model="selectedJob")
              option(v-for="job in jobs" v-bind:value="job.value") {{job.name}}
            button(type="submit" class="btn btn-flat waves-effect waves-light right") Enviar
</template>
<script>
export default {
  name: 'app',
  data () {
    return {
      formRegister:[{
            nombre: 'Nombre',
        },
        {
            nombre: 'Apellido',
        }],
        jobs: [
          {name: 'FullStack JS', value: 'fullstackJs'},
          {name: 'FrontEnd Developer', value: 'frontend'},
          {name: 'Backend Developer', value: 'backend'},
      ],
        selectedJob: 'fullstackJs',
    }
  }
}
</script>

<style lang="scss">
@import './scss/main.scss'
</style>
