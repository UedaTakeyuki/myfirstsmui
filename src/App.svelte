<script>
	export let name;

	import Button from '@smui/button';
  import Fab from '@smui/fab';
  import Textfield from '@smui/textfield';
  import HelperText from '@smui/textfield/helper-text';
	import {Label, Icon} from '@smui/common';
  let superText = '死ねハゲ！';
	
	import Card, {Content, PrimaryAction, Media, MediaContent, Actions, ActionButtons, ActionIcons} from '@smui/card';
	import IconButton from '@smui/icon-button';
	function doAction(action) {
    alert('You did an action: '+action);
	}
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

<Card style="width: 360px;">
  <PrimaryAction on:click={() => doAction('openItemPage')}>
    <Media style="background-image: url(https://via.placeholder.com/320x180.png?text=16x9);" aspectRatio="16x9">
      <MediaContent>
        <div style="color: #fff; position: absolute; bottom: 16px; left: 16px;">
          <h2 class="mdc-typography--headline6" style="margin: 0;">Glorious Item</h2>
          <h3 class="mdc-typography--subtitle2" style="margin: 0;">People are saying you need to buy it.</h3>
        </div>
      </MediaContent>
    </Media>
    <Content class="mdc-typography--body2">
      This item is so glorious that you would have to be some kind of fool to not immediately buy it.
    </Content>
  </PrimaryAction>
  <Actions>
    <ActionButtons>
      <Button on:click={() => doAction('addToCart')}>
        <Label>Add to Card</Label>
      </Button>
      <Button on:click={() => doAction('buyNow')}>
        <Label>Buy Now</Label>
      </Button>
    </ActionButtons>
    <ActionIcons>
      <IconButton on:click={() => doAction('addToFavoritesToggle')} toggle aria-label="Add to favorites" title="Add to favorites">
        <Icon class="material-icons" on>favorite</Icon>
        <Icon class="material-icons">favorite_border</Icon>
      </IconButton>
      <IconButton class="material-icons" on:click={() => doAction('share')} title="Share">share</IconButton>
    </ActionIcons>
  </Actions>
</Card>
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