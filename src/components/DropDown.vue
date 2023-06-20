<script>
    export default {
        name: 'DropDown',
        props: {
            archetypeslist: Array,
        },
        data() {
            return {
                selectedArchetypes: [],
                archetype: 'Blue-Eyes',
            }
        },
        methods: {
            randomArchetypes() {
                for(let i = 0; i < 10; i++){
                    let wichone = Math.floor(Math.random() * 400) + 1;
                    this.selectedArchetypes.push(this.archetypeslist[wichone].archetype_name);
                    console.log(this.selectedArchetypes);
                }
            }
        },
        mounted () {
            this.randomArchetypes();
        },
    }
</script>

<template>
        <div class="btn-group">
                <select name="archetype" id="archetype" @change="$emit('changedtype', archetype )" v-model="archetype">
                    <option value="Blue-Eyes">Blue-Eyes</option>
                    <option :value="arche" v-for="arche in selectedArchetypes">{{arche}}</option>
                </select>
        </div>
</template>

<style lang="scss" scoped>
    @use '../styles/partials/mixing.scss' as *;
    @use '../styles/partials/variables.scss' as *;

    button{
        color: black;
        background-color: white;
        border-color: black;
    }

    button:hover, button:focus, button:focus-visible, button:active{
        color: black;
        background-color: white;
        border-color: black;
    }
</style>