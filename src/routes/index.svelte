<script>
	import { fly } from 'svelte/transition';
	import { onMount } from 'svelte';
	import { FULLPAGE_JS_API_KEY } from '../data';
	import ContactForm from '../components/ContactForm.svelte';
	//import { fullpage, fullpage_api } from 'fullpage.js';



	onMount(async() => {
		// console.log(FULLPAGE_JS_API_KEY);

		new fullpage('#fullpage', {
			//options here
			parallax: true,
			parallaxOptions: {
				type: 'reveal',
				percentage: 62,
				property: 'translate'
			},
			navigation: false,
			slidesNavigation: false,
			navigationPosition: 'right',
			slidesNavigation: 'false',
			easing: 'easeInQuart',
			menu: 'myMenu',
			anchors: ['heroAnchor', 'cardsAnchor', 'adminsAnchor', 'studentsAnchor', 'itAnchor', 'contactAnchor'],
			licenseKey: FULLPAGE_JS_API_KEY,
		});

		//methods
		//fullpage_api.setAllowScrolling(false);
		//fullpage_api.setLockAnchors(false);
	})



</script>

<style>
/*
	h1, figure, p {
		text-align: center;
		margin: 0 auto;
	}

	h1 {
		font-size: 2.8em;
		text-transform: uppercase;
		font-weight: 700;
		margin: 0 0 0.5em 0;
	}

	figure {
		margin: 0 0 1em 0;
	}

	img {
		width: 100%;
		max-width: 400px;
		margin: 0 0 1em 0;
	}

	p {
		margin: 1em auto;
	}
*/

	#students {
  	background-size: cover;
	}

	@media (min-width: 480px) {
		h1 {
			font-size: 4em;
		}
	}
</style>

<svelte:head>
	<title>Faros Education</title>
</svelte:head>

<div id="fullpage">
	<section class="hero is-fullpage is-primary is-bold section " style="margin-top: 3.25rem" data-anchor="heroAnchor">
		<div class="hero-body">
			<div class="container">
				<h1 class="title" in:fly="{{ y: -50, duration: 1000 }}">Faros Education</h1>
				<h2 class="subtitle" in:fly="{{ y: -50, duration: 1000 }}">Student Management. Registration. Advancement.</h2>
			</div>
		</div>
	</section>
	<!-- <section id="what" class="section is-fullpage is-primary" data-anchor="what">
		<quote in:fly="{{ y: -50, duration: 1000 }}">
			“75 percent of institutions are operating a system that is more than 10
			years old… Today, for many institutions, the existing Student Information
			System] SIS is increasingly in need of replacement or repair.” –
			Eduventures Research [2]
		</quote >
		<p in:fly="{{ y: -50, duration: 1000 }}">What can an upgrade do for me?</p>
		<img src="img/student-collaboration.jpg" alt="Photo by Christina Morillo from Pexels">

	</section> -->
	<section id="cards" class="section is-fullpage" data-anchor="cardsAnchor" style="background-color: #ececec;">
		<div class="columns">
			<div class="column">
				<div class="card" in:fly="{{ y: -50, duration: 1000 }}">
					<div class="card-image has-text-centered">
						<i class="mdi mdi-96px mdi-file-multiple"></i>
					</div>
					<div class="card-content">
						<div class="media">
							<div class="media-content">
								<p class="title is-4">For Administrators</p>
							</div>
						</div>
						<div class="content">
							Faros provides reduced costs, first-class student engagement
							leading to better retention.
						</div>
					</div>
					<footer class="card-footer">
						<a href="#adminsAnchor" class="card-footer-item is-success">Learn More</a>
					</footer>
				</div>
			</div>
			<div class="column">
				<div class="card" in:fly="{{ y: -50, duration: 1000 }}">
					<div class="card-image has-text-centered">
							<i class="mdi mdi-96px mdi-school"></i>
					</div>
					<div class="card-content">
						<div class="media">
							<div class="media-content">
								<p class="title is-4">For Students</p>
							</div>
						</div>
						<div class="content">
							Guided Registration ensures all students understand the system and
							how to sign up for classes. Faros systems are smart enough to
							guide you when you get lost, and simple enough to ensure you never
							do.
						</div>
					</div>
					<footer class="card-footer">
						<a href="#studentsAnchor" class="card-footer-item is-success">Learn More</a>
					</footer>
				</div>

			</div>
			<div class="column">
				<div class="card" in:fly="{{ y: -50, duration: 1000 }}">
					<div class="card-image has-text-centered">
						<i class="mdi mdi-96px mdi-cloud-sync"></i>
					</div>
					<div class="card-content">
						<div class="media">
							<div class="media-content">
								<p class="title is-4">Modern IT</p>
							</div>
						</div>
						<div class="content">
							Our cloud architecture means zero downtime, regular upgrades and
							no need for IT to maintain systems on-prem.
						</div>
					</div>
					<footer class="card-footer">
						<a href="#itAnchor" class="card-footer-item is-success">Learn More</a>
					</footer>
				</div>
			</div>
		</div>
	</section>

	<section id="administrators" class="hero section is-fullpage" data-anchor="adminsAnchor" style="background-image:url('admins.jpg'); background-size: cover;">
		<div class="hero-body">
			<div class="container">
				<div class="card" in:fly="{{ y: -50, duration: 1000 }}">
					<div class="card-content">
						<div class="media">
							<div class="media-content">
								<h3 class="title is-4">Faros is built for Administrators</h3>
							</div>
						</div>
						<div class="content">
							<p class="subtitle">
								Increase retention. Know your future needs. Reduce overhead.
							</p>
						</div>
						<p>
							Faros will revolutionize Student Information Systems by bringing first
							class data analtyics to administrators finger tips. Get a Modern ERP
							designed with you in mind.
						</p>
						<div class="columns">
							<div class="column" />
						</div>
					</div>
				</div>
			</div>
		</div>
	</section>

	<section id="students" class="hero is-fullpage section " data-anchor='studentsAnchor' style="background-image:url('student.jpg'); background-size: cover;">
		<div class="hero-body">
			<div class="container">
				<div class="card" in:fly="{{ y: -50, duration: 1000 }}">
					<div class="card-content">
						<div class="media">
							<div class="media-content">
								<h3 class="title is-4">Lead your Students to success</h3>
							</div>
						</div>
						<div class="content">
							<p class="subtitle">Designed with new students in mind</p>
							<p>
								Faros will help onboard students and walk them through the
								registration process. The guided process will instruct them on what
								they need to do, and help them understand the complexities of
								registration.
							</p>
						</div>
					</div>
				</div>
			</div>
		</div>
	</section>

	<section id="it" class="hero is-fullpage section is-fullpage" data-anchor="itAnchor" style="background-image:url('computer.jpg'); background-size: cover;">
		<div class="hero-body">
			<div class="container">
				<div class="card" in:fly="{{ y: -50, duration: 1000 }}">
					<div class="card-content">
						<div class="media">
							<div class="media-content">
								<h3 class="title is-4">Simplify your IT</h3>
							</div>
						</div>
						<div class="content">
							<p class="quote">
								"[Higher Education] institutions remain with their current ERP
								suppliers for at least the next five years as there are no alternative
								ERP cloud suppliers with viable student information systems" -Utah
								System of Higher Education, Legislative brief
							</p>
						</div>
						<ul>
							<li >No maintenance downtimes</li>
							<li >Fully customizable, using the latest frontend technologies</li>
							<li >Scales Automatically during peak times</li>
							<li >No maintenance fees, consultation fees, or other hidden fees</li>
							<li >Public GraphQL API, making custom queries fast and easy</li>
						</ul>
					</div>
				</div>
			</div>
		</div>
	</section>

	<!-- <section id="advantages" class="section">
		<div class="tile is-ancestor">
			<div class="tile is-parent">
				<article class="tile is-child box">
					<img src="img/analytics.jpg" alt="analytics" />
					<p class="title">Stunning Analytics</p>
					<p class="subtitle">What is up?</p>
					Photo by Webaroo on Unsplash
				</article>
			</div>
			<div class="tile is-parent">
				<article class="tile is-child box">
					<img src="img/design.jpg" />
					<p class="title">Innovative Design</p>
					<p class="subtitle">Bar</p>
					Photo by Med Badr Chemmaoui on Unsplash
				</article>
			</div>
			<div class="tile is-parent">
				<article class="tile is-child box">
					<img src="img/cloud-harddrives.jpg" />
					<p class="title">Maintenance Free</p>
					<p class="subtitle">Secure Cloud Architecture</p>
					<div class="content">
						<p>Photo by panumas nikhomkhai from Pexels</p>
					</div>
				</article>
			</div>
		</div>
	</section> -->

	<section id="contact-us" class="section is-fullpage" style="background-color: #ececec;" data-anchor="contactAnchor">
		<div class="container">
			<div class="columns is-centered">
				<div class="column is-6" in:fly="{{ y: -50, duration: 1000 }}">
					<ContactForm />
				</div>
			</div>

		</div>

	</section>
</div>
