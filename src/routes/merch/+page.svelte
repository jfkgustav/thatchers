<script>

  import gray_tshirt from "$lib/assets/gray_tshirt.png";
  import black_tshirt from "$lib/assets/black_tshirt.png";
  import navy_tshirt from "$lib/assets/navy_tshirt.png";
  import sticker from "$lib/assets/sticker.png";
  import allting from "$lib/assets/allting_ordnar_sig.jpg";
  import bygg from "$lib/assets/bygg.jpg";
  import pollen from "$lib/assets/pollen.jpg";
  import fran from "$lib/assets/fran_savar.jpg";
  let name = '';
  let email = '';
  let address = '';
  let postNr = '';
  let city = '';
  let order = '';
  let status = '';

  async function handleSubmit() {
    const response = await fetch('https://formspree.io/f/mblovwnr', {
      method: 'POST',
      headers: {
        'Accept': 'application/json',
        'Content-Type': 'application/json'
      },
      body: JSON.stringify({ name, email, order, address, postNr, city })
    });

    if (response.ok) {
      status = 'Meddelandet har skickats!';
      name = email = order = city = address = postNr = '';
    } else {
      status = 'Något gick fel, försök igen.';
    }
  }
</script>
<div class="container h-screen overflow-y-scroll flex flex-col bg-slate-200 py-8 rounded-lg">

  <h1 class="text-4xl font-bold">MERCH</h1>
  <p class ="text-xl my-4">På denna sida kan du "beställa" merch genom att kika på vad vi har för merch och därefter skriva en beställning i rutan där nere som heter "önskad beställning". Därefter kan du fylla i dina uppgifter och skicka beställningen genom att klicka på "skicka". Då får vi ett mejl och kommer granska beställningen och höra av oss till dig så att vi kan komma överens hur vi gör med frakt och betalning.</p>
  <p class ="text-xl my-4"> Just nu säljer vi dessa 8 produkter: </p>
  <div class="grid grid-cols-2 sm:grid-cols-4 gap-4">
    <div class="flex flex-col mx-auto text-center">
      <img width="200px" src={gray_tshirt}>
      <p>T-shirt grå</p>
      <p>S, M, L, XL</p>
      <p>250kr</p>
    </div>
    <div class="flex flex-col mx-auto text-center">
      <img width="200px" src={navy_tshirt}>
      <p>T-shirt blå</p>
      <p>S, M, L, XL</p>
      <p>250kr</p>
    </div>
    <div class="flex flex-col mx-auto text-center">
      <img width="200px" src={black_tshirt}>
      <p>T-shirt svart</p>
      <p>S, M, L, XL</p>
      <p>250kr</p>
    </div>
    <div class="flex flex-col mx-auto text-center">
      <img width="200px" src={sticker}>
      <p>Allting ordnar sig sticker</p>
      <p class="font-bold">Ingår i alla köp</p>
    </div>
    <div class="flex flex-col mx-auto text-center">
      <img width="200px" src={bygg}>
      <p>Bygg låtar med Thatchers CD</p>
      <p>100kr</p>
    </div>
    <div class="flex flex-col mx-auto text-center">
      <img width="200px" src={fran}>
      <p>Från Sävar</p>
      <p>CD</p>
      <p>100kr</p>
    </div>
    <div class="flex flex-col mx-auto text-center">
      <img width="200px" src={pollen}>
      <p>Pollen</p>
      <p>CD</p>
      <p>100kr</p>
    </div>
    <div class="flex flex-col mx-auto text-center">
      <img width="200px" src={allting}>
      <p>Allting ordnar sig</p>
      <p>CD</p>
      <p>100kr</p>
    </div>
  </div>
  <strong class="text-center mb-12">Paketpris för alla fyra CDs är 350kr</strong>

<form on:submit|preventDefault={handleSubmit} class="flex flex-col">

  <label class="flex flex-col mb-4 ">
    <h2 class="font-bold">Önskad beställning:</h2>
    <textarea placeholder="Skriv här vad du vill beställa :)" bind:value={order} class="p-4"></textarea>
  </label>

  <div class="flex flex-col">
    <h2 class="font-bold">Leveransuppgifter</h2>
    <label class="my-4 grid grid-cols-2">
      E-post:
      <input type="email" bind:value={email} required />
    </label>
    <label class="my-4 grid grid-cols-2">
      Namn:
      <input type="text" bind:value={name} required />
    </label>
    <label class="my-4 grid grid-cols-2" >
      Adress:
      <input type="text" bind:value={address} required />
    </label>
    <label class="my-4 grid grid-cols-2">
      Postnummer:
      <input type="text" bind:value={postNr} required />
    </label>
    <label class="my-4 grid grid-cols-2">
      Stad:
      <input type="text" bind:value={city} required />
    </label>
  </div>
  <button class="bg-white my-4" type="submit">Skicka</button>
</form>

{#if status}
  <p>{status}</p>
{/if}


</div>
