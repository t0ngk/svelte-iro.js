<script lang="ts">
	import iro from '@jaames/iro';
	import type { IroColorPicker } from '@jaames/iro/dist/ColorPicker.js';
	import type { IroComponentProps } from '@jaames/iro/dist/ComponentTypes';
	import { onMount } from 'svelte';
	let element: HTMLDivElement | null = null;
	let colorPicker: IroColorPicker;
	export let options: Partial<IroComponentProps> = {};
	export let color: string = '#fff';
	export let autoSize:boolean = false;
	export const setColor = (color: string) => {
		colorPicker?.color.set(color);
	}

	onMount(() => {
		if (autoSize) {
			options.width = element?.clientWidth || 0;
			options.height = element?.clientHeight || 0;
		}
		colorPicker = new (iro.ColorPicker as any)(element, options);
		colorPicker.color.set(color);
		colorPicker.on('color:change', (c: iro.Color) => {
			color = c.hexString;
		});
	});
</script>

<div bind:this={element}></div>
