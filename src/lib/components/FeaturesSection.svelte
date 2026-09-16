<script lang="ts">
    import { IconChevronDown, IconChartCircles, IconTableImport, IconWorld, IconUsersGroup, IconDatabaseExport } from '@tabler/icons-svelte';
    import { Accordion } from '@skeletonlabs/skeleton-svelte';
	import { slide } from 'svelte/transition';
    import { base } from '$app/paths';

    const features = [
		{
			id: '0',
			title: 'Import any kind of data',
			description:
				"Bring in artefact records from spreadsheets, JSON files, museum databases exports . Ọkpan adapts to the data you already have, however incomplete or inconsistent it is.",
            imgName: 'feature0.png',
			icon: IconTableImport
                
		},
		{
			id: '1',
			title: 'Connections: situated knowledge, not fixed vocabularies',
			description:
				"Standard ontologies and vocabularies are built without the knowledge of the communities objects come from. Connections let you attach Indigenous designations, oral histories, and cultural context directly to a record: knowledge that doesn't need to fit inside someone else's classification system to count.",
            imgName: 'feature1.png',
			icon: IconChartCircles
		},
		{
			id: '2',
			title: 'Build your catalogue, publish it online',
			description:
				"Turn imported and enriched records into a structured catalogue, and publish it as a public website others can browse, search, and cite. No separate web project required.",
            imgName: 'feature2.png',
			icon: IconWorld
		},
        {
			id: '3',
			title: 'Offline-first, built for collaboration',
			description:
				"Work on your catalogue without an internet connection when you need to, then sync and collaborate with partner institutions, researchers, and communities when you're back online.",
            imgName: 'feature3.png',
			icon: IconUsersGroup
		},
        {
			id: '4',
			title: 'Publish enriched, open datasets',
			description:
				"Share your enriched collection as structured, reusable data, so the knowledge you've gathered can travel beyond your own catalogue and support research elsewhere.",
            imgName: 'feature4.png',
			icon: IconDatabaseExport
		}
	];

    let selected = $state(features[0].id);
</script>


<section class="container mx-auto py-48 px-16 grid grid-cols-12 gap-16">
    <div class="col-span-12 lg:col-span-7">
        <img 
            src={`${base}/imgs/${features[parseInt(selected)].imgName}`}
            alt={features[parseInt(selected)].title}
			class="hidden lg:inline"
        >
    </div>


    <div class="col-span-12 lg:col-span-5 flex flex-col gap-16 lg:pl-48">
    <Accordion value={[selected]} onValueChange={(details) => (selected = details.value[0])} class='gap-8'>
	    {#each features as feature, i (feature)}
		    
            <Accordion.Item value={feature.id} class='rounded-lg'>
			    <h3>
				    <Accordion.ItemTrigger class="flex items-center gap-12 p-16 lg:py-24 group">
						<div class="btn p-4 rounded-lg h-fit group-data-[state=open]:preset-filled-brand group-data-[state=open]:text-white">
							<feature.icon stroke="1.5" class="size-24" />
						</div>
						<p class="w-full h4 leading-[1.2] tracking-[-0.01em]">{feature.title}</p>
                        <Accordion.ItemIndicator class="group">
						    <IconChevronDown stroke="1.5" class="size-18 transition group-data-[state=open]:rotate-180" />
					    </Accordion.ItemIndicator>
                    </Accordion.ItemTrigger>
			    </h3>
			
                <Accordion.ItemContent class="px-16 pt-0 pb-24">
                    {#snippet element(attributes)}
					    {#if !attributes.hidden}
						    <div {...attributes} transition:slide={{ duration: 150 }}>
								<img 
									class="pb-16 lg:hidden"
            						src={`${base}/imgs/${feature.imgName}`}
            						alt={feature.title} />
							    <p class="text-brand-contrast-dark">{feature.description}</p>
						    </div>
					    {/if}
				    {/snippet}
                </Accordion.ItemContent>

		    </Accordion.Item>
	    {/each}
    </Accordion>
    </div>
</section>