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
        fetch('https://api.finazon.io/latest/datasets?code=bybit&page=0&page_size=100&apikey=95fcb7469df942cb82430fb321d47c5exn')
        .then((response) => {
           console.log(response)
        })
    }
}
</script>
<style lang="">
    
</style>