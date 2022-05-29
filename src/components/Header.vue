<template>
<div class="header">
    <div class="header_container">
      <a href="#">
          <img src="../assets/img/logo.png" alt="logo" class="header_logo">
      </a>
      <p class="header_text">
          Самые вкусные арбузы только у нас!
      </p>
  </div>
</div>
  
</template>

<script>
export default {
  name: 'Header'
}
</script>

<style scoped>
.header{
    border-bottom: 0.05rem solid rgba(213, 213, 213, 0.6);
}
.header_container {
    margin: 0 auto;
    width: 65%;
    height: 60px;

    display: flex;
    align-items: center;
    justify-content: space-between;
}
.header_logo {
    height: 40px;
}
.header_text{
    color: #309A00;
    font-size: 18px;
    font-weight: 500;
}
</style>
