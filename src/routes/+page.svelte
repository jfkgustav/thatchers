<script>
    import midsommar from "$lib/assets/midsommar.jpg"; 
    import sittin from "$lib/assets/sittin.png";
    import { Button } from "$lib/components/ui/button";

</script>


<div class="h-1/3 grid pt-5 sm:flex sm:justify-center sm:items-center">
  <h1 class="font-extrabold sm:-mt-10 text-5xl text-yellow-600 sm:text-white text-center">THATCHERS</h1>
  <h2 class="sm:hidden font-extrabold sm:-mt-10 text-xl sm:text-white text-center ">Bandet i Sävar</h2>
  <div class=" pt-10 text-center sm:hidden">
    <Button variant="link" class="font-bold text-md" href="/music">Musik</Button>

    <Button variant="link" class="font-bold text-md" href="/images">Bilder</Button>

    <Button variant="link" class="font-bold text-md" href="/films">Filmer</Button>
  </div>
</div>



<div>

  <img src={midsommar} alt="bild på bandet från midsommar" class="sm:hidden w-100%">

</div>

