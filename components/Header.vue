<template>
  <v-app-bar color="deep-purple accent-4" dense dark>
    <div class="d-flex justify-space-between" style="width: 50%">
      <div>
        this is my header
      </div>
      <a class="display-1" @click="$router.go(-1)">back</a>
    </div>
  </v-app-bar>
</template>

<script>
export default {
  name: 'Header'
}
</script>

<style></style>
