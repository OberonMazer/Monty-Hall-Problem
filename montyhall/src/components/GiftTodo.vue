<template>
  <div class="gifttodo">
    <div class="gifttodo-tie-1"></div>
    <div class="gifttodo-tie-2"></div>
    <div class="gifttodo-top"></div>
    <div class="gifttodo-body"></div>
  </div>
</template>

<script>
export default {
  name: 'GiftTodo'
}
</script>

<style>
.gifttodo {
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: center;
  z-index: 10;
}

.gifttodo-top {
  width: 100px;
  height: 25px;
  background-color: #7aa944;
}

.gifttodo-body {
  width: 90px;
  height: 60px;
  background-color: #5c7e32;
}

.gifttodo-tie-1 {
  position: absolute;
  width: 15px;
  height: 85px;
  background-color: red;
}

.gifttodo-tie-2 {
  position: absolute;
  top: 40px;
  width: 90px;
  height: 15px;
  background-color: red;
}
</style>