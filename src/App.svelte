<script>
	export let name;

	import Button from '@smui/button';
  import Fab from '@smui/fab';
  import Textfield from '@smui/textfield';
  import HelperText from '@smui/textfield/helper-text';
	import {Label, Icon} from '@smui/common';
	
	import Card, {Content, PrimaryAction, Media, MediaContent, Actions, ActionButtons, ActionIcons} from '@smui/card';
	import IconButton from '@smui/icon-button';
	import List, {Item, Separator, Text} from '@smui/list';

  import TopAppBar, {Section, Title, Row} from '@smui/top-app-bar';
  import Menu from '@smui/menu';
  import {GroupItem} from '@smui/button';
  let dense = true;
  let menu;
  let topAppBar;
  let title = "禿！";
</script>

<main>
  <TopAppBar bind:this={topAppBar} {dense}>
    <Row>
      <Section>
        <IconButton class="material-icons">menu</IconButton>
        <Title>{title}</Title>
      </Section>
      <Section align="end" toolbar>
        <IconButton class="material-icons" aria-label="Download"
          >file_download</IconButton
        >
      </Section>
    </Row>
  </TopAppBar>
	<h1>Hello {name}!</h1>

  <Button on:click={() => alert('Clicked!')}>Just a Button</Button>
  <Button variant="raised"><Label>Raised Button, Using a Label</Label></Button>
  <Button some-arbitrary-prop="placed on the actual button">Button</Button>

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