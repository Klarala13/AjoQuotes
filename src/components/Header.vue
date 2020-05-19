<template>
  <div class="row">
    <div class="col-12">
      <h3>Quotes Added</h3>
      <p class="text-center">Las citas que ves son de la maravillosa Ajo Micropoetisa. <a href="https://twitter.com/ajomicropoetisa?lang=es" target="blank">Aquí </a> puedes ver algunos de sus trabajos.</p>
      <div class="progress">
        <div class="progress">
          <div
            class="progress-bar-danger progress-bar-striped"
            role="progressbar"
            aria-valuenow="60"
            aria-valuemin="0"
            aria-valuemax="100"
            :style="{ width: (quoteCount / maxQuotes) * 100 + '%' }"
          >
            {{ quoteCount }} / {{ maxQuotes }}
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: ["quoteCount", "maxQuotes"]
};
</script>
