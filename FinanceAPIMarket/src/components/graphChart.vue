<template>
    <div>
        
    </div>
</template>
<script >
export default {
  setup() {

    // expose to template and other options API hooks
    return {

    }
  },
    mounted() {
        fetch('https://api.finazon.io/latest/tickers/forex?&apikey=95fcb7469df942cb82430fb321d47c5exn')
        .then((response) => {
           console.log(response)
        })
        fetch('https://api.finazon.io/latest/time_series?dataset=forex&ticker=xauusd&&apikey=95fcb7469df942cb82430fb321d47c5exn')
        .then(res => {
          console.log(res)
        })
        fetch('https://api.finazon.io/latest/datasets?apikey=95fcb7469df942cb82430fb321d47c5exn')
        .then(res => {
          console.log(res)
        })
    }
}
</script>
<style lang="">
    
</style>