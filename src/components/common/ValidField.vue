<template lang="pug">
  div.valid-field
    label.valid-field-label(
      v-if="label"
    ) {{ label }}
    input.valid-field-input(
      v-bind:value="value"
      v-on:input="$emit('input', $event.target.value)"
      v-validate="valid"
      :type="type"
      :name="fieldName"
    )
    span.valid-field-error(
      v-show="errors.has(fieldName)"
    ) {{errors.first(fieldName)}}
</template>

<script>
export default {
  props: {
    fieldName: String,
    label: String,
    labelWidth: {
      type: Number,
      default: 100,
    },
    required: {
      type: Boolean,
      default: false,
    },
    type: String,
    valid: String,
    value: {
      type: String,
      default: "",
    },
  },
  
}

</script>

<style lang="postcss" scoped>
.valid-field {
  display: flex;

  &.valid-field-label {
    line-height: 40px;
    margin-right: 10px;
    text-align: left;
  }
}
</style>