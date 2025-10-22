<script>
	import { Link, Mail, Github, Linkedin } from 'lucide-svelte';
</script>

<section class="section-card">
	<h2 class="section-title">
		<Link size={20} class="text-primary inline" /> Links
	</h2>
	<div class="flex flex-col space-y-1">
		<a
			href="mailto:srangisetti@usf.edu"
			class="text-text-muted py-1r flex items-center gap-2 px-2"
		>
			<Mail size={16} class="text-primary" /> srangisetti@usf.edu
		</a>
		<a
			href="https://github.com/saranRangisetti"
			target="_blank"
			rel="noopener noreferrer"
			class="text-text-muted flex items-center gap-2 px-2 py-1"
		>
			<Github size={16} class="text-primary" /> GitHub
		</a>
		<a
			href="https://www.linkedin.com/in/sai-saran-rangisetti-5791061a1/"
			target="_blank"
			rel="noopener noreferrer"
			class="text-text-muted flex items-center gap-2 px-2 py-1"
		>
			<Linkedin size={16} class="text-primary" /> LinkedIn
		</a>
	</div>
</section>
