<template>
  <b-form v-model="valid">
    <b-input-group v-if="hasName" prepend="Name" class="my-2">
      <b-form-input
        v-model="userInfo.name" 
        label="Name"
      />
    </b-input-group>
    <b-input-group prepend="Email" class="my-2">
      <b-form-input
        v-model="userInfo.email" 
        label="Email"
      />
    </b-input-group>

    <b-input-group prepend="Password" class="my-2">
      <b-form-input
        v-model="userInfo.password"
        label="Password"
        type="password"
      />
    </b-input-group>

    <b-btn :disabled="!valid" @click="submitForm(userInfo)">{{ buttonText }}</b-btn>
  </b-form>
</template>

<script>
  import validations from "~/utils/validations";
  export default {
    props: ["submitForm", "buttonText", "hasName"],
    data() {
      return {
        valid: false,
        showPassword: false,
        // eslint-disable-next-line vue/no-dupe-keys
        hasName: false,
        userInfo: {
          email: '',
          password: ''
        },
        ...validations
      }
    }
  }
</script>

<style lang="scss" scoped>
</style>