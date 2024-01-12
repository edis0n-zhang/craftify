<script>
  import LightSwitch from "$lib/components/LightSwitch.svelte";
  import { Lightbulb } from "lucide-svelte";

  function handleClick() {
    window.location.href = "https://edisonzhang.me/";
  }
</script>

<div class="navbar sticky w-full p-4 flex justify-between">
  <button class="flex items-center" on:click={handleClick}>
    <Lightbulb class="h-[2rem] w-[2rem] hover:fill-yellow-500" />
    <p class="font-bold font:Montserrat">edison zhang</p>
  </button>
  <LightSwitch />
</div>

<style>
  @import url("https://fonts.googleapis.com/css2?family=Montserrat&display=swap");
</style>
