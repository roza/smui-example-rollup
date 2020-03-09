<svelte:head>
  <title>SMUI example</title>
  <link href="https://fonts.googleapis.com/css?family=Material+Icons&display=block" rel="stylesheet">
</svelte:head>
<TopAppBar variant="static" {prominent} {dense} color={secondaryColor ? 'secondary' : 'primary'}>
        <Row>
          <Section>
            <IconButton class="material-icons">menu</IconButton>
            <Title>Static</Title>
          </Section>
          <Section align="end" toolbar>
            <IconButton class="material-icons" aria-label="Download">file_download</IconButton>
            <IconButton class="material-icons" aria-label="Print this page">print</IconButton>
            <IconButton class="material-icons" aria-label="Bookmark this page">bookmark</IconButton>
          </Section>
        </Row>
      </TopAppBar>

<div class="container">
  <Button on:click={() => clicked++}>
    <Icon class="material-icons">thumb_up</Icon>
    <Label>Click Me</Label>
  </Button>
  <p class="mdc-typography--body1">
    {#if clicked}
      You've clicked the button {clicked} time{clicked === 1 ? '' : 's'}.
    {:else}
      <span class="grayed">You haven't clicked the button.</span>
    {/if}
  </p>
</div>

<script>
  import TopAppBar, {Row, Section, Title} from '@smui/top-app-bar';
  
  let prominent = false;
  let dense = false;
  let secondaryColor = false;
  import Button, {Label, Icon} from '@smui/button';
  import IconButton from '@smui/icon-button';
  
  let clicked = 0;
</script>

<style>
  .grayed {
    opacity: .6;
  }
</style>