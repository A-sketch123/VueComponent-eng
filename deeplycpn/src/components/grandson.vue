<template>
    <div>
        <h3> I am the grandson component of provide / inject, and the value of the ancestor component I received is:</h3>

        <div >{{fatherTxet.info}}</div>
    </div>
</template>
<script>
    export default{
        name:'grandson',
        // grandson component injection depends on accessing parent component, use provide/inject
        inject:['fatherTxet'],
      

    }
</script>