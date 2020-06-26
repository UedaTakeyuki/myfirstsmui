<script>
	export let name;

	import Button from '@smui/button';
  import Fab from '@smui/fab';
  import Textfield from '@smui/textfield';
  import HelperText from '@smui/textfield/helper-text';
  import {Label, Icon} from '@smui/common';

  let superText = 'あほ';
</script>

<main>
	<h1>Hello {name}!</h1>
	<p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p>

<Button on:click={() => alert('Clicked!')}>Just a Button</Button>
<Button variant="raised"><Label>Raised Button, Using a Label</Label></Button>
<Button some-arbitrary-prop="placed on the actual button">Button</Button>

<Fab on:click={() => alert('Clicked!')} extended>
  <Icon class="material-icons" style="margin-right: 12px;">favorite</Icon>
  <Label>Extended FAB</Label>
</Fab>

<Textfield
  bind:value={superText}
  label="Super Text"
  input$aria-controls="super-helper"
  input$aria-describedby="super-helper"
/>
<HelperText id="super-helper">What you put in this box will become super!</HelperText>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>