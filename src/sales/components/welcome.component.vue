<script>
import {Developer} from "../domain/model/developer.entity.js";

export default {
  name: "welcome",
  props: {
    firstName: String,
    lastName: String
  },

  methods: {
    developerName() {
      let developer = new Developer(this.firstName, this.lastName);
      return developer.fullName;
    }
  }
}
</script>

<template>
  <p>Hello {{ developerName() }}. Now you are a Vue Developer!</p>
</template>

<style scoped>

</style>