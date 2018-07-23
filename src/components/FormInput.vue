<template lang="pug">
div
  ValidField(
    label="test"
    type="text"
    valid="required"
    fieldName="test"
    v-model="test"
  )
  ValidField(
    label="testNum"
    type="text"
    valid="required|numeric"
    fieldName="testNum"
    v-model="testNum"
  )
  ValidField(
    label="testDate"
    type="date"
    valid="date_format"
    fieldName="testDate"
    v-bind:value="testDate"
    v-on:input="testDate = $event"
  )
</template>

<script>
import ValidField from "./common/ValidField";

export default {
  components: { ValidField},
  data() {
    return {
      test: "",
      testNum: "",
      testDate:"",
    };
  },
  methods: {},
};
</script>