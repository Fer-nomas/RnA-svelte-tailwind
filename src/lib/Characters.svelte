<script>
    export let character;
</script>

<div class="flex flex-col max-w-sm">
   <img class="rounded-t-3xl" src={character.image} alt={character.name} >
   <div class="flex flex-col justify-center items-baseline p-2 bg-[#285430] text-[#50d71e]">
    <div>Nombre: {character.name}</div>
    <div>Especie: {character.species}</div>
    <div>Estado: {character.status}</div>
    <div>Genero: {character.gender}</div>
   </div>
  
</div>



