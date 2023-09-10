<template>
    <div class="flex  justify-end">
        <span class="mt-2 text-white">There are {{ itemCount }} things to do ...</span>
    </div>
    
</template>

<script>

export default{
    props:["itemCount"] //itemCount'u yazdırmak için props kullandık.
        
}

</script>