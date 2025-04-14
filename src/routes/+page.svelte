<script lang="ts">
	import AccordionItem from '$lib/components/accordion-item.svelte';
	import Accordion from '$lib/components/accordion.svelte';
	import Button from '$lib/components/button.svelte';
</script>

<div class="space-y-4 p-4">
	<p>Default:</p>

	<div class="flex flex-wrap gap-4">
		<Button>Default</Button>
		<Button variant="secondary">Secondary</Button>
		<Button variant="accent-cool">Accent Cool</Button>
		<Button variant="accent-warm">Accent Warm</Button>
		<Button variant="base">Base</Button>
		<Button variant="outline">Outline</Button>
		<Button variant="inverse">Outline Inverse</Button>
	</div>

	<p>Small:</p>

	<div class="flex flex-wrap gap-4">
		<Button size="small">Default</Button>
		<Button size="small" variant="secondary">Secondary</Button>
		<Button size="small" variant="accent-cool">Accent Cool</Button>
		<Button size="small" variant="accent-warm">Accent Warm</Button>
		<Button size="small" variant="base">Base</Button>
		<Button size="small" variant="outline">Outline</Button>
		<Button size="small" variant="inverse">Outline Inverse</Button>
	</div>

	<p>Large:</p>

	<div class="flex flex-wrap gap-4">
		<Button size="large">Default</Button>
		<Button size="large" variant="secondary">Secondary</Button>
		<Button size="large" variant="accent-cool">Accent Cool</Button>
		<Button size="large" variant="accent-warm">Accent Warm</Button>
		<Button size="large" variant="base">Base</Button>
		<Button size="large" variant="outline">Outline</Button>
		<Button size="large" variant="inverse">Outline Inverse</Button>
	</div>

	<p>Disabled:</p>

	<div class="flex flex-wrap gap-4">
		<Button disabled>Primary</Button>
		<Button disabled variant="secondary">Secondary</Button>
		<Button disabled variant="accent-cool">Accent Cool</Button>
		<Button disabled variant="accent-warm">Accent Warm</Button>
		<Button disabled variant="base">Base</Button>
		<Button disabled variant="outline">Outline</Button>
		<Button disabled variant="inverse">Outline Inverse</Button>
	</div>

	<p>accordion:</p>

	<Accordion>
		<AccordionItem header="First Amendment">
			Congress shall make no law respecting an establishment of religion, or prohibiting the free
			exercise thereof; or abridging the freedom of speech, or of the press; or the right of the
			people peaceably to assemble, and to petition the Government for a redress of grievances.
		</AccordionItem>
		<AccordionItem header="Second Amendment">
			A well regulated Militia, being necessary to the security of a free State, the right of the
			people to keep and bear Arms, shall not be infringed.
		</AccordionItem>
		<AccordionItem header="Third Amendment">
			No Soldier shall, in time of peace be quartered in any house, without the consent of the
			Owner, nor in time of war, but in a manner to be prescribed by law.
		</AccordionItem>
		<AccordionItem header="Fourth Amendment">
			The right of the people to be secure in their persons, houses, papers, and effects, against
			unreasonable searches and seizures, shall not be violated, and no Warrants shall issue, but
			upon probable cause, supported by Oath or affirmation, and particularly describing the place
			to be searched, and the persons or things to be seized.
		</AccordionItem>
		<AccordionItem header="Fifth Amendment">
			No person shall be held to answer for a capital, or otherwise infamous crime, unless on a
			presentment or indictment of a Grand Jury, except in cases arising in the land or naval
			forces, or in the Militia, when in actual service in time of War or public danger; nor shall
			any person be subject for the same offence to be twice put in jeopardy of life or limb; nor
			shall be compelled in any criminal case to be a witness against himself, nor be deprived of
			life, liberty, or property, without due process of law; nor shall private property be taken
			for public use, without just compensation.
		</AccordionItem>
	</Accordion>
</div>
