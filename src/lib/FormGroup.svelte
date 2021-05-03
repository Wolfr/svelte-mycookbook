<script>
  export let label = null;
  export let layoutType = null;
  export let forValue = null;
  export let cssClass = null;

</script>

<div class="o-form-group {cssClass}">
  <label class="o-form-group__label" for={forValue}>{label}</label>
  <div class="o-form-group__controls">
    <slot />
  </div>
</div>
