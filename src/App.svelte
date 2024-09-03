<script>
  import About from "./lib/About.svelte";
  import Skills from "./lib/Skills.svelte";
  import Workhist from "./lib/Workhist.svelte";
  
  let currentTab = 0;
  const comps = [
		{ color: 'About me', component: About },
		{ color: 'Technical Skills', component: Skills },
		{ color: 'Work History', component: Workhist }
	];
  $: currentComp = comps[currentTab];
</script>

<style>
</style>

<main class="">
  <div class="container">
    <div class="bg-dark text-white row d-flex align-items-center">
      <div class="col-md-6 col-12">
        <div class="d-flex gap-2 align-items-center">
          <div class="display-6">Srikant Gudi</div>
          <div>| Bengaluru, India</div>
        </div>
      </div>
      <div class="col-md-6 col">
        <button class="btn btn-sm btn-info" on:click={() => currentTab=0}>About me</button>
        <button class="btn btn-sm btn-info" on:click={() => currentTab=1}>Technical Skills</button>
        <button on:click={() => currentTab=2} class="btn btn-sm btn-info">Work Historry</button>
      </div>
    </div>
    <div class="card p-2">
      <div class="row">
        <div class="col-12">
          <div class="my-5">
            <svelte:component this={currentComp.component} />
          </div>
        </div>
      </div>
    </div>
  </div>
</main>
