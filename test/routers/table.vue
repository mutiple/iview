<style>
    body{
        height: auto;
    }
</style>
<template>
    <div>
        <!--<i-table size="large" border stripe :columns="columns" :data="data"></i-table>-->
        <br>
        <i-table
                width="550"
                stripe
                border
                highlight-row
                :show-header="true"
                :columns="columns"
                :data="data"
                :row-class-name="rowClsName"
                @on-current-change="current"
                @on-select="select"
                @on-selection-change="schange"
                @on-select-all="sall">
            <!--<div slot="header">表格标题</div>-->
            <!--<div slot="footer">表格标题</div>-->
        </i-table>
        <br>
        <!--<i-table size="small" border stripe :columns="columns" :data="data"></i-table>-->
    </div>
</template>
<script>
    export default {
        props: {
        
        },
        data () {
            return {
                columns: [
                    {
                        type: 'selection',
                        width: 150
                    },
                    {
                        type: 'index',
                        width: 50
                    },
                    {
                        title: '姓名',
                        key: 'name',
                        align: 'left',
                        fixed: 'left',
                        width: 100
                    },
                    {
                        title: '年龄',
                        key: 'age',
                        align: 'right',
//                        fixed: 'left',
                        sortable: true,
                        width: 100
//                        render (row) {
//                            return `<i-button>${row.age}</i-button>`
//                        }
                    },
                    {
                        title: '地址',
                        key: 'address',
                        align: 'center',
//                        fixed: 'right',
                        width: 100,
//                        render (row, column, index) {
//                            if (row.edit) {
//                                return `<i-input :value.sync="data[${index}].name"></i-input>`;
//                            } else {
//                                return `<Tooltip content="${row.address}"><i-button @click="show(${index})">${row.name}</i-button></Tooltip>`;
//                            }
//                        }
                    },
                    {
                        title: '操作',
                        key: 'action',
                        fixed: 'right',
                        width: 120,
                        render (row, column, index) {
                            return `<i-button @click="edit(${index})">${row.name}${index}</i-button>`
//                            return `<a>${row.name}</a>`
                        }
                    }
                ],
                data: [
                    {
                        name: '梁灏',
                        age: 25,
                        address: '北京市朝阳区',
                        edit: false
                    },
                    {
                        name: '段模',
                        age: 21,
                        address: '北京市海淀区',
                        edit: false
                    },
                    {
                        name: '刘天娇',
                        age: 27,
                        address: '北京市东城区',
                        edit: false
                    },
                    {
                        name: '胡国伟',
                        age: 22,
                        address: '北京市西城区',
                        edit: false
                    }
                ],
                height: 200
            }
        },
        computed: {
        
        },
        methods: {
            show (name) {
                this.$Message.info(name);
            },
            edit (index) {
//                this.data[index].edit = true;
                this.$Message.info(this.data[index].name);
            },
            current (newData, oldData) {
//                console.log(newData);
//                console.log(oldData);
            },
            select (a,b){
                console.log(JSON.stringify(b));
//                console.log(b);
            },
            schange (a) {
//                console.log(a)
            },
            sall (a) {
                console.log(a)
            },
            rowClsName (row, index) {
                if (index == 1) {
                    return 'row-success';
                } else {
                    return '';
                }
            }
        },
        ready () {
            setTimeout(() => {
//                this.columns[3].width = 300;
//                this.columns[2].width = 150;
//                return;
//                this.height = 150;
//                this.data.push({
//                    name: '刘天娇2',
//                    age: 272,
//                    address: '北京市东城区2',
//                    edit: false
//                });
//                this.data.splice(0, 1)
//                this.columns.splice(2,1)
            }, 2000);
        }
    }
</script>