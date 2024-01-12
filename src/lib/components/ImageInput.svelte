<script lang="ts">
  import { Input } from "$lib/components/ui/input";
  import { Label } from "$lib/components/ui/label";

  export let label = "Picture";
  export let id = "picture";
  export let accept = "image/*"; // Default to accepting all image types

  let selectedFile;

  function handleFileChange(event) {
    const files = event.target.files;
    if (files.length > 0) {
      selectedFile = files[0];
      // Do something with the newly selected file
    }
  }
</script>

<div class="grid w-full max-w-sm items-center">
  <Label class="text-left pb-1.5" for={id}>{label}</Label>
  <Input
    {id}
    type="file"
    {accept}
    on:change={handleFileChange}
    class="hidden"
  />
</div>
