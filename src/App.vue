<script setup>
//import "@/assets/css/pico.min.css";
import { RouterLink, RouterView } from "vue-router";
</script>

<template>
  <main class="container">
    <header class="header-margin">
      <div class="text-center" style="margin-top: 0.5em; margin-bottom: 4em">
        <img
          style="height: 120px"
          src="https://i.imgur.com/gDeZKlv.png"
          alt="logo"
        />
      </div>
      <nav class="nav">
        <RouterLink to="/">หน้าแรก</RouterLink>
        <RouterLink to="/courses">รายวิชา</RouterLink>
        <RouterLink to="/enrollments">ลงทะเบียนเรียน</RouterLink>
        <RouterLink to="/mycourse">วิชาที่ฉันลงทะเบียน</RouterLink>
      </nav>
    </header>

    <RouterView />
  </main>
</template>

<style scoped>
.header-margin {
  padding-top: 0.8em;
  padding-bottom: 0.8em;
}

nav > a {
  padding-left: 0.5em;
  padding-right: 0.5em;
}

.nav {
  display: flex;
  justify-content: space-between;
}

.text-center {
  text-align: center;
}
</style>
