<script lang="ts">
	import Stop from '~icons/tabler/hand-stop';
	import Disable from '~icons/tabler/alert-triangle'
	import type { StepperControl } from '$lib/types/models';

	export let stepperControl: StepperControl;
	export let onChange: () => void;
</script>

<div class="flex flex-row flex-wrap justify-between gap-x-2">
	<div class="flex-grow"></div>
	<div>
		<button class="btn btn-primary inline-flex items-center" on:click={() => {stepperControl.isEnabled = false; onChange();}}>
			<Disable class="mr-2 h-5 w-5" /><span>Disable</span>
		</button>
	</div>
	<div>
		<button class="btn btn-primary inline-flex items-center" on:click={() => {stepperControl.isEnabled = true; stepperControl.speed=0; onChange();}}>
			<Stop class="mr-2 h-5 w-5" /><span>Stop</span>
		</button>
	</div>
</div>