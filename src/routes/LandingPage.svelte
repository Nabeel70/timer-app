<script>
	import Spinner from '../Spinner.svelte'
	import CountdownTimer from '../CountdownTimer.svelte'
	import { timers } from '../stores.js'
	import { v4 as uuidv4 } from 'uuid'

	// import Spinner from './Spinner.svelte';
  import { onMount } from 'svelte';

  let ready = false;

  onMount(() => {
    setTimeout(() => {
      ready = true;
    }, 2000);
  });
	timers.useLocalStorage()

	let name = ''
	let date = null
	let time = null
	let validated = false
	let errors = []
	let showForm = false

	function deleteTimer() {
        let index = $timers.findIndex(element => {
            element.id === timer.id
        })

        $timers.splice(index, 1)

		timers.set($timers)
    }

	function handleClick(e) {

		validated = true

		errors = []

		if (name.length === 0) {
			errors.push('You must provide an event name')
		}
		if (!date) {
			errors.push('You must provide a date')
		}

		date = `${date} ${time || ''}`
		if (new Date(date) < new Date()) {
			errors.push('The specified date and time has already occurred')
		}

		if (errors.length === 0) {
			showForm = false
			$timers.push({
				id: uuidv4(),
				event: name,
				date: date
			})

			timers.set($timers)

			validated = false
		}
	}

</script>
<header>
<div class="nk-wrap">
	<header class="nk-header page-header is-transparent is-sticky is-shrink is-dark" id="header">
	  <!-- Header @s -->
	  <div class="header-main">
		<div class="header-container container">
		  <div class="header-wrap">
			<!-- Logo @s -->
			<div class="header-logo logo animated" data-animate="fadeInDown" data-delay=".65">
			  <a href="./" class="logo-link">
				<img class="logo-dark" src="../../public/images/logo.png" srcset="../../public/images/logo2x.png 2x" alt="logo" />
				<img class="logo-light" src="../../public/images/logo-white.png" srcset="../../public/images/logo-white2x.png 2x" alt="logo" />
			  </a>
			</div>
  
			<!-- Menu Toogle @s -->
			<div class="header-nav-toggle">
			  <!-- svelte-ignore a11y-invalid-attribute -->
			  <a href="#" class="navbar-toggle" data-menu-toggle="example-menu-04">
				<div class="toggle-line">
				  <span></span>
				</div>
			  </a>
			</div>
  
			<!-- Menu @s -->
			<div class="header-navbar header-navbar-s1">
			  <nav class="header-menu" id="example-menu-04">
				<ul class="menu menu-s2 animated" data-animate="fadeInDown" data-delay=".75">
				  <li class="menu-item"><a class="menu-link nav-link" href="#ico">About</a></li>
				  <li class="menu-item"><a class="menu-link nav-link" href="#token">Tokenomics</a></li>
				  <li class="menu-item"><a class="menu-link nav-link" href="#roadmap">Roadmap</a></li>
				  <li class="menu-item"><a class="menu-link nav-link" href="#news">News</a></li>
				  <li class="menu-item"><a class="menu-link nav-link" href="#LandingPage">RU RDY?</a></li>
				  <li class="menu-item">
					<a class="menu-link nav-link" href="https://pbom.rocketbunny.io/wrap.html">Wrap $BUNNY</a>
				  </li>
				</ul>
				<ul class="menu-btns animated" data-animate="fadeInDown" data-delay=".85">
				  <li>
					<a
					  href="https://drop.rocketbunny.io/"
					  target="_blank"
					  class="btn btn-rg btn-auto btn-outline btn-grad on-bg-theme btn-round"><span>ROCKET DROP</span></a
					>
				  </li>
				</ul>
			  </nav>
			</div>
			<!-- .header-navbar @e -->
		  </div>
		</div>
	  </div>
	  </div>
	</header>
<br><br> <br> <br> <br><br> <br> <br> <br><br> <br>
<div class="uk-container" style="text-align: center;">

	<div>
		{#if showForm}
			<div class="uk-align-center uk-width-1-3 uk-background-default">
				<form autocomplete="off" class="uk-padding">
					<label for="event" class="uk-text-bold">Event name</label>
					<input type="text" name="name" id="name" bind:value={name}
						on:input={(e) => { validated = false }}
						class="uk-input uk-margin-bottom"
						class:warning="{validated && name.length === 0}">
					
					<label for="date" class="uk-text-bold">Date</label>
					<input type="date" id="date" name="date" bind:value={date}
						on:input={(e) => { validated = false }}
						class="uk-input uk-margin-bottom"
						class:warning="{validated && !date}">
					
					<label for="time" class="uk-text-bold">Time</label>
					<input type="time" id="time" name="time" bind:value={time} class="uk-input uk-margin-bottom">
					<button on:click|preventDefault={handleClick} class="uk-button uk-button-primary">Create</button>
					<button on:click={(e) => showForm = false } class="uk-button uk-button-default">Cancel</button>
				</form>

				{#if errors.length > 0}
					<div class="uk-padding">
						{#each errors as error}
							<p class="error">{error}</p>
						{/each}
					</div>
				{/if}
			</div>
		{:else}
			<button type="button" class="btn btn-rg btn-auto btn-outline btn-grad on-bg-theme btn-round" on:click={(e) => {
				name = ''
				date = ''
				showForm = true
			}}>
				Let's Add a new countdown<span uk-icon="icon: arrow-right"></span>
			</button>
		{/if}
	</div>

	<div class="uk-grid">
		{#each $timers as timer}
			<CountdownTimer timer={timer} />
		{/each}
	</div>
</div>
<br><br><br>
<footer class="nk-footer bg-theme-alt section-connect">
    <div class="section section-m pb-0 tc-light ov-h">
      <div class="section section-footer section-s tc-light bg-transparent">
        <div class="container">
          <!-- Block @s -->
          <div class="nk-block block-footer">
            <div class="row">
              <div class="col">
                <div class="wgs wgs-text text-center mb-3">
                  <ul class="social pdb-m justify-content-center">
                    <li>
                      <a href="https://t.me/RocketBunnyChat" target="_blank">
                        <em class="social-icon fab fa-telegram"></em>
                      </a>
                    </li>
                    <li>
                      <a href="https://twitter.com/RocketBunny2021" target="_blank">
                        <em class="social-icon fab fa-twitter"></em>
                      </a>
                    </li>
                    <li>
                      <a href="https://rocketbunny.medium.com/" target="_blank">
                        <em class="social-icon fab fa-medium-m"></em>
                      </a>
                    </li>
                    <li>
                      <a href="https://www.youtube.com/channel/UCyaV80BMsZPoT_bxPZ_rg4Q" target="_blank">
                        <em class="social-icon fab fa-youtube"></em>
                      </a>
                    </li>
                  </ul>
                  <div class="copyright-text copyright-text-s3 pdt-m">
                    <p><span class="d-sm-block">Copyright &copy; 2021, <a href="./">ROCKET BUNNY</a></span></p>
                  </div>
                </div>
              </div>
            </div>
          </div>
          <!-- .block @e -->
        </div>
      </div>
    </div>
  </footer>
{#if !ready}
  <Spinner />
{/if}
