<script lang="ts">
	import ProjectCard from '$lib/components/ProjectCard.svelte';
	import TwoColumnShell from '$lib/layouts/TwoColumnShell.svelte';

	const projects = [
		{
			title: 'Trackr - AI Career Co-Pilot',
			description:
				'Intelligent career companion that combines AI-driven insights, automation, and analytics to revolutionize job search experience. Features smart job aggregation, application tracking, AI resume assistance, and career analytics.',
			tech: ['React', 'Django', 'OpenAI', 'LangChain', 'PostgreSQL', 'AWS', 'Docker'],
			repo: 'https://github.com/saranRangisetti',
			demo: null
		},
		{
			title: 'AI Recycling Detection & Classification',
			description:
				'Smart Classification of Recyclables Using Barcode and Photoluminescence. AI-powered system that uses photoluminescence signals to identify material properties of plastic waste after barcode scanning.',
			tech: ['Python', 'Machine Learning', 'Scikit-learn', 'XGBoost', 'Photoluminescence'],
			repo: 'https://github.com/saranRangisetti',
			demo: null
		},
		{
			title: 'Toxic Comments Classification',
			description:
				'Built and fine-tuned DistilBERT and DeBERTa models for multi-label toxic comment classification on 160k+ samples from the Jigsaw dataset. Applied Focal Loss, Label Smoothing, and FGSM adversarial training.',
			tech: ['Python', 'Deep Learning', 'DistilBERT', 'DeBERTa', 'Gradio', 'Transformers'],
			repo: 'https://github.com/saranRangisetti/Identify-Categorize-Toxic-Comments-Online-Using-Deep-Learning-',
			demo: null
		},
		{
			title: 'DSA Visualizer',
			description:
				'Interactive visualization of sorting algorithms and pathfinding with step-by-step animations, speed controls, and detailed statistics for learning data structures and algorithms.',
			tech: ['SvelteKit', 'TypeScript', 'Algorithms', 'Visualization'],
			repo: 'https://github.com/saranRangisetti',
			demo: '/labs/dsa-visualizer'
		},
		{
			title: 'Game of Life',
			description:
				"Conway's cellular automaton with pattern library, speed controls, and interactive grid editing. Watch evolution patterns unfold and create your own configurations.",
			tech: ['SvelteKit', 'TypeScript', 'Cellular Automata', 'Simulation'],
			repo: 'https://github.com/saranRangisetti',
			demo: '/labs/gameoflife'
		},
		{
			title: 'Tic Tac Toe with AI',
			description:
				'Interactive Tic Tac Toe game with intelligent AI opponent using minimax algorithm. Features different difficulty levels and strategic gameplay.',
			tech: ['SvelteKit', 'TypeScript', 'AI', 'Minimax', 'Game'],
			repo: 'https://github.com/saranRangisetti',
			demo: '/labs/tictactoe'
		},
		{
			title: 'Saran-os - Desktop Environment',
			description:
				'Custom desktop environment built from scratch with modern UI components, window management, and system integration features.',
			tech: ['C++', 'Linux', 'X11', 'Desktop Environment'],
			repo: 'https://github.com/saranRangisetti',
			demo: null
		}
	];

	// Removed unused techTags variable
</script>

<svelte:head>
	<title>Projects - Full-Stack Software Developer Portfolio | Sai Saran Rangisetti</title>
	<meta
		name="description"
		content="Open source projects by Sai Saran Rangisetti - Full-stack applications, web tools, algorithms, and interactive experiences. Showcasing modern software development practices from Tampa, FL."
	/>
	<meta
		name="keywords"
		content="software developer portfolio Tampa, full stack projects, web applications Tampa, open source projects, interactive demos, programming portfolio Tampa, software development showcase, AI projects"
	/>
	<meta property="og:title" content="Projects - Full-Stack Software Developer Portfolio" />
	<meta
		property="og:description"
		content="Open source projects by Sai Saran Rangisetti - Full-stack applications, web tools, algorithms, and interactive experiences from Tampa, FL."
	/>
	<meta property="og:url" content="https://anishshrestha.com/projects" />
</svelte:head>

<main class="container" style="padding-top: var(--space-8); padding-bottom: var(--space-8);">
	<TwoColumnShell>
		{#snippet left()}
			<section class="section-card">
				<h3 class="section-title text-lg">Projects</h3>
				<p class="text-text-muted text-sm leading-relaxed">
					A collection of open-source projects and personal experiments. From CLI tools and
					algorithms to web applications and games, these projects showcase different aspects of
					software development using Go, Python, and modern web technologies.
				</p>
			</section>
		{/snippet}

		<div class="w-full">
			<section class="flex flex-col" style="gap: var(--space-4); padding-bottom: var(--space-16);">
				{#each projects as p (p.title)}
					<ProjectCard
						title={p.title}
						description={p.description}
						tech={p.tech}
						repo={p.repo}
						demo={p.demo}
					/>
				{/each}
			</section>
		</div>
	</TwoColumnShell>
</main>
