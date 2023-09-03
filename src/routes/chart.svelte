<script>
  import { onMount } from 'svelte';
  import { writable } from 'svelte/store';
  import Chart from 'chart.js/auto';

  export let countryDataStore = writable([]);

  let chart;

  onMount(async () => {
    const response = await fetch('https://restcountries.com/v3.1/all');
    const data = await response.json();
    countryDataStore.set(data);
  });

  $: topCountries = $countryDataStore
    .slice()
    .sort((a, b) => b.population - a.population)
    .slice(0, 10);

  $: data = {
    labels: topCountries.map(c => c.name.common),
    datasets: [
      {
        data: topCountries.map(c => c.population),
        backgroundColor: topCountries.map(() => 
          '#' + Math.floor(Math.random() * 16777215).toString(16))
      }
    ]
  };

  $: config = {
    type: 'polarArea',
    data: data,
    options: {
      responsive: true,
      maintainAspectRatio: false, 
      top: 500,
      left: 50,
    },
  };

  onMount(() => {
    const ctx = chart.getContext('2d');
    new Chart(ctx, config);
  });


</script>
<style>
    .small-chart{
        width: 50px; 
        height: 50px;
    }
    .right-align {
        float: right;
    }
    table {
    border-collapse: collapse;
    width: 100%;
    }
    th, td {
    border: 1px solid #ddd;
    padding: 8px;
    text-align: center;
    }
    th {
    background-color: #f2f2f2;
    }
    .table-container {
    margin: 20px;
    overflow-x: auto; 
    }
</style>
<div class="table-container">
<table>
  <thead>
    <tr>
      <th>Flag</th>
      <th>Name</th>
      <th>CIOC</th>
      <th>UN Member Status</th>
      <th>Currencies</th>
      <th>Population</th>
      <th>Languages</th>  
    </tr>
  </thead>

  {#each $countryDataStore as country}
    <tr>
      <td><img src={country.flags.png} alt={country.name.common} style="width: 50px;" /></td>
      <td style="text-align: center;">{country.name.common}</td>
      <td style="text-align: center;">{country.cioc}</td>
      <td style="text-align: center;">{country.unMember ? 'Yes' : 'No'}</td>
      <td style="text-align: center;">{Object.keys(country.currencies).join(', ')}</td>
      <td style="text-align: center;">{country.population}</td>
      <td style="text-align: center;">{Object.values(country.languages).join(', ')}</td>
    </tr>
  {/each}
</table>
</div>

<div>
  <canvas bind:this={chart} class="small-chart right-align"/>
</div>