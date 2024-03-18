<template>
  <nav>
    <div class="nav-item">
      <a href="#">Sign Up</a>
      <a href="#">Log In</a>
    </div>
  </nav>
</template>
<script lang="ts">
export default {
  name:"Navbar"
}
</script>

<style>

nav .nav-item{
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 1rem;
  color: white;
  margin-left: 250px;
}
nav .nav-item a{
  color: inherit;
  position: relative;
  background-color: transparent;
}

nav .nav-item a::before{
  content: "";
  position: absolute;
  bottom: 0px;
  left: 0px;
  right: 0px;
  border: 0.5px solid white;
  transform: scaleX(0);
  transition: transform 300ms ease-in-out;

}
nav .nav-item a:hover::before{
  transform: scaleX(1);
}

</style>
