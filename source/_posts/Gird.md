title: Gird， 表格通过主表确认副表内容
tags: front-end
description: 活用jqGrid
---
1. html主体

2. javascript内容
//先通过jqGrid建两个表对象
//两个数组，排除已经在附表中的数组
function subArray(a, b) {
        var result = [];
        for (var i in a) {
            if ($.inArray(a[i], b) == -1)
                result.push(a[i]);
        }
        return result;
    }
    //提交副表的主键
$("#application").submit(function (e) {
    e.preventDefault();
    var formData = $("#application").serialize();
    var tableData = $("#sublist").jqGrid('getDataIDs');
    console.log(formData);
    console.log(tableData);
});
//在colModel中设定key:true确定主键。默认是一个自增量
//name: 'reclaimStorageNo',
//sorttype:'integer',
//key:true,
//searchoptions:{sopt:['cn'],readonly: false, 
//dataEvents: [{ type: 'keypress', 
//fn: function (e) {this.value=this.value.replace(/\s+/g,""); } }]}
//所选需要的数据填到副表
$("#moveToRight").click(function () {
    var group = jQuery("#list").jqGrid('getGridParam', 'selarrrow');
    var subgroup = jQuery("#sublist").jqGrid('getDataIDs');
    //剔除数组中重复的部分
    //do something
    group = subArray(group, subgroup);
    var dataRow = [];
    for (var i = 0; i < group.length; i++) {
        var index = group[i];
        var reclaimStorageNo = $("#list").getCell(index, "reclaimStorageNo");
        var productBrand = $("#list").getCell(index, "productBrand");
        var productModel = $("#list").getCell(index, "productModel");
        var row = {};
        row.reclaimStorageNo = reclaimStorageNo;
        row.productBrand = productBrand;
        dataRow.push(row);
    }
    //通过dataRow在副表填数据
    $("#sublist").jqGrid("addRowData", "reclaimStorageNo", dataRow, "first");
    //清空所选
    $("#list").jqGrid("resetSelection");
    //按需要排序
    $("#sublist").sortGrid('reclaimStorageNo', true);
});
//将副表不需要的数据移回
jQuery("#moveToLeft").click(function () {
    var selectedRowIds = $("#sublist").jqGrid("getGridParam", "selarrrow");
    var len = selectedRowIds.length;
    for (var i = 0; i < len; i++) {
        $("#sublist").jqGrid("delRowData", selectedRowIds[0]);
    }
});