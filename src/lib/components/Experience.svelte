<!--
Experience Component

Professional experience showcase with company details, roles, and key achievements.
Features clean timeline layout with company logos and detailed descriptions.
-->

<script lang="ts">
	import { Briefcase, Calendar, MapPin, ExternalLink } from 'lucide-svelte';

	interface ExperienceItem {
		company: string;
		position: string;
		location: string;
		period: string;
		description: string;
		achievements: string[];
		website?: string;
	}

	const experiences: ExperienceItem[] = [
		{
			company: 'American Fidelity',
			position: 'Data Science Intern',
			location: 'Oklahoma City, OK',
			period: 'Aug 2025 - Present',
			description: 'Design and build enterprise-grade AI chatbots using OpenAI models integrated with Python/Django and Vue.js.',
			achievements: [
				'Implement autonomous decision-making capabilities so chatbots can complete complex workflows without manual intervention',
				'Develop APIs and backend logic to handle conversations, workflows, and AI responses',
				'Manage databases for storing conversations, chatbot states, and user interactions',
				'Work with Enterprise Data & Innovation team on integration, predictive modeling, BI dashboards, and automation initiatives'
			],
			website: 'https://www.americanfidelity.com'
		},
		{
			company: 'Zensar Technologies',
			position: 'Senior Software Developer',
			location: 'Remote',
			period: 'Apr 2024 - Aug 2024',
			description: 'Spearheaded the design and development of interactive dashboard solutions with React and SQL.',
			achievements: [
				'Designed and integrated RESTful APIs with PostgreSQL/MySQL databases to support dynamic dashboards and reporting features',
				'Improved front-end performance and UI consistency through reusable component libraries and responsive layouts',
				'Optimized back-end query execution and implemented caching strategies to reduce latency and improve scalability',
				'Collaborated in Agile sprints, performing code reviews, unit/integration testing, and ensuring software quality across the stack'
			],
			website: 'https://www.zensar.com'
		},
		{
			company: 'PwC (PricewaterhouseCoopers)',
			position: 'Associate 2',
			location: 'Remote',
			period: 'Aug 2022 - Dec 2023',
			description: 'Led front-end architecture and enhancements in the Guidewire PolicyCenter interface.',
			achievements: [
				'Focused on accessibility, responsiveness, and user personalization, resulting in improved user experience and increased user engagement',
				'Built automation workflows by connecting front-end forms to back-end services for vehicle history report retrieval, reducing processing time',
				'Diagnosed and resolved high-priority system bugs across Guidewire modules, collaborating with backend engineers and QA testers',
				'Delivered internal tech talks and documentation walkthroughs to improve team familiarity with Guidewire infrastructure',
				'Mentored junior developers by guiding them through onboarding processes and reviewing their code contributions'
			],
			website: 'https://www.pwc.com'
		},
		{
			company: 'PwC (PricewaterhouseCoopers)',
			position: 'Associate',
			location: 'Remote',
			period: 'Sep 2021 - Aug 2022',
			description: 'Played a foundational role in developing a multi-purpose dashboard used across several Guidewire client implementations.',
			achievements: [
				'Reduced redundant development cycles through reusable dashboard components',
				'Conducted comprehensive usability testing sessions with clients and developers, collecting qualitative feedback to drive UI enhancements',
				'Earned Guidewire Associate Certification, gaining hands-on experience with ClaimCenter and BillingCenter modules',
				'Supported sprint planning and cross-border team collaboration, bridging development efforts between India and U.S. teams',
				'Involved in the entire SDLC for multiple Guidewire implementations, contributing to both technical planning and hands-on coding'
			],
			website: 'https://www.pwc.com'
		}
	];
</script>

<section class="section-card">
	<h2 class="section-title flex items-center gap-2">
		<Briefcase size={20} class="text-primary inline" /> Professional Experience
	</h2>

	<div class="experience-timeline">
		{#each experiences as experience, index (experience.company + experience.period)}
			<div class="experience-item">
				<div class="experience-header">
					<div class="experience-company">
						<h3 class="company-name">{experience.company}</h3>
						<p class="position-title">{experience.position}</p>
					</div>
					<div class="experience-meta">
						<div class="meta-item">
							<Calendar size={14} class="text-primary" />
							<span class="meta-text">{experience.period}</span>
						</div>
						<div class="meta-item">
							<MapPin size={14} class="text-primary" />
							<span class="meta-text">{experience.location}</span>
						</div>
						{#if experience.website}
							<a
								href={experience.website}
								target="_blank"
								rel="noopener noreferrer"
								class="meta-link"
							>
								<ExternalLink size={14} class="text-primary" />
								<span class="meta-text">Website</span>
							</a>
						{/if}
					</div>
				</div>

				<div class="experience-content">
					<p class="experience-description">{experience.description}</p>
					
					<div class="achievements-section">
						<h4 class="achievements-title">Key Achievements:</h4>
						<ul class="achievements-list">
							{#each experience.achievements as achievement}
								<li class="achievement-item">{achievement}</li>
							{/each}
						</ul>
					</div>
				</div>
			</div>
		{/each}
	</div>
</section>

<style>
	.experience-timeline {
		display: flex;
		flex-direction: column;
		gap: var(--space-6);
	}

	.experience-item {
		padding: var(--space-4);
		border: 1px solid var(--color-border);
		border-radius: 8px;
		background: var(--color-bg-primary);
		transition: all 0.3s ease;
	}

	.experience-item:hover {
		border-color: var(--color-primary);
		box-shadow: 0 4px 12px -2px rgba(201, 42, 42, 0.1);
		transform: translateY(-2px);
	}

	.experience-header {
		display: flex;
		justify-content: space-between;
		align-items: flex-start;
		margin-bottom: var(--space-4);
		gap: var(--space-4);
	}

	.experience-company {
		flex: 1;
	}

	.company-name {
		font-size: 1.1rem;
		font-weight: 700;
		color: var(--color-text);
		margin: 0 0 var(--space-1) 0;
	}

	.position-title {
		font-size: 0.95rem;
		font-weight: 600;
		color: var(--color-primary);
		margin: 0;
	}

	.experience-meta {
		display: flex;
		flex-direction: column;
		gap: var(--space-2);
		align-items: flex-end;
		min-width: 200px;
	}

	.meta-item,
	.meta-link {
		display: flex;
		align-items: center;
		gap: var(--space-2);
		font-size: 0.875rem;
		color: var(--color-text-muted);
		text-decoration: none;
		transition: color 0.3s ease;
	}

	.meta-link:hover {
		color: var(--color-primary);
	}

	.meta-text {
		font-size: 0.875rem;
	}

	.experience-content {
		display: flex;
		flex-direction: column;
		gap: var(--space-4);
	}

	.experience-description {
		color: var(--color-text);
		line-height: 1.6;
		font-size: 0.95rem;
		margin: 0;
	}

	.achievements-section {
		display: flex;
		flex-direction: column;
		gap: var(--space-2);
	}

	.achievements-title {
		font-size: 0.9rem;
		font-weight: 600;
		color: var(--color-text);
		margin: 0;
		text-transform: uppercase;
		letter-spacing: 0.5px;
	}

	.achievements-list {
		margin: 0;
		padding-left: var(--space-4);
		display: flex;
		flex-direction: column;
		gap: var(--space-2);
	}

	.achievement-item {
		color: var(--color-text);
		line-height: 1.5;
		font-size: 0.9rem;
		position: relative;
	}

	.achievement-item::marker {
		color: var(--color-primary);
	}

	/* Mobile responsiveness */
	@media (max-width: 768px) {
		.experience-header {
			flex-direction: column;
			align-items: flex-start;
			gap: var(--space-3);
		}

		.experience-meta {
			align-items: flex-start;
			min-width: auto;
			width: 100%;
		}

		.meta-item,
		.meta-link {
			justify-content: flex-start;
		}

		.experience-item {
			padding: var(--space-3);
		}

		.achievements-list {
			padding-left: var(--space-3);
		}
	}
</style>
