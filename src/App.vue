<script>
import RegisterDeveloper from "./sales/components/register-developer.component.vue";
import Welcome from "./sales/components/welcome.component.vue";
import ShowDeveloperCount from "./sales/components/show-developer-count.component.vue";

export default {
  name: "app",
  components: {ShowDeveloperCount, Welcome, RegisterDeveloper},
  data() {
    return {
      firstName: '',
      lastName: '',
      developerCount: 0
    }
  },
  methods: {
    onDeveloperRegistered(developer) {
      this.firstName = developer.firstName;
      this.lastName = developer.lastName;
      console.log("Developer registered: ", developer);
      this.updateDeveloperCount(developer);
    },

    updateDeveloperCount(developer) {
      if (developer.fullName !== "Unknown")
        this.developerCount++;
    }
  }
}
</script>

<template>
  <h1>Hello Vue Developer Application</h1>
  <register-developer v-on:developer-registered="onDeveloperRegistered"/>
  <welcome :first-name="firstName" :last-name="lastName" :developer-count="developerCount"/>
  <show-developer-count :developer-count="developerCount"/>
</template>