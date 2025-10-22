<!--
Featured Projects Component

Showcases major external and GitHub projects.
Complements the LatestLabs component by focusing on production/GitHub projects
rather than interactive browser-based labs.
-->

<script lang="ts">
	import { FolderGit } from 'lucide-svelte';
	import MiniProjectCard from './MiniProjectCard.svelte';
</script>

<section class="section-card">
	<h2 class="section-title flex items-center gap-2">
		<FolderGit size={20} class="text-primary inline" /> Featured Projects
	</h2>
	<div class="flex flex-col gap-6">
		<MiniProjectCard
			title="Trackr - AI Career Co-Pilot"
			description="Intelligent career companion that combines AI-driven insights, automation, and analytics to revolutionize job search experience. Features smart job aggregation, application tracking, AI resume assistance, and career analytics."
			tech={['React', 'Django', 'OpenAI', 'LangChain', 'PostgreSQL', 'AWS', 'Docker']}
			repo="https://github.com/saranRangisetti"
		/>

		<MiniProjectCard
			title="AI Recycling Detection & Classification"
			description="Smart Classification of Recyclables Using Barcode and Photoluminescence. AI-powered system that uses photoluminescence signals to identify material properties of plastic waste after barcode scanning."
			tech={['Python', 'Machine Learning', 'Scikit-learn', 'XGBoost', 'Photoluminescence']}
			repo="https://github.com/saranRangisetti"
		/>

		<MiniProjectCard
			title="Toxic Comments Classification"
			description="Built and fine-tuned DistilBERT and DeBERTa models for multi-label toxic comment classification on 160k+ samples from the Jigsaw dataset. Applied Focal Loss, Label Smoothing, and FGSM adversarial training."
			tech={['Python', 'Deep Learning', 'DistilBERT', 'DeBERTa', 'Gradio', 'Transformers']}
			repo="https://github.com/saranRangisetti/Identify-Categorize-Toxic-Comments-Online-Using-Deep-Learning-"
		/>

		<MiniProjectCard
			title="Saran-os - Desktop Environment"
			description="Desktop environment in the browser built with JavaScript. Interactive web-based desktop experience with modern UI components and responsive design."
			tech={['JavaScript', 'HTML', 'CSS', 'Web Technologies']}
			repo="https://github.com/saranRangisetti/Saran-os"
		/>

		<MiniProjectCard
			title="Smart Inventory Management System"
			description="Comprehensive inventory management solution with real-time tracking, automated reordering, and analytics dashboard for efficient business operations."
			tech={['Python', 'Django', 'PostgreSQL', 'React', 'AWS']}
			repo="https://github.com/saranRangisetti/Smart-Inventory-Management-System"
		/>
	</div>
</section>
