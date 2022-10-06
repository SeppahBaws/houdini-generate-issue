<script lang="ts">
	import { graphql, type PastLaunchesStore } from '$houdini';

	const launches: PastLaunchesStore = graphql`
		query PastLaunches {
			launchesPast(limit: 10) {
				mission_name
			}
		}
	`;
</script>

<p>Past launches:</p>
<ul>
	{#each $launches.data?.launchesPast ?? [] as launch}
		<li>{launch?.mission_name}</li>
	{/each}
</ul>
