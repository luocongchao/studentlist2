<template>
    <el-table :data="tableData" style="width: 100%">
        <el-table-column label="Date" prop="date"></el-table-column>
        <el-table-column label="Name" prop="name">
            <template slot="header" slot-scope="scope">
                <el-button type="success">成功按钮</el-button>
            </template>
        </el-table-column>
        <el-table-column label="adress" :render-header="renderHeader">
            <template slot-scope="scope">
                <el-button size="mini" @click="handleEdit(scope.$index, scope.row)">Edit</el-button>
                <el-button size="mini" type="danger" @click="handleDelete(scope.$index, scope.row)">Delete</el-button>
            </template>
        </el-table-column>
    </el-table>
</template>

<script>
export default {
    data() {
        return {
            tableData: [
                {
                    date: "2016-05-02",
                    name: "王小虎",
                    address: "上海市普陀区金沙江路 1518 弄"
                },
                {
                    date: "2016-05-04",
                    name: "王小虎",
                    address: "上海市普陀区金沙江路 1517 弄"
                },
                {
                    date: "2016-05-01",
                    name: "王小虎",
                    address: "上海市普陀区金沙江路 1519 弄"
                },
                {
                    date: "2016-05-03",
                    name: "王小虎",
                    address: "上海市普陀区金沙江路 1516 弄"
                }
            ],
            search: ""
        };
    },
    methods: {
        handleEdit(index, row) {
            console.log(index, row);
        },
        handleDelete(index, row) {
            console.log(index, row);
        },
        renderHeader(h, { column, $index }, index) {
            return h("span", {}, [
                h("span", {}, column.label),
                h("Button", {
                    on: {
                        click: () => {
                            alert(5555);
                        }
                    }
                },"kkkk"),
                h(
                    "i",
                    {
                        slot: "reference",
                        class: "el-icon-question",
                        on: {
                            click: () => {
                                alert(55555);
                            }
                        }
                    },
                    ""
                )
            ]);
        }
    }
};
</script>