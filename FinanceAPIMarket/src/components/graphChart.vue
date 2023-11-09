<template>
    <div >
        <div v-for="(data, index) in forexData" :key="index">
          <p>{{ data.t }} ahhh</p>
          </div>
          ahh
    </div>
</template>
<script >
import { computed } from 'vue'
export default {
  setup() {
    const forexData = null
  const computedData = computed(() => {
    return forexData
  })
    // expose to template and other options API hooks
    return {
      forexData,
      computedData
    }
  },
    async mounted() {
        fetch('https://api.finazon.io/latest/tickers/forex?&apikey=95fcb7469df942cb82430fb321d47c5exn')
        .then((response) => {
           console.log(response)
        })
        fetch('https://api.finazon.io/latest/datasets?apikey=95fcb7469df942cb82430fb321d47c5exn')
        .then(res => {
          console.log(res)
        })
        fetch('https://api.finazon.io/latest/tickers/forex?apikey=95fcb7469df942cb82430fb321d47c5exn')
        .then(res => {
          console.log(res)
        })
        try {
            const usdJPY = await fetch('https://api.finazon.io/latest/time_series?dataset=forex&ticker=USD%2FJPY&apikey=e16fe89151aa423488d361185f01347d43')
            const response = await usdJPY.json()
            this.forexData = response.data
            console.log(this.forexData, this.computedData)
  
          } catch (err) {
            console.error(err)
          }
    }
}
</script>
<style lang="">
    
</style>