<script lang="ts">
	import '../app.css';
	import { onNavigate } from '$app/navigation';
	import Header from '$lib/components/Header.svelte';
	import Footer from '$lib/components/Footer.svelte';

	let { children } = $props();

	// Use the native View Transitions API for smooth page transitions
	onNavigate((navigation) => {
		if (!document.startViewTransition) return;

		return new Promise((resolve) => {
			document.startViewTransition(async () => {
				resolve();
				await navigation.complete;
			});
		});
	});
</script>

<svelte:head>
	<meta charset="utf-8" />
	<meta name="viewport" content="width=device-width, initial-scale=1" />
	<meta
		name="description"
		content="Sai Saran Rangisetti - Full-Stack Software Developer in Tampa, FL. Building web applications, AI systems, and interactive experiences. Specializing in Python, React, Django, AWS, and modern development practices."
	/>
	<meta
		name="keywords"
		content="software developer Tampa, full stack developer Tampa, Tampa web developer, Florida programmer, software engineer Tampa, Python developer, React developer, Django developer, remote developer Tampa, web development Tampa, software development Tampa, AI developer Tampa"
	/>
	<meta name="author" content="Sai Saran Rangisetti" />
	<meta name="robots" content="index, follow" />
	<meta name="language" content="en" />
	<meta name="geo.region" content="US-FL" />
	<meta name="geo.placename" content="Tampa, FL" />
	<meta name="geo.position" content="27.9506;-82.4572" />
	<meta name="ICBM" content="27.9506, -82.4572" />
	<title>Sai Saran Rangisetti - Data Scientist & AI Specialist</title>

	<!-- Open Graph -->
	<meta
		property="og:title"
		content="Sai Saran Rangisetti - Data Scientist & AI Specialist"
	/>
	<meta
		property="og:description"
		content="Data Scientist and AI Specialist creating intelligent systems, machine learning models, and data-driven solutions. Available for remote collaboration worldwide."
	/>
	<meta property="og:type" content="website" />
	<meta property="og:url" content="https://anishshrestha.com" />
	<meta property="og:site_name" content="Sai Saran Rangisetti" />
	<meta property="og:locale" content="en_US" />

	<!-- Twitter Card -->
	<meta name="twitter:card" content="summary" />
	<meta name="twitter:title" content="Sai Saran Rangisetti - Data Scientist & AI Specialist" />
	<meta
		name="twitter:description"
		content="Data Scientist and AI Specialist creating intelligent systems, machine learning models, and data-driven solutions."
	/>

	<!-- JSON-LD Schema -->
	<script type="application/ld+json">
		{
			"@context": "https://schema.org",
			"@type": "Person",
			"name": "Sai Saran Rangisetti",
			"jobTitle": "Software Developer",
			"description": "Full-stack software developer specializing in web applications, AI systems, and interactive experiences. Expert in Python, React, Django, AWS, and modern development practices.",
			"url": "https://anishshrestha.com",
			"sameAs": ["https://github.com/saranRangisetti", "https://www.linkedin.com/in/sai-saran-rangisetti-5791061a1/"],
			"address": {
				"@type": "PostalAddress",
				"addressLocality": "Tampa",
				"addressRegion": "FL",
				"addressCountry": "US"
			},
			"knowsAbout": [
				"Software Development",
				"Full-Stack Development",
				"Web Development",
				"Go Programming",
				"Python Development",
				"JavaScript",
				"TypeScript",
				"SvelteKit",
				"React",
				"Node.js",
				"PostgreSQL",
				"Distributed Systems",
				"Software Architecture",
				"API Design",
				"DevOps",
				"Docker",
				"Linux",
				"AWS",
				"Algorithm Design",
				"Data Structures"
			],
			"workLocation": {
				"@type": "Place",
				"name": "Remote / Kathmandu, Nepal"
			},
			"hasOccupation": {
				"@type": "Occupation",
				"name": "Software Developer",
				"occupationLocation": {
					"@type": "Country",
					"name": "Nepal"
				},
				"skills": [
					"Full-Stack Development",
					"Backend Development",
					"Frontend Development",
					"Web Application Development",
					"Distributed Systems",
					"Software Architecture",
					"Algorithm Implementation",
					"Database Design",
					"API Development",
					"DevOps Practices"
				]
			}
		}
	</script>
	<script
		defer
		src="https://cloud.umami.is/script.js"
		data-website-id="b7abb816-2b4e-4807-bddb-f31649532505"
	></script>
</svelte:head>

<div class="flex min-h-screen flex-col">
	<Header />

	<div class="flex-1">
		{@render children()}
	</div>
	<Footer />
</div>
