<template>
    <div class="container">
        <div v-if="!totalCheck" class="row W-75" style="height: 100px; flex-direction: row;">
            <div v-for="(item, index) in casesArrays" :key="index" 
                :class="['col-3 m-2 alert', (!item.checked ? 'alert-warning': 'alert-success')]">
                <button class="h1 btn btn-lg" @click="checkCase(item, index)" :disabled="!item.checkable">
                    <b-icon v-if="!item.checked" icon="exclamation-circle-fill" variant="warning"></b-icon>
                    <b-icon v-else icon="check-circle-fill" variant="success"></b-icon>
                </button>
            </div>
        </div>
        <div v-else class="row W-75" style="height: 100px; flex-direction: row;">
            <div class="alert alert-success alert-dismissible">
                <h3 class="text-success"><i class="fa fa-check-circle"></i> OK</h3>
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
            ],
            totalCheck: false
        }
    },
    methods: {
        checkCase(item, index){
            item.checked = true
            if(this.casesArrays[index+1] )
                this.casesArrays[index+1].checkable = true
            this.totalCheck = this.casesArrays.every( val => val.checked === true)
        }
    },
}
</script>