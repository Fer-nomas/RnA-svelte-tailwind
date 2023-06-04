<script>
  import Characters from "./lib/Characters.svelte";
    let characters =[]
    let page = 1
    async function loadData(){
      const response = await fetch("https://rickandmortyapi.com/api/character?page="+ page)
      const data = await response.json()
      characters = await data.results
      console.log(characters)
   }
  function previusBtn() {
    page--
    loadData()
  }
  function nextBtn() {
    page++
    loadData()
  }
   loadData();
   
</script>
<div class="overflow-x-hidden flex flex-col justify-center items-center bg-[#224B0C]">
  <h1 class="m-10 text-5xl text-white font-bold p-10 border-4 border-white">Personajes de Rick and Morty</h1>
  <div class="m-2 flex justify-between items-center w-10/12">
      <button class="py-3 px-5 border-2 border-white text-white" on:click={previusBtn} disabled={page === 1}>Anterior</button>
      <button class="py-3 px-5 border-2 border-white text-white" on:click={nextBtn}>Siguiente</button>
  </div>
  <div class="flex w-screen flex-wrap justify-center items-center gap-5">
    {#each characters as character}
       <Characters character={character}/>
    {/each}
  </div>
</div>


<style>
  :global(body){
    font-family: 'Open Sans', sans-serif;
    font-family: 'Poppins', sans-serif;
  }
</style>
