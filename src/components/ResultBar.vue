<template>
    <div class="flex  justify-end">
        <span class="mt-2 text-white">{{ itemCount }} adet todo vardır...</span>
    </div>
    
</template>

<script>

export default{
    props:["itemCount"] //itemCount'u yazdırmak için props kullandık.
        
}

</script>