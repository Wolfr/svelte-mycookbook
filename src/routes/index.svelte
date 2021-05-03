<script>
  import RichContent from '$lib/RichContent.svelte';
  import Button from '$lib/Button.svelte';


  import Container from '$lib/Container.svelte';
  import ResetRem from '$lib/ResetRem.svelte';


  import FormGroupLayout from '$lib/FormGroupLayout.svelte';
  import FormGroup from '$lib/FormGroup.svelte';

  import Toggle from "$lib/Toggle.svelte";

  let toggled = false;
  let title = "Blank recipe";

  // https://svelte.dev/repl/c7094fb1004b440482d2a88f4d1d7ef5?version=3.14.0
  import MultiSelect from '$lib/MultiSelect.svelte';
  let valueMultiSelect = null;

  import { autoresize } from '$lib/autosize.js';

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
                <option>1hour 15 mins</option>
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
            <MultiSelect id='category' activeOption="false" bind:valueMultiSelect>
              <option id="FR">French</option>
              <option id="IN">Indian</option>
              <option id="IT">Italian</option>
              <option id="JP">Japanese</option>
              <option id="MEX">Mexican</option>
              <option id="AFR">African</option>
              <option id="AM">American</option>
              <option id="BR">British</option>
              <option id="CAR">Caribbean</option>
              <option id="CH">Chinese</option>
              <option id="GR">Greek</option>
              <option id="KOR">Korean</option>
              <option id="MOR">Moroccan</option>
              <option id="PAK">Pakistani</option>
              <option id="POR">Portuguese</option>
              <option id="SA">South American</option>
              <option id="SP">Spanish</option>
              <option id="TH">Thai</option>
              <option id="ME">Middle Eastern</option>
              <option id="OT">Other</option>
            </MultiSelect>
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