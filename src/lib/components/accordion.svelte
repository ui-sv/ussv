<script lang="ts">
	/* eslint-disable @typescript-eslint/no-explicit-any */
	import { Accordion } from 'bits-ui';
	import { setContext, type Snippet } from 'svelte';
	import type { AccordionContext } from './accordion-item.svelte';

	export type Props = {
		multiple?: boolean;
		background?: string;
		children?: Snippet;
		bordered?: boolean;
		'border-width'?: string | number;
		'border-color'?: string;
		variant?: AccordionContext['variant'];
	};

	let {
		children,
		background,
		multiple = false,
		variant = 'base',
		bordered = false,
		'border-width': border_width,
		'border-color': border_color,
		...rest_props
	}: Props = $props();
	let context = $state<AccordionContext>({
		variant,
		border_width,
		border_color,
		bordered,
		selected: []
	});

	setContext<AccordionContext>('accordion_context', context);
</script>

<Accordion.Root
	value={multiple ? context.selected : (context.selected?.at(-2) as any)}
	class={['grid gap-2 py-2']}
	type={(multiple ? 'multiple' : 'single') as any}
	style={{ background: background }}
	{...rest_props}
>
	{@render children?.()}
</Accordion.Root>
