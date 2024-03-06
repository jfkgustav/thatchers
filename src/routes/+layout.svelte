<script>
import "../app.pcss";

  import { Button } from "$lib/components/ui/button";
  import thatchers from "$lib/assets/thathchers.png";
  import * as DropdownMenu from "$lib/components/ui/dropdown-menu";
  import * as Sheet from "$lib/components/ui/sheet";
  import hamburger from "$lib/assets/hamburgare.png";
  import { mediaQuery } from "svelte-legos";

  let open = false;
  const isDesktop = mediaQuery("(min-width: 768px)");


</script>

 





  {#if $isDesktop}
  <div class="bg-local h-full" style="background-image: url({thatchers}); background-size: 100%; " >
    <div class="flex flex-wrap items-center justify-between mx-auto sm:py-16 px-12 bg-transparent">
      <div>
        <Button variant="link" class="font-bold text-xl text-white" href="/">Hem</Button>
      </div>
      <div>
        <Button variant="link" class="font-bold text-xl text-white" href="/music">Musik</Button>
      </div>
      <div>
        <Button variant="link" class="font-bold text-xl text-white" href="/images">Bilder</Button>
      </div>
      <div>
        <Button variant="link" class="font-bold text-xl text-white" href="/films">Filmer</Button>
      </div>
      <DropdownMenu.Root>
        <DropdownMenu.Trigger class="font-bold text-xl text-white">Kontakt</DropdownMenu.Trigger>
        <DropdownMenu.Content>
          <DropdownMenu.Group>
            <DropdownMenu.Label>Kontakta oss!</DropdownMenu.Label>
            <DropdownMenu.Separator />
            <DropdownMenu.Item>Mail: <a href="mailto:thatchersavar@gmail.com" class="pl-2 text-blue-900">thatchersavar@gmail.com</a></DropdownMenu.Item>
            <DropdownMenu.Item>Telefon: <a href="tel:0730204696" class="pl-2 text-blue-900">073 020 46 96</a></DropdownMenu.Item>
            <DropdownMenu.Item>Instagram: <a href="https://www.instagram.com/thatchersband" class="pl-2 text-blue-900">@thatchersband</a></DropdownMenu.Item>
            <DropdownMenu.Item>Facebook: <a href="https://www.facebook.com/thatchersband" class="pl-2 text-blue-900">Thatchers</a></DropdownMenu.Item>
          </DropdownMenu.Group>
        </DropdownMenu.Content>
      </DropdownMenu.Root>
      <div>
        <Button variant="link" class="font-bold text-xl text-white" href="/about">Om</Button>
      </div>
      
    </div>
    
    
    <div class="h-screen"> 
    <slot />
    </div>
  </div>
 
  {:else}
  <div class="bg-local h-full">
  
  <div class=" bg-white">
  <Sheet.Root>
    <Sheet.Trigger asChild let:builder>
      <div class="flex justify-between items-center">
      <Button variant="link" class="font-bold text-xl" href="/">
        Hem
      </Button>
      <Button builders={[builder]} variant="link" class="w-1/4 m-2 mr-0">
        <img src={hamburger} alt="meny">
      </Button>
    </div>
    </Sheet.Trigger>
    <Sheet.Content side="right" class="h-fit w-full">
      <Sheet.Close asChild let:builder>
      <div class="text-center pt-0">
        <div>
          <Button builders={[builder]} variant="link" class="font-bold text-xl" href="/">Hem</Button>
        </div>
        <div>
          <Button builders={[builder]} variant="link" class="font-bold text-xl" href="/music">Musik</Button>
        </div>
        <div>
          <Button builders={[builder]} variant="link" class="font-bold text-xl" href="/images">Bilder</Button>
        </div>
        <div>
          <Button builders={[builder]} variant="link" class="font-bold text-xl" href="/films">Filmer</Button>
        </div>
        <div>
          <Button builders={[builder]} variant="link" class="font-bold text-xl" href="/about">Om</Button>
        </div>
        <hr class="mt-5">
        <div>
          <h1 class="font-bold text-xl my-3" >Kontakta oss!</h1>
        </div>
        <table class="px-10 text-left mx-auto">
          <tr>
            <th><h2 class="font-bold text-md ">Mail:</h2></th>
            <th><a href="mailto:thatchersavar@gmail.com" class="ml-10 text-blue-900">thatchersavar@gmail.com</a></th>
          </tr>
          <tr>
            <th><h2 class="font-bold text-md ">Telefon: </h2>
            <th><a href="tel:0730204696" class="ml-10 text-blue-900">073 020 46 96</a></th>
          </tr>
          <tr>
            <th><h2 class="font-bold text-md ">Instagram: </h2>
            <th><a href="https://www.instagram.com/thatchersband" class="ml-10 text-blue-900">@thatchersband</a></th>
          </tr>
          <tr>
            <th><h2 class="font-bold text-md ">Facebook: </h2>
            <th><a href="https://www.facebook.com/thatchersband" class="ml-10 text-blue-900">Thatchers</a></th>
          </tr>
        </table>
      </div>
      </Sheet.Close>
      <Sheet.Footer class="items-center">
        <Sheet.Close asChild let:builder>
          <Button builders={[builder]} type="submit" class="w-1/4 font-bold" variant="ghost"></Button>
        </Sheet.Close>
      </Sheet.Footer>
    </Sheet.Content>
  </Sheet.Root>
  </div>

    <div class="h-screen"> 
      <slot />
     </div>
  </div>   
  {/if}

