<template>
  <div class="header">
    <img alt="Vue logo" src="../../assets/logo.png">
    <span> Welcome </span>
  </div>
</template>

<script>
export default {
  name: 'Header',
};
</script>


<style>
.header {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
  width: 100%;
}
.header img{
  width: 50px;
}
</style>
