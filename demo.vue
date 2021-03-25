
 <el-button  style="margin:0 0 20px 20px;" type="primary"  @click="handleDownload">
           导出
        </el-button>
handleDownload() {
                import('@/vendor/Export2Excel').then(excel => {
                    const tHeader = ['注册日期', '用户姓名']//表头
                    const filterVal = ['registe_time', 'username']//对应的值
                    const list = this.tableData//要导出的数据
                    const data = this.formatJson(filterVal, list)
                    excel.export_json_to_excel({
                        header: tHeader,
                        data,
                    })
                })
            },
//数据的处理
            formatJson(filterVal, jsonData) {
                return jsonData.map(v => filterVal.map(j => {
                    if (j === 'timestamp') {
                        return parseTime(v[j])
                    } else {
                        return v[j]
                    }
                }))
            }
