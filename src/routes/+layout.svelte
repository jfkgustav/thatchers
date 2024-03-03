<script>
import "../app.pcss";

  import { Button } from "$lib/components/ui/button";
  import thatchers from "$lib/assets/thathchers.png";
  import * as DropdownMenu from "$lib/components/ui/dropdown-menu";

</script>

 




<div class="bg-local h-full" style="background-image: url({thatchers}); background-size: 100%;
background-repeat: no-repeat; " >
  <div class="flex flex-wrap items-center justify-between mx-auto py-16 px-12 bg-transparent">
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
