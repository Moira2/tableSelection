<template>
    <div class="showList">
        <div class="itemList">
            <el-card class="itemList-box-card">
                <div slot="header">
                    Items
                </div>
                <div class="text item">
                    <el-table ref="multipleTable"
                              :data="tableData"
                              tooltip-effect="dark"
                              style="width: 100%"
                              size="mini"
                              :header-cell-style="headStyle"
                              :cell-style="rowStyle">
                        <el-table-column type="selection">
                        </el-table-column>
                        <el-table-column prop="date"
                                         label="日期"
                                         min-width="40">
                        </el-table-column>
                        <el-table-column prop="name"
                                         label="姓名"
                                         min-width="30">
                        </el-table-column>
                        <el-table-column prop="address"
                                         label="地址"
                                         show-overflow-tooltip>
                        </el-table-column>
                    </el-table>
                </div>
            </el-card>
        </div>
        <div class="selectedItemList">
            <el-card class="selectedItemList-box-card">
                <div slot="header">
                    Selected Items
                </div>
            </el-card>
        </div>
    </div>
</template>
<script>
import * as mockApi from '../api/api.js'
export default {
    name: 'tableSelection',
    props: {

    },
    data () {
        return {
            tableData: [],
            multipleSelection: []
        }
    },
    mounted () {
        this.getItemList()
    },
    methods: {
        headStyle () {
            return 'text-align:center'
        },
        rowStyle () {
            return 'text-align:center'
        },
        getItemList () {
            mockApi.getItemList().then(res => {
                this.tableData = res.data.userTableData;
            }).catch(err => {

            })
        }
    }
}
</script>
<style lang="scss" scoped >
.showList {
    height: 600px;
    width: 900px;
    border: 1px solid #ebeef5;
    margin: 0 auto;
    display: flex;
    justify-content: space-around;
    align-items: center;
    .text {
        font-size: 14px;
    }
    .item {
        margin-bottom: 18px;
    }
    .itemList {
        .itemList-box-card {
            width: 400px;
            height: 500px;
        }
    }
    .selectedItemList {
        .selectedItemList-box-card {
            width: 400px;
            height: 500px;
        }
    }
}
</style>







