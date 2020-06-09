<template>
  <footer class="site-footer">
    {{ $siteConfig.siteName }} &copy; {{ new Date().getFullYear() }} - All
    Rights Reserved
    <br />
    <a href="https://www.linkedin.com/in/harshitkumar197/"> Made with <span style="color: #e25555;">&#9829;</span> By HK </a>
	<div class="social">
	<font-awesome-icon icon="fab fa-twitter" /><font-awesome-icon icon="fab fa-facebook-square" /><font-awesome-icon icon="fab fa-instagram" /><font-awesome-icon icon="fab fa-whatsapp" /><font-awesome-icon icon="fab fa-youtube" />
  </footer>
</template>

<script>
export default {
  name: 'SiteFooter'
}
</script>

<style scoped>
footer {
  background: #eee;
  padding: 20px 10px;
  text-align: center;
  transition: 0.5s ease all;
}
</style>
