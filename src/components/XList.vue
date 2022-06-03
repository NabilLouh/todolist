<template>

<div>
    <ul class="todo-list">

            
        <li v-for="(tache, index) in listetache" :key="index" 
        :class="{completed: tache.etat == true}"
        v-show="filtre == 'all' || tache.etat == filtre">

            <div class="view">

            <input class="toggle" type="checkbox" v-model="tache.etat">

            <label  @dblclick="tache.modi = true" v-if="tache.modi == false">{{tache.ntache}}</label>
            <input type="text" v-model="tache.ntache" v-else @keyup.enter="tache.modi = false">


            <button class="destroy" @click="this.listetache.splice(index, 1)"></button>

            </div>

            <input class="edit" value="Rule the web">

        </li>

    </ul>
</div>
    
</template>






<script>
export default {
    props: ['listedestache', "filtre"],

    data() {
        return {
            listetache: this.listedestache,
            choix: this.filtre,

        }
    },

     
    
    
}
</script>



<style scoped>

</style>