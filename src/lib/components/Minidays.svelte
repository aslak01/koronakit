<script>
  import { getData } from '$lib/utils/fetch.js'
  import { getData2 } from '$lib/utils/fetch1.js'
  import MiniJHday from '$lib/MiniJHday.svelte'

  export let country
  // export let index;

  let req = getData2(
    'https://disease.sh/v3/covid-19/historical/' + country + '?lastdays=all'
  )

  let cData = getData(
    'https://restcountries.eu/rest/v2/alpha/' +
      country +
      '?fields=population;nativeName'
  )
</script>

{#await $req}...{:then data}
  {#await $cData}...{:then cData}
    <MiniJHday {country} {data} {cData} />
  {/await}
{/await}
