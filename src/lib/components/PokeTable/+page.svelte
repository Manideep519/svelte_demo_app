<script>
  import {
    Card,
    Table,
    TableBody,
    TableBodyCell,
    TableBodyRow,
    TableHead,
    TableHeadCell,
    Spinner,
  } from "flowbite-svelte";

  let tableCellClass = "px-8 py-2 text-center mx-auto";

  let allUrls = [];
  let allPromises = [];
  let pokemonData = [];

  async function fetchPokemon() {
    fetch("https://pokeapi.co/api/v2/pokemon")
      .then((res) => res.json())
      .then(async (res) => {
        allUrls = res.results.map((pokemon) => pokemon.url);
      });
  }
  fetchPokemon();

  $: {
    if (pokemonData.length === 0) {
      allPromises = allUrls.map((url) => fetch(url).then((res) => res.json()));
      Promise.all(allPromises).then((res) => {
        res?.forEach((pokemon) => {
          console.log(pokemon.name);
          pokemonData.push({
            id: pokemon.id,
            name: pokemon.name,
            image: pokemon.sprites.other.dream_world.front_default,
            weight: pokemon.weight,
            cry: pokemon.cries.latest,
          });
          pokemonData = pokemonData;
        });
      });
    }
  }
</script>

<Card class="my-8 max-w-full">
  <Table noborder={false} shadow striped={true}>
    <TableHead class="bg-gray-100">
      <TableHeadCell class={`${tableCellClass} text-lg capitalize`}>Pokemon</TableHeadCell>
      <TableHeadCell class={`${tableCellClass} text-lg capitalize`}>Name</TableHeadCell>
      <TableHeadCell class={`${tableCellClass} text-lg capitalize`}
        >Weight <small>(kgs)</small></TableHeadCell
      >
      <TableHeadCell class={`${tableCellClass} text-lg capitalize`}>Cry</TableHeadCell>
    </TableHead>

    <TableBody>
      {#if pokemonData.length !== 0}
        <div class="flex w-full justify-center items-center h-24">
          <Spinner />
          <p>Loading Pokemons</p>
        </div>
      {:else}
        {#each pokemonData as pokemon}
          <TableBodyRow>
            <TableBodyCell tdClass={tableCellClass}
              ><img
                class="h-24 max-w-20"
                src={pokemon.image}
                alt={`Image of ${pokemon.name}`}
              /></TableBodyCell
            >
            <TableBodyCell
              tdClass={`${tableCellClass} text-lg font-semibold dark:text-white capitalize`}
            >
              {pokemon.name}
            </TableBodyCell>
            <TableBodyCell
              tdClass={`${tableCellClass} text-2xl font-semibold dark:text-white capitalize`}
              >{Math.round(pokemon.weight * 0.1)}</TableBodyCell
            >
            <TableBodyCell tdClass={tableCellClass}>
              <audio controls>
                <source src={pokemon?.cry} type="audio/ogg" />
                Your browser does not support the audio element.
              </audio>
            </TableBodyCell>
          </TableBodyRow>
        {/each}
      {/if}
    </TableBody>
  </Table>
</Card>
