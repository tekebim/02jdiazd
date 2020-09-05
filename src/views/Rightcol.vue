<template>
    <div class="aside col-md-12 col-lg-4 py-5">
        <h1>Colonne de droite</h1>

        <div class="form-group">
            <InputBlock
                    v-bind:value="inputdemerde.value"
                    v-bind:classname="inputdemerde.classname"
                    v-bind:placeholder="inputdemerde.placeholder"
                    v-on:input="inputdemerde.value = $event"
                    v-on:keyup.enter="searchNearBy"
            >
                Lorem ipsum dolor sin amet
                <template v-slot:label>Effectuer une recherche</template>
                <template v-slot:message>{{ inputdemerde.message }}</template>
            </InputBlock>
        </div>
        <hr/>
    </div>
</template>

<script>
// @ is an alias to /src
import InputBlock from '@/components/InputBlock.vue'

export default {
  name: 'rightcol',
  components: {
    InputBlock
  },
  data () {
    return {
      inputdemerde: {
        value: '',
        placeholder: 'placeholder de l\'input',
        classname: '',
        message: 'message par défaut'
      }
    }
  },
  watch: {
    'inputdemerde.value': function (val, oldValue) {
      if (val.length < 5) {

          if(oldValue.length == 1) {
              console.log(oldValue)
              console.log('0 texte')
              this.inputdemerde.classname = ''
              this.inputdemerde.message = ''
          }
          else {
              this.inputdemerde.classname = 'error'
              this.inputdemerde.message = 'trop court'
          }
      } else {
        this.inputdemerde.classname = ''
        this.inputdemerde.message = 'ok !'
      }
    }
  }
}
</script>

<style lang="scss" scoped="scoped">
    .aside {
        // background-color: $primary-color;
        // background-color: $secondary-color;
        background-color: aliceblue;
    }
    .error {
        background-color: #ff5555;
    }
</style>
