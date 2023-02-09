<template>
  <dialog :open="isDialogOpen">
    <h3>ข้อมูลวิชา {{ courseInfo.course_name }}</h3>
    <small><strong>หน่วยกิต:</strong> {{ courseInfo.course_credit }}</small>
    <small><strong>ผู้สอน:</strong> {{ courseInfo.course_instructor }}</small>
    <hr />
    <button style="padding: 5px" @click="closeDialogue">ปิดหน้าต่าง</button>
  </dialog>

  <h3>รายวิชาทั้งหมด</h3>
  <hr />
  <table>
    <tr>
      <th>รหัสวิชา</th>
      <th>ชื่อวิชา</th>
    </tr>

    <tr v-for="(course, index) in courses" :key="index">
      <td style="text-align: left">{{ course.course_id }}</td>
      <td style="text-align: left">
        <a href="#" @click="viewDetails(index)">{{ course.course_name }}</a>
      </td>
    </tr>
  </table>
</template>
<script setup>
import courses from "../json/cs_courses.json";
import { ref } from "vue";
const isDialogOpen = ref(false);
const courseInfo = ref({});
const closeDialogue = () => (isDialogOpen.value = false);
function viewDetails(key) {
  courseInfo.value = {
    course_name: courses[key].course_name,
    course_credit: courses[key].credit,
    course_instructor: null,
  };
  isDialogOpen.value = true;
}
</script>
<style scoped>
small {
  display: block;
}
</style>
