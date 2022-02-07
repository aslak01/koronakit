<script>
  import MiniWorld from '$lib/MiJHworld.svelte'
  import { getData } from '$lib/utils/fetch.js'
  const worldData = getData(
    'https://disease.sh/v3/covid-19/historical/all?lastdays=all'
  )
  const worldPop = 7832328000
</script>

{#await $worldData}...{:then worldData}
  <MiniWorld data={worldData} {worldPop} />
{/await}
