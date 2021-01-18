<script>
	import "@polymer/paper-card";
	import "@material/mwc-button";
	import '@material/mwc-top-app-bar-fixed';
	import '@material/mwc-icon-button';
	
	let elements = [];
	import DB from "./DB.svelte";
</script>
	
	
	<style>
		paper-card{
			width:90%;
			margin-top: 3px;
	margin-bottom: 3px;
		}



	</style>

	​​
	
	<DB bind:elements = {elements} />
	<link href="https://fonts.googleapis.com/css?family=Material+Icons&display=block" rel="stylesheet">
	<mwc-top-app-bar-fixed>
	<mwc-icon-button icon="menu" slot="navigationIcon"></mwc-icon-button>
	<div slot="title">Title</div>
		<mwc-icon-button icon="file_download" slot="actionItems"></mwc-icon-button>
		<mwc-icon-button icon="print" slot="actionItems"></mwc-icon-button>
		<mwc-icon-button icon="favorite" slot="actionItems"></mwc-icon-button>
	<div><!-- content --></div>
	</mwc-top-app-bar-fixed>
	<main>
		{#each elements as elem}​​
		<paper-card heading={elem.title}​​>
			<img src="data:image/jpeg;base64, {elem.img.data}​​" alt="{elem.title}​​" title="{elem.title}​​"/>
			<div class="card-content">de {elem.author}​​ au prix de {elem.price}​​</div>
		</paper-card>
		{/each}​​
		<mwc-button label="Click me!" />
	</main>