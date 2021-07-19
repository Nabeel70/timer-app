<script>
	import Spinner from './Spinner.svelte'
	import CountdownTimer from './CountdownTimer.svelte'
	import { timers } from './stores.js'

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
<header class="nk-header page-header is-transparent is-sticky is-shrink is-dark" id="header">
    <!-- Header @s -->
    <div class="header-main">
      <div class="header-container container">
        <div class="header-wrap">
          <!-- Logo @s -->
          <div class="header-logo logo animated" data-animate="fadeInDown" data-delay=".65">
            <a href="./" class="logo-link">
              <img class="logo-dark" src="images/logo.png" srcset="images/logo2x.png 2x" alt="logo" />
              <img class="logo-light" src="images/logo-white.png" srcset="images/logo-white2x.png 2x" alt="logo" />
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
                <li class="menu-item"><a class="menu-link nav-link" href="#news">RU RDY?</a></li>
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
    <!-- .header-main @e -->
    <!-- Banner @s -->
    <div class="header-banner bg-theme-dark">
      <div class="nk-banner">
        <div class="banner banner-mask-fix banner-fs banner-single tc-light">
          <div class="banner-wrap">
            <div class="container">
              <div class="row align-items-center justify-content-center gutter-vr-30px">
                <div class="col-lg-6 order-lg-last">
                  <div class="banner-gfx banner-gfx-re-s3 animated" data-animate="fadeInUp" data-delay="1.25">
                    <img src="images/dark/gfx-d-dark.png" alt="header" />
                    <img class="banner-gfx-icon banner-gfx-icon-1" src="images/icons/icon-custom.png" alt="" />
                    <img class="banner-gfx-icon banner-gfx-icon-2" src="images/icons/icon-custom.png" alt="" />
                  </div>
                </div>
                <div class="col-lg-6">
                  <div class="banner-caption wide-auto text-center text-lg-left">
                    <div class="cpn-head mt-0">
                      <h1 class="title title-xl-2 title-semibold animated" data-animate="fadeInUp" data-delay="1.35">
                        Join the Bunny Force
                      </h1>
                    </div>
                    <div class="cpn-text cpn-text-s1">
                      <p class="lead animated" data-animate="fadeInUp" data-delay="1.45">
                        Rocket Bunny combines the most sought after tokenomics across DeFi: automatic liquidity adds,
                        compounding yield, deflationary supply, liquidity rewards, and price shock protection.
                      </p>
                    </div>
                    <div class="cpn-btns">
                      <ul class="btn-grp animated" data-animate="fadeInUp" data-delay="1.55">
                        <li>
                          <a
                            href="https://app.uniswap.org/#/swap?outputCurrency=0x3Ea50B7Ef6a7eaf7E966E2cb72b519C16557497c"
                            target="_blank"
                            class="btn btn-md btn-grad btn-round">Get $BUNNY</a
                          >
                        </li>
                      </ul>
                    </div>
                    <div class="cpn-social">
                      <ul class="social">
                        <li class="animated" data-animate="fadeInUp" data-delay="1.85">
                          <a href="https://t.me/RocketBunnyChat" target="_blank"
                            ><em class="social-icon fab fa-telegram"></em></a
                          >
                        </li>
                        <li class="animated" data-animate="fadeInUp" data-delay="1.7">
                          <a href="https://twitter.com/RocketBunny2021" target="_blank"
                            ><em class="social-icon fab fa-twitter"></em></a
                          >
                        </li>
                        <li class="animated" data-animate="fadeInUp" data-delay="1.9">
                          <a href="https://rocketbunny.medium.com/" target="_blank"
                            ><em class="social-icon fab fa-medium-m"></em></a
                          >
                        </li>
                        <li class="animated" data-animate="fadeInUp" data-delay="1.75">
                          <a href="https://www.youtube.com/channel/UCyaV80BMsZPoT_bxPZ_rg4Q" target="_blank"
                            ><em class="social-icon fab fa-youtube"></em></a
                          >
                        </li>
                      </ul>
                    </div>
                  </div>
                </div>
                <!-- .col -->
              </div>
              <!-- .row -->
            </div>
          </div>
        </div>
      </div>
      <!-- .nk-banner -->
      <div class="nk-ovm mask-c-dark shape-v mask-contain-bottom"></div>

      <!-- Place Particle Js -->
      <div
        id="particles-bg"
        class="particles-container particles-bg"
        data-pt-base="#af3a2b"
        data-pt-base-op=".3"
        data-pt-line="#ffffff"
        data-pt-line-op=".5"
        data-pt-shape="#af3a2b"
        data-pt-shape-op=".2"
      ></div>
    </div>
    <!-- .header-banner @e -->
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
