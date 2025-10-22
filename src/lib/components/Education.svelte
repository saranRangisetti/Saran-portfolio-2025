<!--
Education Component

Educational background showcase with degree details, coursework, and achievements.
Features clean layout with institution information and academic highlights.
-->

<script lang="ts">
	import { GraduationCap, Calendar, MapPin, Award, BookOpen } from 'lucide-svelte';

	interface EducationItem {
		institution: string;
		degree: string;
		field: string;
		location: string;
		period: string;
		description: string;
		coursework: string[];
		achievements?: string[];
		website?: string;
	}

	const education: EducationItem[] = [
		{
			institution: 'University of South Florida',
			degree: 'Master of Science',
			field: 'Artificial Intelligence and Business Analytics',
			location: 'Tampa, FL',
			period: 'Aug 2024 - Dec 2026',
			description: 'Pursuing advanced studies in AI and business analytics with focus on machine learning, deep learning, and data-driven decision making.',
			coursework: [
				'Machine Learning',
				'Deep Learning',
				'Business Analytics',
				'Data Mining',
				'Statistical Analysis'
			],
			achievements: [
				'Independent Study – AI Recycling Detection & Classification',
				'Smart Classification of Recyclables Using Barcode and Photoluminescence',
				'Collaborated on AI-powered system for material property identification'
			],
			website: 'https://www.usf.edu'
		},
		{
			institution: 'Chaitanya Bharathi Institute of Technology',
			degree: 'Bachelor of Technology',
			field: 'Information Technology',
			location: 'Hyderabad, India',
			period: 'Aug 2017 - Jun 2021',
			description: 'Comprehensive undergraduate program covering software engineering, database systems, web technologies, and computer science fundamentals.',
			coursework: [
				'Data Structures and Algorithms',
				'Database Management Systems',
				'Software Engineering',
				'Computer Networks',
				'Web Technologies',
				'Operating Systems'
			],
			website: 'https://www.cbit.ac.in'
		}
	];
</script>

<section class="section-card">
	<h2 class="section-title flex items-center gap-2">
		<GraduationCap size={20} class="text-primary inline" /> Education
	</h2>

	<div class="education-timeline">
		{#each education as edu, index (edu.institution + edu.period)}
			<div class="education-item">
				<div class="education-header">
					<div class="education-institution">
						<h3 class="institution-name">{edu.institution}</h3>
						<p class="degree-title">{edu.degree} in {edu.field}</p>
					</div>
					<div class="education-meta">
						<div class="meta-item">
							<Calendar size={14} class="text-primary" />
							<span class="meta-text">{edu.period}</span>
						</div>
						<div class="meta-item">
							<MapPin size={14} class="text-primary" />
							<span class="meta-text">{edu.location}</span>
						</div>
						{#if edu.website}
							<a
								href={edu.website}
								target="_blank"
								rel="noopener noreferrer"
								class="meta-link"
							>
								<Award size={14} class="text-primary" />
								<span class="meta-text">Website</span>
							</a>
						{/if}
					</div>
				</div>

				<div class="education-content">
					<p class="education-description">{edu.description}</p>
					
					<div class="coursework-section">
						<div class="section-header">
							<BookOpen size={16} class="text-primary" />
							<h4 class="section-title">Relevant Coursework</h4>
						</div>
						<div class="coursework-tags">
							{#each edu.coursework as course}
								<span class="coursework-tag">{course}</span>
							{/each}
						</div>
					</div>

					{#if edu.achievements}
						<div class="achievements-section">
							<div class="section-header">
								<Award size={16} class="text-primary" />
								<h4 class="section-title">Key Achievements</h4>
							</div>
							<ul class="achievements-list">
								{#each edu.achievements as achievement}
									<li class="achievement-item">{achievement}</li>
								{/each}
							</ul>
						</div>
					{/if}
				</div>
			</div>
		{/each}
	</div>
</section>

<style>
	.education-timeline {
		display: flex;
		flex-direction: column;
		gap: var(--space-6);
	}

	.education-item {
		padding: var(--space-4);
		border: 1px solid var(--color-border);
		border-radius: 8px;
		background: var(--color-bg-primary);
		transition: all 0.3s ease;
	}

	.education-item:hover {
		border-color: var(--color-primary);
		box-shadow: 0 4px 12px -2px rgba(201, 42, 42, 0.1);
		transform: translateY(-2px);
	}

	.education-header {
		display: flex;
		justify-content: space-between;
		align-items: flex-start;
		margin-bottom: var(--space-4);
		gap: var(--space-4);
	}

	.education-institution {
		flex: 1;
	}

	.institution-name {
		font-size: 1.1rem;
		font-weight: 700;
		color: var(--color-text);
		margin: 0 0 var(--space-1) 0;
	}

	.degree-title {
		font-size: 0.95rem;
		font-weight: 600;
		color: var(--color-primary);
		margin: 0;
	}

	.education-meta {
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

	.education-content {
		display: flex;
		flex-direction: column;
		gap: var(--space-4);
	}

	.education-description {
		color: var(--color-text);
		line-height: 1.6;
		font-size: 0.95rem;
		margin: 0;
	}

	.coursework-section,
	.achievements-section {
		display: flex;
		flex-direction: column;
		gap: var(--space-3);
	}

	.section-header {
		display: flex;
		align-items: center;
		gap: var(--space-2);
	}

	.section-title {
		font-size: 0.9rem;
		font-weight: 600;
		color: var(--color-text);
		margin: 0;
		text-transform: uppercase;
		letter-spacing: 0.5px;
	}

	.coursework-tags {
		display: flex;
		flex-wrap: wrap;
		gap: var(--space-2);
	}

	.coursework-tag {
		padding: var(--space-1) var(--space-3);
		background: var(--color-bg-secondary);
		border: 1px solid var(--color-border);
		border-radius: 16px;
		font-size: 0.8rem;
		font-weight: 500;
		color: var(--color-text);
		transition: all 0.3s ease;
	}

	.coursework-tag:hover {
		background: var(--color-primary);
		color: white;
		border-color: var(--color-primary);
		transform: translateY(-1px);
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
		.education-header {
			flex-direction: column;
			align-items: flex-start;
			gap: var(--space-3);
		}

		.education-meta {
			align-items: flex-start;
			min-width: auto;
			width: 100%;
		}

		.meta-item,
		.meta-link {
			justify-content: flex-start;
		}

		.education-item {
			padding: var(--space-3);
		}

		.coursework-tags {
			gap: var(--space-1);
		}

		.coursework-tag {
			font-size: 0.75rem;
			padding: var(--space-1) var(--space-2);
		}

		.achievements-list {
			padding-left: var(--space-3);
		}
	}
</style>
