<script setup>
const props = defineProps(['user'])
</script>

<template>
    <tr >
    <td class="user">{{ props.user.summary }}</td>
    <td class="user">{{ user.EmailAdress }}</td>
    <td class="user">{{ user.phonenumber }}</td>
    <td class="user">{{ user.location }}</td>
    <td class="user">{{ user.tags }}</td>
    </tr>
</template>

<style>
.user
{
font-family: 'Courier New', Courier, monospace;
width:120px;
height:20px;
border: 3px solid orange;
  }
</style>