<template>
    <q-drawer v-model="leftDrawer" side="left" bordered>
      <!-- drawer content -->
    </q-drawer>
</template>
<script>
export default {
    props:{
        leftDrawer: isopen;
    }
}
</script>