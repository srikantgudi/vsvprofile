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
    <div class="d-flex flex-column gap-1 align-items-center justify-content-around">
      <div class="display-6">Srikant Gudi</div>
      <div>Bengaluru, India</div>
      <div>
        +91 829 665 6336 | srikantgdev@gmail.com | <a href="https://linkedin.com/in/srikantgudi-blr">LinkedIN profile</a>
      </div>
      <div class="body-title">Front-end / Backend Developer</div>
      <div class="my-4">
        <button class="btn btn-sm btn-info" on:click={() => currentTab=0}>About me</button>
        <button class="btn btn-sm btn-info" on:click={() => currentTab=1}>Technical Skills</button>
        <button on:click={() => currentTab=2} class="btn btn-sm btn-info">Work Historry</button>
      </div>
    </div>

    <div class="card px-md-5 px-2 w-md-75 mx-auto">
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
