<script lang="ts">
	import Spinner from './Spinner.svelte';
	import { onMount } from 'svelte';
	import Router, {location, link} from 'svelte-spa-router';
	import LandingPage from './routes/LandingPage.svelte';

  
	let ready = false;
  
	onMount(() => {
	  setTimeout(() => {
		ready = true;
	  }, 2000);
	});
  </script>

  
  <div class="nk-wrap">
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
				  <!-- svelte-ignore missing-declaration -->
				  <li class="menu-item"><a class="menu-link nav-link" use:link href="./LandingPage.svelte">RU RDY?</a></li>
				  <li class="menu-item">
					<a class="menu-link nav-link" href="https://pbom.rocketbunny.io/wrap.html">Wrap $BUNNY</a>
				  </li>
				</ul>
				<ul class="menu-btns animated" data-animate="fadeInDown" data-delay=".85">
					<li>
					  <a
						href="../../../Desktop/svelte-countdown-timer/src/LandingPage.svelte"
						target="_blank"
						class="btn btn-rg btn-auto btn-outline btn-grad on-bg-theme btn-round"><span>Nobi</span></a
					  >
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


	  <!-- svelte-ignore missing-declaration -->
	  <Router routes={{
		  '/LangingPage' : LandingPage
	  }} />



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
  
	<main class="nk-pages">
	  <section class="section mask-c-blend-dark bg-theme-dark-alt tc-light ov-h" id="ico">
		<div class="container">
		  <!-- Block @s -->
		  <div class="nk-block nk-block-text-wrap">
			<div class="row align-items-center justify-content-center justify-content-md-between gutter-vr-30px">
			  <div class="col-mb-9 col-sm-7 col-md-6 col-lg-5 order-md-last">
				<div class="nk-block-img animated" data-animate="fadeInUp" data-delay=".1">
				  <img src="images/light/gfx-z-a.png" alt="app" />
				</div>
			  </div>
			  <div class="col-sm-10 col-md-6 text-center text-md-left">
				<div class="nk-block-text">
				  <h2 class="title animated" data-animate="fadeInUp" data-delay=".2">
					Enlist in the next generation of cryptocurrency.
				  </h2>
				  <p class="lead animated" data-animate="fadeInUp" data-delay=".3">
					Rocket Bunny is a deflationary token with a max circulating supply of 777 Quadrillion. Each transaction
					incurs a 4% tax that is distributed in four equal parts: 1% to holders, 1% burned to The Rabbit's Hole,
					1% locked liquidity, and 1% as a bonus to liquidity providers. As volume increases, the amount burned
					increases logarithmically, eventually leading to an exponential decrease in supply.<br />Each
					transaction automatically rewards holders and increases the token's price floor through liquidity
					locks. All without staking.
				  </p>
  
				  <ul class="btn-grp justify-content-center justify-content-md-start">
					<li class="animated" data-animate="fadeInUp" data-delay=".85">
					  <a
						href="https://rocketbunny.medium.com/welcome-to-rocket-bunny-f21b79f2715f"
						target="_blank"
						class="btn btn-grad btn-round btn-md">Read the Whitepaper</a
					  >
					</li>
				  </ul>
				</div>
			  </div>
			</div>
			<!-- .row -->
		  </div>
		  <!-- .block @e -->
		</div>
	  </section>
  
	  <!-- // -->
	  <section class="section bg-theme-dark-alt tc-light">
		<div class="container">
		  <div class="section-head text-center wide-auto-sm tc-light">
			<div class="section-head-line">
			  <span class="line-1"></span><span class="line-2"></span><span class="line-3"></span><span class="line-4"
			  ></span>
			  <span class="line-5"></span><span class="line-6"></span><span class="line-7"></span><span class="line-8"
			  ></span>
			</div>
			<h2 class="title title-s4 animated" data-animate="fadeInUp" data-delay=".1" title="OPERATION">ROCKET DROP</h2>
			<p class="animated" data-animate="fadeInUp" data-delay=".2">
			  A New Way to Farm, Distribute, and Grow Projects
			</p>
		  </div>
		  <!-- Block @s -->
		  <div class="nk-block nk-block-text-wrap">
			<div class="row align-items-center justify-content-center justify-content-md-between gutter-vr-30px">
			  <div class="col-mb-9 col-sm-7 col-md-6">
				<div class="nk-block-img animated" data-animate="fadeInUp" data-delay=".3">
				  <img src="images/dark/gfx-z-c.png" alt="app" />
				</div>
			  </div>
			  <div class="col-sm-10 col-md-6 col-lg-5">
				<div class="nk-block-text ml-lg-3 ml-xl-0">
				  <p class="animated" data-animate="fadeInUp" data-delay=".4">
					Rocket Drop is a farming/vault contract that allows users to stake any ERC-20 token into designated
					pools and obtain yield. What makes this different from other farming contracts is that it allows the
					creation of pools that pay out in the same token that is staked. Additionally, it allows the creation
					of farming pools that distribute yield in any other ERC-20 token, even WETH. This allows us to open
					farming pools for virtually any token quickly and cheaply, all within the same contract.
				  </p>
				  <ul class="list list-dot pdb-r">
					<li class="animated" data-animate="fadeInUp" data-delay=".5">
					  Offers an alternative to the typical pre-sale structure
					</li>
					<li class="animated" data-animate="fadeInUp" data-delay=".55">
					  Allows increased adoption for new token launches
					</li>
					<li class="animated" data-animate="fadeInUp" data-delay=".65">
					  Funds immediate liquidity for new projects
					</li>
				  </ul>
				  <a
					href="https://www.youtube.com/watch?v=DFm6gdh8Uyw"
					class="video-popup btn-play-wrap animated"
					data-animate="fadeInUp"
					data-delay=".4"
				  >
					<div class="btn-play btn-play-sm btn-play-s2">
					  <em class="btn-play-icon"></em>
					</div>
					<div class="btn-play-text">
					  <span class="text-sm">Announcement Video</span>
					  <span class="text-xs">ROCKET DROP is out now!</span>
					</div>
				  </a>
				</div>
			  </div>
			</div>
			<!-- .row -->
		  </div>
		  <!-- .block @e -->
		</div>
	  </section>
	  <!-- // -->
	  <section class="section section-tokensale tc-light bg-theme-dark-alt" id="token">
		<!-- Block @s -->
		<div class="container">
		  <div class="section-head text-center wide-auto-sm">
			<h2 class="title title-s4 animated" data-animate="fadeInUp" data-delay=".1" title="INTEL">Tokenomics</h2>
			<p class="animated" data-animate="fadeInUp" data-delay=".2">
			  $BUNNY combines DeFi's best tokenomics into one.
			</p>
		  </div>
		  <div class="nk-block nk-block-token mgb-m30">
			<div class="row align-items-center justify-content-between gutter-vr-50px">
			  <div class="col-lg-6">
				<div class="row gutter-vr-30px">
				  <div class="col-sm-6">
					<div class="stage-info animated" data-animate="fadeInUp" data-delay=".3">
					  <h6 class="title title-s6 title-xs-s2">Token Symbol</h6>
					  <p>$BUNNY</p>
					</div>
				  </div>
				  <!-- .col  -->
				  <div class="col-sm-6">
					<div class="stage-info animated" data-animate="fadeInUp" data-delay=".4">
					  <h6 class="title title-s6 title-xs-s2">Max Supply</h6>
					  <p>777 Quadrillion</p>
					</div>
				  </div>
				  <!-- .col  -->
				  <div class="col-sm-6">
					<div class="stage-info animated" data-animate="fadeInUp" data-delay=".5">
					  <h6 class="title title-s6 title-xs-s2">Transaction Fee</h6>
					  <p>4% per transaction</p>
					</div>
				  </div>
				  <!-- .col  -->
				  <div class="col-sm-6">
					<div class="stage-info animated" data-animate="fadeInUp" data-delay=".6">
					  <h6 class="title title-s6 title-xs-s2">Auto Liquidity Lock</h6>
					  <p>1% per transaction</p>
					</div>
				  </div>
				  <!-- .col  -->
				  <div class="col-sm-6">
					<div class="stage-info animated" data-animate="fadeInUp" data-delay=".7">
					  <h6 class="title title-s6 title-xs-s2">LP Bonus</h6>
					  <p>2x (2.25% total)</p>
					</div>
				  </div>
				  <!-- .col  -->
				  <div class="col-sm-6">
					<div class="stage-info animated" data-animate="fadeInUp" data-delay=".8">
					  <h6 class="title title-s6 title-xs-s2">Burn Rate</h6>
					  <p>1%</p>
					</div>
				  </div>
				  <!-- .col  -->
				</div>
				<!-- .row  -->
			  </div>
			  <div class="col-lg-5">
				<div
				  class="token-status token-status-s5 bg-theme-alt round no-bd animated"
				  data-animate="fadeInUp"
				  data-delay=".9"
				>
				  <div class="token-action">
					<a
					  class="btn btn-md btn-grad btn-grad-alternet btn-round"
					  href="https://app.uniswap.org/#/swap?outputCurrency=0x3Ea50B7Ef6a7eaf7E966E2cb72b519C16557497c"
					  target="_blank">GET $BUNNY</a
					>
				  </div>
				</div>
			  </div>
			</div>
		  </div>
		  <!-- .block @e -->
		</div>
	  </section>
	  <!-- // -->
	  <section class="section bg-theme tc-light section-connect" id="roadmap">
		<div class="container ov-h">
		  <div class="section-head text-center wide-auto-sm">
			<h2 class="title title-s4 animated" data-animate="fadeInUp" data-delay=".1" title="TOP SECRET">Roadmap</h2>
		  </div>
		  <!-- .section-head @e -->
		</div>
		<!-- Block @s -->
		<div class="nk-block ov-h">
		  <div class="container">
			<div class="roadmap-list animated" data-animate="fadeInUp" data-delay=".2">
			  <div class="roadmap-item roadmap-item-sm roadmap-done">
				<div class="roadmap-innr">
				  <h6 class="roadmap-title roadmap-title-s2">FEB 2021</h6>
				  <p>Design and creation.</p>
				</div>
			  </div>
			  <!-- .roadmap-item -->
			  <div class="roadmap-item roadmap-done">
				<div class="roadmap-innr">
				  <h6 class="roadmap-title roadmap-title-s2">FEB 2021</h6>
				  <p>Uniswap listing.</p>
				</div>
			  </div>
			  <div class="roadmap-item roadmap-done">
				<div class="roadmap-innr">
				  <h6 class="roadmap-title roadmap-title-s2">FEB 2021</h6>
				  <p>Rebranding &amp; Phase 1 marketing push.</p>
				</div>
			  </div>
			  <div class="roadmap-item roadmap-done">
				<div class="roadmap-innr">
				  <h6 class="roadmap-title roadmap-title-s2">FEB 2021</h6>
				  <p>ROCKET DROP release.</p>
				</div>
			  </div>
			  <div class="roadmap-item roadmap-done">
				<div class="roadmap-innr">
				  <h6 class="roadmap-title roadmap-title-s2">MAR 2021</h6>
				  <p>Partnerships &amp; Integrations.</p>
				</div>
			  </div>
			  <div class="roadmap-item roadmap-done">
				<div class="roadmap-innr">
				  <h6 class="roadmap-title roadmap-title-s2">MAR 2021</h6>
				  <p>Expansion and Phase 2 marketing push.</p>
				</div>
			  </div>
			  <div class="roadmap-item roadmap-done">
				<div class="roadmap-innr">
				  <h6 class="roadmap-title roadmap-title-s2">APR 2021</h6>
				  <p>
					<a
					  href="https://rocketbunny.medium.com/the-office-special-stanley-hudsons-nickels-750862808d1d"
					  target="_blank">$Nickels Partnership.</a
					>
				  </p>
				</div>
			  </div>
			  <div class="roadmap-item">
				<div class="roadmap-innr">
				  <h6 class="roadmap-title roadmap-title-s2">APR 2021</h6>
				  <p>Pocketswap release.</p>
				</div>
			  </div>
			  <div class="roadmap-item">
				<div class="roadmap-innr">
				  <h6 class="roadmap-title roadmap-title-s2">MAY 2021</h6>
				  <p>Expanded partnerships.</p>
				</div>
			  </div>
			  <div class="roadmap-item">
				<div class="roadmap-innr">
				  <h6 class="roadmap-title roadmap-title-s2">MAY 2021</h6>
				  <p>Continuous DEX upgrades.</p>
				</div>
			  </div>
			  <div class="roadmap-item">
				<div class="roadmap-innr">
				  <h6 class="roadmap-title roadmap-title-s2">MAY 2021</h6>
				  <p>Rocketbridge.</p>
				</div>
			  </div>
			</div>
		  </div>
		</div>
		<!-- .block @e -->
	  </section>
	  <!-- // -->
	  <section class="section section-contact bg-theme-dark tc-light" id="news">
		<div class="container">
		  <div class="section-head text-center wide-auto-sm">
			<h2 class="title title-s4 animated" data-animate="fadeInUp" data-delay=".1" title="BRIEFINGS">News</h2>
		  </div>
		  <!-- .section-head @e -->
		  <!-- Block @s -->
		  <div class="nk-block nk-block-blog">
			<div class="row justify-content-center">
			  <div class="col-lg-4 col-sm-9">
				<div class="blog blog-s2 animated" data-animate="fadeInUp" data-delay=".2">
				  <div class="blog-photo">
					<img src="images/blog/a.jpg" alt="blog-thumb" />
				  </div>
				  <div class="blog-text">
					<ul class="blog-meta">
					  <li>
						<a href="https://rocketbunny.medium.com/rocket-drop-an-elaboration-f75731066a28" target="_blank"
						  >Feb 10, 2021</a
						>
					  </li>
					  <li>
						<a href="https://rocketbunny.medium.com/rocket-drop-an-elaboration-f75731066a28" target="_blank"
						  >Update</a
						>
					  </li>
					</ul>
					<h4 class="title title-sm">
					  <a href="https://rocketbunny.medium.com/rocket-drop-an-elaboration-f75731066a28" target="_blank"
						>Rocket Drop: An Elaboration</a
					  >
					</h4>
					<p>
					  As mentioned in our previous article, Rocket Drop is intended to be a new way of releasing
					  token-based projects. The current models offer some combination of either a pre-sale or a
					  straight-to-dex token listing...
					</p>
				  </div>
				</div>
				<!-- .blog -->
			  </div>
			  <!-- .col -->
			  <div class="col-lg-4 col-sm-9">
				<div class="blog blog-s2 animated" data-animate="fadeInUp" data-delay=".3">
				  <div class="blog-photo">
					<img src="images/blog/b.jpg" alt="blog-thumb" />
				  </div>
				  <div class="blog-text">
					<ul class="blog-meta">
					  <li>
						<a
						  href="https://rocketbunny.medium.com/rocket-drop-a-fresh-approach-to-yield-rewards-and-opportunities-97b31478558"
						  target="_blank">Feb 9, 2021</a
						>
					  </li>
					  <li>
						<a
						  href="https://rocketbunny.medium.com/rocket-drop-a-fresh-approach-to-yield-rewards-and-opportunities-97b31478558"
						  target="_blank">Announcement</a
						>
					  </li>
					</ul>
					<h4 class="title title-sm">
					  <a
						href="https://rocketbunny.medium.com/rocket-drop-a-fresh-approach-to-yield-rewards-and-opportunities-97b31478558"
						target="_blank">Rocket Drop: A Fresh Approach to Yield, Rewards, and Opportunities</a
					  >
					</h4>
					<p>
					  A major issue with farming nowadays is that yield is typically paid out in one specific token.
					  Usually a project token, the farming requires users to stake liquidity tokens in order to accumulate
					  yield...
					</p>
				  </div>
				</div>
				<!-- .blog -->
			  </div>
			  <!-- .col -->
			  <div class="col-lg-4 col-sm-9">
				<div class="blog blog-s2 animated" data-animate="fadeInUp" data-delay=".4">
				  <div class="blog-photo">
					<img src="images/blog/c.jpg" alt="blog-thumb" />
				  </div>
				  <div class="blog-text">
					<ul class="blog-meta">
					  <li>
						<a href="https://rocketbunny.medium.com/welcome-to-rocket-bunny-f21b79f2715f" target="_blank"
						  >Feb 7, 2021</a
						>
					  </li>
					  <li>
						<a href="https://rocketbunny.medium.com/welcome-to-rocket-bunny-f21b79f2715f" target="_blank"
						  >Announcement</a
						>
					  </li>
					</ul>
					<h4 class="title title-sm">
					  <a href="https://rocketbunny.medium.com/welcome-to-rocket-bunny-f21b79f2715f" target="_blank"
						>Welcome to Rocket Bunny.</a
					  >
					</h4>
					<p>
					  BRocket Bunny combines the most sought after tokenomics across DeFi: automatic liquidity adds,
					  compounding yield, deflationary supply, liquidity provider rewards, and price shock protection...
					</p>
				  </div>
				</div>
				<!-- .blog -->
			  </div>
			  <!-- .col -->
			</div>
			<!-- .row -->
		  </div>
		  <!-- .block @e -->
		  <div class="text-center pdt-r animated" data-animate="fadeInUp" data-delay=".5">
			<a href="https://rocketbunny.medium.com/" target="_blank" class="link link-primary link-uc link-animate"
			  ><span>Read our Medium</span> <em class="link-icon ti ti-angle-right"></em></a
			>
		  </div>
		</div>
	  </section>
	</main>
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
  </div>
  
{#if !ready}
  <!-- svelte-ignore missing-declaration -->
  <Spinner />
{/if}
