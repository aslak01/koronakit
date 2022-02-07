<script>
  import Select from 'svelte-select'
  import { countries as items } from '$lib/utils/searchcountries.js'

  export let selectedValue

  // $: console.log(selectedValue)
</script>

<div class="themed">
  <Select {items} bind:selectedValue isClearable={false} showIndicator={true} />
</div>

<style>
  .themed {
    --itemColor: #333;
    --itemIsActiveColor: #333;
    color: #333;
    width: 20%;
    min-width: 200px;
    max-width: 500px;
    display: inline-block;
  }
</style>
