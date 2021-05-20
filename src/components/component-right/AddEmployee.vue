<template>
    <div class="title-add">
                <div class="title">
                    <b>Danh sách nhân viên</b>
                </div>
                <div class="add">
                    <div class="btn">
                        <button v-on:click="btnAddOnClick">
                            <span class="icon-btn"><img height="16" width="16" src="../../assets/content/icon/add.png" class="image"></span>
                            <!-- --><span class="content-btn">Thêm nhân viên</span>
                    </button>
             </div>
        </div>
        <FormAdd @closePopup="closePopup" :isHide="isHideParent" />
    </div>
    
</template>

<script>
import FormAdd from './FormAdd.vue'

export default {
    name: "AddEmployee",
    components:{
        FormAdd,
    },
    methods: {
    btnAddOnClick() {
      this.isHideParent = false;
    },
    closePopup(value) {
      this.isHideParent = value;
    }
    },
    data(){
        return {
             color: "#019160",
      loader: "dots", // bars  dots spinner
      onCancel: this.cancelLoading,
      width: 50,
      height: 50,
      backgroundColor: "#000",
      fullPage: false,
      opacity: 0.2,
      isHideParent: true,
      blur: "15px"
        }
    }
}
</script>


