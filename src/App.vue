<script setup>
import axios from "axios";
import { ref } from "vue";
const data = ref();
const config = {
  method: "get",
  url: "https://api.codename-t.com/campus",
  headers: {},
};
axios(config)
  .then(function (response) {
    data.value = response.data;
    console.log(data.value);
  })
  .catch(function (error) {
    console.log(error);
  });
</script>
<template>
  <div class="container">
    <h1 style="color: black; "><center>คณะและสาขา</center></h1>
    <table>
      <thead>
        <th style="color: black;">สาขา</th>
        <th style="color: black;">คณะ</th>
      </thead>
      <tbody>
        <tr v-for="(value, index) in data" :key="index">
          <td style="color: black;">{{ value.faculty_name_th }}</td>
          <td style="color: black;">{{ value.field_name_th }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<style scoped></style>