<script lang="ts">
  import { writable } from "svelte/store";
  import { Button, buttonVariants } from "$lib/components/ui/button";
  import * as Dialog from "$lib/components/ui/dialog";
  import { Input } from "$lib/components/ui/input";
  import { Label } from "$lib/components/ui/label";

  const openAIToken = writable(""); // Create a Svelte store
  openAIToken.set("Not Set");

  function saveToken(event: SubmitEvent) {
    event.preventDefault();
    const formData = new FormData(event.target as HTMLFormElement);
    const token = formData.get("token") as string;
    openAIToken.set(token); // Update the store with the new token
  }
</script>

<Dialog.Root>
  <Dialog.Trigger
    class="{buttonVariants({
      variant: 'outline',
    })} dark:bg-green-500 hover:bg-green-500 dark:hover:bg-green-600 min-h-14 text-white hover:text-white bg-green"
  >
    <p class="text-3xl">OpenAI API Token</p>
  </Dialog.Trigger>
  <Dialog.Content class="sm:max-w-[425px]">
    <Dialog.Header>
      <Dialog.Title>OpenAI API Token</Dialog.Title>
      <Dialog.Description>
        Select your OpenAI API Token. You can find it <a
          href="https://platform.openai.com/api-keys"
          class="text-blue-400 hover:underline">here</a
        >.
      </Dialog.Description>
    </Dialog.Header>
    <form class="grid gap-4" on:submit={saveToken}>
      <div class="flex-row">
        <Label for="token">Token</Label>
        <Input id="token" name="token" />
      </div>
      <Dialog.Footer>
        <Button type="submit">Save changes</Button>
      </Dialog.Footer>
    </form>
  </Dialog.Content>
</Dialog.Root>
