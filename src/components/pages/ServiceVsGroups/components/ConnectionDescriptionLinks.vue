<template>
  <span v-if="dataSource">
    <span v-if="typeof dataSource === 'string'">
      <a :href="dataSource" target="_blank" class="text-darkred">How-to doc</a>
    </span>
    <span v-else-if="typeof dataSource === 'object' && dataSource.length >= 1">
      <span v-if="dataSource.length == 1">
        <a :href="dataSource[0]" target="_blank" class="text-darkred">How-to doc</a>
      </span>
      <span v-else>
        How-to doc:
        <span v-for="(connUrl, idx) in dataSource">
          <a :href="connUrl" target="_blank" class="text-darkred">{{idx+1}}</a>
          <span v-if="idx+1 < dataSource.length">
            |
          </span>
        </span>
      </span>
    </span>
    <span v-else>

    </span>
  </span>
</template>

<script>
export default {
  name: 'ConnectionDiscriptionLinks',
  props: {
    dataSource: [String, Array]
  }
}
</script>
