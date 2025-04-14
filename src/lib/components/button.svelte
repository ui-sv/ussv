<script lang="ts">
	import { Button, type ButtonRootProps } from 'bits-ui';
	import type { ClassValue } from 'svelte/elements';

	export type Size = 'small' | 'medium' | 'large';
	export type Variant =
		| 'primary'
		| 'secondary'
		| 'accent-cool'
		| 'accent-warm'
		| 'base'
		| 'outline'
		| 'inverse';

	type Props = ButtonRootProps & { size?: Size; variant?: Variant };

	let { children, size = 'medium', variant = 'primary', ...rest_props }: Props = $props();

	const sizes: Record<Size, ClassValue> = {
		small: 'h-8 px-2 rounded text-sm outline-offset-2 outline-3',
		medium: 'h-10 px-4 rounded outline-offset-4 outline-4',
		large: ' h-12 px-6 text-lg rounded-lg outline-offset-4 outline-4'
	};

	const variants: Record<Variant, ClassValue> = {
		primary: [
			'text-white bg-sky-700 outline-solid',
			'hover:(bg-sky-900)',
			'active:(bg-sky-950)',
			'focus:(outline-sky-700)'
		],
		secondary: [
			'text-white bg-red-700 outline-solid',
			'hover:(bg-red-900)',
			'active:(bg-red-950)',
			'focus:(outline-red-700)'
		],
		'accent-cool': [
			'text-white bg-cyan-600 outline-solid',
			'hover:(bg-cyan-700)',
			'active:(bg-cyan-900)',
			'focus:(outline-cyan-600)'
		],
		'accent-warm': [
			'text-white bg-amber-600 outline-solid',
			'hover:(bg-amber-900)',
			'active:(bg-amber-950)',
			'focus:(outline-amber-600)'
		],
		base: [
			'text-white bg-zinc-500 outline-solid',
			'hover:(bg-zinc-700)',
			'active:(bg-zinc-950)',
			'focus:(outline-zinc-500)'
		],
		outline: [
			'border-2 border-sky-700 text-sky-700 outline-solid outline-transparent',
			'hover:(border-sky-900) text-sky-900',
			'active:(border-sky-950 text-sky-950)',
			'focus:(outline-sky-700)'
		],
		inverse: [
			'border-2 border-zinc-200 text-zinc-200 outline-solid outline-transparent',
			'hover:(border-zinc-100) text-zinc-100',
			'active:(border-zinc-50 text-zinc-50)',
			'focus:(outline-zinc-200)'
		]
	};
</script>

<Button.Root
	class={[
		'flex items-center gap-1 font-bold',
		sizes[size],
		variants[variant],
		'disabled:(text-zinc-600 outline-transparent bg-zinc-300 cursor-not-allowed border-none)'
	]}
	{...rest_props}
>
	{@render children?.()}
</Button.Root>
