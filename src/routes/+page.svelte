<script>
  import ImageInput from "$lib/components/ImageInput.svelte";
  import PageHeader from "$lib/components/header.svelte";
</script>

<PageHeader />
<div class="flex flex-col min-h-screen">
  <div class="py-20">
    <body class="text-3xl text-center blocky-font">Craftify</body>
    <body class="text-8xl col-span-4 text-center blocky-font">
      Turn yourself into a <span class="text-green-300"
        >Minecraft Character
      </span>
    </body>
  </div>

  <div class="flex w-full justify-center items-center">
    <ImageInput
      class="text-left"
      label="Image"
      id="image-input"
      accept="image/png, image/jpeg"
    />
  </div>
</div>

<style>
  @import url("https://fonts.googleapis.com/css2?family=VT323&display=swap");

  /* Use the font in your CSS */
  .blocky-font {
    font-family: "VT323", monospace;
  }
</style>
