<script lang="ts">
  import "../app.css";
  import BackgroundImage from "$lib/components/BackgroundImage.svelte";
</script>

<style>
  h1 {
    font-size: 72px;
    font-family: Arial;
    font-weight: 900;
    padding-left: 2vw;
    padding-top: 2vh;
    color: white;
    text-transform: capitalize;
  }
</style>

<BackgroundImage
  width="100%"
  height="100vh"
  src="bananas"
  alt="Some bananas against a yellow background."
>
  <h1>Bananas</h1>
</BackgroundImage>
