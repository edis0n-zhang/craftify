<script>
  import ImageInput from "$lib/components/ImageInput.svelte";
  import PageHeader from "$lib/components/Header.svelte";
  import TokenInput from "$lib/components/TokenInput.svelte";
  import LightSwitch from "$lib/components/LightSwitch.svelte";

  import { Input } from "$lib/components/ui/input";
  import { Label } from "$lib/components/ui/label";
  import { Button } from "$lib/components/ui/button";

  let inputImageURL = "";
  let outputImageURL = "";

  let selectedFile;

  function handleFileChange(event) {
    const files = event.target.files;
    if (files.length > 0) {
      selectedFile = files[0];
    }
  }
</script>

<div class="flex flex-col max-h-screen">
  <PageHeader />
  <div class="py-20 blocky-font">
    <div class="text-4xl text-center">Craftify</div>
    <div class="text-8xl col-span-4 text-center">
      Turn yourself into a <br /><span
        class="dark:text-green-400 text-green-600">Minecraft Character</span
      >
    </div>
  </div>

  <div>
    <p class="text-3xl text-center blocky-font">
      Input your <TokenInput /> and
      <Label
        class="inline-flex items-center text-3xl px-4 py-2 bg-green-600 dark:bg-green-500 text-white rounded-md cursor-pointer hover:bg-green-500 dark:hover:bg-green-600"
        for="file-input">Upload an Image</Label
      >
      !
      <Input
        id="file-input"
        type="file"
        accept="image/*"
        on:change={handleFileChange}
        class="hidden"
      />
    </p>
  </div>

  <div class="flex justify-center items-center space-x-4 my-8">
    <div>
      <Label>Input:</Label>
      <img src={inputImageURL} alt="Image 1" class="min-w-xs max-w-xs" />
    </div>
    <div>
      <Label>Output:</Label>
      <img src={outputImageURL} alt="Image 2" class="min-w-xs max-w-xs" />
    </div>
  </div>
</div>

<style>
  @import url("https://fonts.googleapis.com/css2?family=VT323&display=swap");

  .blocky-font {
    font-family: "VT323", monospace;
  }
</style>
