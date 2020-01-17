<template>
    <div>
         <el-button @click="henka">ダイヤログを開く</el-button>
         <el-dialog :visible.sync="visible" title="確認">
             <p>処理されました。</p>
        </el-dialog>
    </div>
</template>

<script>
export default {
    data() {
        return {
            visible: false
        }
    },
    methods: {
        henka() {
            this.visible = true
        }
    }
}
</script>