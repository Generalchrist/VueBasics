<script lang="ts">
export default {
  data() {
    return {
      name: 'John Doe',
      status: 'active',
      tasks: ['Task One', 'Task Two', 'Task Three'],
      link: 'https://google.com',
    }
  },
  methods: {
    toggleStatus() {
      switch (this.status) {
        case 'active':
          this.status = 'pending'
          break
        case 'pending':
          this.status = 'inactive'
          break
        default:
          this.status = 'active'
          break
      }
    },
  },
}
</script>

<template>
  <h1>{{ name }}</h1>
  <p v-if="status === 'active'">User is active</p>
  <p v-else-if="status === 'pending'">User is pending</p>
  <p v-else>User is inactive</p>

  <h3>Tasks</h3>
  <ul>
    <!-- 
      v-bind: yerine sadece : koydugumuzda da ayni sekilde baglantiyi kurar
      : isareti bu yaptigimiz elementin dinamik oldugunu bize anlatir
      :key="task" oldugu zaman vue buradaki task adindaki degiskenin degerini buraya koyar
      key="task" dersek oraya task stringini koyar asagisaki google ornegine bakalim mesela
    -->
    <li v-for="task in tasks" v-bind:key="task">
      {{ task }}
    </li>
  </ul>

  <!-- 
    Ayni sekilde burada da bir v-bind var bu link degerine baglandigini bize anlatir
    ama biz oraya sadece href="link" koysaydik o bizi browserda link stringinde bir yere
    yonlendirirdi
    bunu deneyerek gorebilirsin.
  -->
  <a v-bind:href="link" target="_blank">Click for google</a>

  <br />
  <!-- 
    v-on:click yerine @click de kullanilabilir 
    hangisi sana daha uygunsa onu kullanabilirsin 
    -->
  <button v-on:click="toggleStatus">Change Status</button>
</template>

<!-- 
  scoped sadece bu component icin gecerli anlamina geliyor 
  -->
<style scoped></style>
