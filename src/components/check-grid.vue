<template>
    <div class="container">
        <div class="row W-75" style="height: 100px; flex-direction: row;">
            <div v-for="(item, index) in casesArrays" :key="index" class="col-3 m-2 alert alert-warning">
                <button class="h1" @click="checkCase(item)" :disabled="!item.checkable">
                    <b-icon v-if="!item.checked" icon="exclamation-circle-fill" variant="warning"></b-icon>
                    <b-icon v-else icon="check-circle-fill" variant="success"></b-icon>
                </button>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data(){
        return{
            casesArrays:[
                { checked: false, checkable: true },
                { checked: false, checkable: false },
                { checked: false, checkable: false },
                { checked: false, checkable: false },
                { checked: false, checkable: false },
                { checked: false, checkable: false }
            ]
        }
    },
    methods: {
        checkCase(item){
            item.checked = true
            this.setChecability()
        },
        setChecability(){
            console.log("casesArrays ::", this.casesArrays )
            for (let index = 1; index < this.casesArrays.length; index++) {
                if(this.casesArrays[index-1].checked)
                    this.casesArrays[index].checkable = true
            }
        }
    },
}
</script>