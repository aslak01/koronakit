<script>
  // import { getData } from '$lib/utils/fetch.js'
  import { getData2 } from '$lib/utils/fetch1.js'
  import MiniJHday from '$lib/MiniJHday.svelte'

  export let country
  // export let index;

  let req = getData2(
    'https://disease.sh/v3/covid-19/historical/' + country + '?lastdays=all'
  )

  async function getData() {
    let response = await fetch(
      'https://countriesnow.space/api/v0.1/countries/population',
      {
        method: 'POST',
        headers: {
          'Content-Type': 'application/x-www-form-urlencoded'
        },
        body: new URLSearchParams({
          iso3: country
        })
      }
    )
    let data = await response.json()
    return data
  }

  let cData = getData()

  // let cData = getData(
  //   'https://restcountries.eu/rest/v2/alpha/' +
  //     country +
  //     '?fields=population;nativeName'
  // )
</script>

{#await $req}...{:then data}
  {#await cData}...{:then cData}
    <MiniJHday {country} {data} {cData} />
  {/await}
{/await}
