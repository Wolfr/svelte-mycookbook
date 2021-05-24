<script>
  import RichContent from '$lib/RichContent.svelte';
  import Button from '$lib/Button.svelte';
  import MultiSelect from 'svelte-select';
  import Container from '$lib/Container.svelte';
  import ResetRem from '$lib/ResetRem.svelte';


  import FormGroupLayout from '$lib/FormGroupLayout.svelte';
  import FormGroup from '$lib/FormGroup.svelte';

  import Toggle from "$lib/Toggle.svelte";

  let toggled = false;
  let title = "Blank recipe";


  import { autoresize } from '$lib/autosize.js';

  let selectedValue;
  const complexItems = [
   { value: 'French', label: 'French', group: 'All' },
   { value: 'Indian', label: 'Indian', group: 'All' },
   { value: 'Italian', label: 'Italian', group: 'All' },
   { value: 'Japanese', label: 'Japanese', group: 'All' },
   { value: 'Mexican', label: 'Mexican', group: 'All' },
   { value: 'African', label: 'African', group: 'All' },
   { value: 'American', label: 'American', group: 'All' },
   { value: 'British', label: 'British', group: 'All' },
   { value: 'Caribbean', label: 'Caribbean', group: 'All' },
   { value: 'Chinese', label: 'Chinese', group: 'All' },
   { value: 'Greek', label: 'Greek', group: 'All' },
   { value: 'Korean', label: 'Korean', group: 'All' },
   { value: 'Moroccan', label: 'Moroccan', group: 'All' },
   { value: 'Pakistani', label: 'Pakistani', group: 'All' },
   { value: 'Portuguese', label: 'Portuguese', group: 'All' },
   { value: 'South American', label: 'South American', group: 'All' },
   { value: 'Spanish', label: 'Spanish', group: 'All' },
   { value: 'Thai', label: 'Thai', group: 'All' },
   { value: 'Middle Eastern', label: 'Middle Eastern', group: 'All' },
   { value: 'Other', label: 'Other', group: 'All' },
  ];






</script>

<slot />

<div class="o-scroll-wrapper">
  <div class="o-scroll-wrapper__body">
    <Container>
      <div class="o-container-vertical">
        <h2 class="c-h2">{title}</h2>

        <FormGroupLayout layoutType="standard">
          <FormGroup label="Name" forValue="name">
            <input id="name" class="c-input" bind:value={title} type="text">
          </FormGroup>
          <FormGroup label="Preparation time" forValue="prepTime">
            <div class="c-select-holder">
              <select class="c-select" id="prepTime">
                <option>Select an option</option>
                <option>10 minutes</option>
                <option>15 minutes</option>
                <option>30 minutes</option>
                <option>45 minutes</option>
                <option>1 hour</option>
                <option>1 hour 15 mins</option>
                <option>1 hour 30 mins</option>
                <option>1 hour 45 mins</option>
                <option>2 hours</option>
                <option>2,5 hours</option>
                <option>3 hours</option>
              </select>
            </div>
          </FormGroup>
          <FormGroup label="Serves (# of persons)" forValue="prepTime">
            <div class="c-select-holder">
              <select class="c-select" id="prepTime">
                <option>1</option>
                <option>2</option>
                <option>3</option>
                <option>4</option>
                <option>5</option>
                <option>6</option>
                <option>7</option>
                <option>8</option>
                <option>Other</option>
              </select>
            </div>
          </FormGroup>
          <FormGroup label="Needs extra preparation beforehand?" forValue="needsPrep">
              <Toggle bind:toggled label="Needs prep" />
          </FormGroup>
          <FormGroup label="Category" forValue="category">
            <MultiSelect items={complexItems} bind:selectedValue isMulti={true} />
          </FormGroup>
          <FormGroup label="Description" forValue="description">
            <textarea use:autoresize class="c-input" id="description" rows="5" />
          </FormGroup>
          <FormGroup label="Ingredients" forValue="ingredients">
            <textarea use:autoresize class="c-input" id="ingredients" rows="4" />
          </FormGroup>
          <FormGroup label="Instructions" forValue="instructions">
            <textarea use:autoresize class="c-input" id="instructions" rows="3" />
          </FormGroup>
        </FormGroupLayout>
      </div>
    </Container>
  </div>
</div>