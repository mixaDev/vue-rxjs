<template>
  <div id="app">
    <span>Count: {{ count }}</span>
  </div>
</template>

<script>
//  import { Observable } from 'rxjs/Rx'
  import { Observable } from 'rxjs/Observable'
  import 'rxjs/add/observable/interval'
  import 'rxjs/add/operator/filter'

  export default {
    name: 'app',
    subscriptions () {
      return {
        count: Observable.interval(1000)
          .filter((value) => value % 2 == 0)
      }
    }
  }
</script>

<style>

</style>
