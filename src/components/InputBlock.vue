<template>
    <fieldset v-bind:class="['input--block col-12']">
        <h3>
            <slot></slot>
        </h3>
        <label for="truc">
            <slot name="label"></slot>
        </label>
        <input name="truc"
               v-bind:value="value"
               v-bind:placeholder="placeholder"
               v-on:input="$emit('input', $event.target.value)"
               v-bind:class="[classname, 'form-control form-control-lg']"
        >
        <span class="notification">
            <slot name="message"></slot>
        </span>
    </fieldset>
</template>

<script>
export default {
  name: 'InputBlock',
  props: {
    classname: String,
    value: String,
    placeholder: String
  }
}
</script>

<style scoped="scoped" lang="scss">
    .input--block > * {
    }

    input {
        border:1px solid red;
    }

    .error {
        background-color: #ff5555;
    }

</style>
