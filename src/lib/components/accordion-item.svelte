<script lang="ts">
	import { Accordion } from 'bits-ui';
	import { getContext, type Snippet } from 'svelte';
	import type { ClassValue } from 'svelte/elements';
	import Plus from 'lucide-svelte/icons/plus';
	import Minus from 'lucide-svelte/icons/minus';

	export type AccordionContext = {
		variant: 'primary' | 'secondary' | 'accent-cool' | 'accent-warm' | 'base';
		border_width?: string | number;
		border_color?: string;
		bordered: boolean;
		selected?: string[];
	};

	export type Props = {
		children?: Snippet;
		header: string;
		background?: string;
	};

	let { children, header, background, ...rest_props }: Props = $props();
	let context: AccordionContext = getContext('accordion_context');
	const id = $props.id();

	const variants: Record<AccordionContext['variant'], ClassValue> = {
		'accent-cool': ['text-white bg-cyan-600 hover:(bg-cyan-700)'],
		'accent-warm': ['text-white bg-amber-600 hover:(bg-amber-900)'],
		base: ['text-black bg-zinc-200 hover:(bg-zinc-300)'],
		primary: ['text-white bg-sky-700 hover:(bg-sky-900)'],
		secondary: ['text-white bg-red-700 hover:(bg-red-900)']
	};
</script>

<Accordion.Item value={id} style={{ backgroundColor: background }} {...rest_props}>
	<Accordion.Header>
		<Accordion.Trigger
			class={[
				'h-13 px-6 font-bold flex items-center justify-between w-full',
				variants[context.variant]
			]}
			onclick={() =>
				context.selected?.includes(id) ? (context.selected = []) : (context.selected = [id])}
		>
			{header}

			{#if context.selected?.includes(id)}
				<Minus class="data-[state=open]=hidden" />
			{:else}
				<Plus class="data-[state=open]=hidden" />
			{/if}
		</Accordion.Trigger>
	</Accordion.Header>

	<Accordion.Content
		class={['p-4', context.bordered && 'border-solid border-2 border-sky-100']}
		style={{
			borderWidth:
				typeof context.border_width === 'string'
					? context.border_width
					: `${context.border_width}px`,
			borderColor: context.border_color
		}}
	>
		{@render children?.()}
	</Accordion.Content>
</Accordion.Item>
