<template>
  <div>
    <p v-if="$fetchState.pending">
      Fetching...
    </p>
    <p v-else-if="$fetchState.error" id="error">
      {{ $fetchState.error.message }}
    </p>
    <pre v-else>{{ team }}</pre>
  </div>
</template>

<script>
export default {
  data () {
    return {
      team: []
    }
  },
  async fetch () {
    await new Promise((resolve, reject) => reject(new Error('fetch-error')))
  }
}
</script>
