时间选择器
===============================
 
###Options

*   container: 容器，一般为document.body
*   dom：在指定元素上绑定选择器，通常为input，如果不指定dom，则选择器会直接显示在container中，不会消失，除非手动调用close
*   className：选择器额外的类名
*   selectedClassName: 选中某个时间时的样式
*   closeAfterSelect：选择后，是否关闭，此参数只有在dom不为空时才会起作用
*   disabled：禁用时间类型列表

 
###Events
 
*   select(event, value)
*   open: 打开时触发
*   close：关闭时触发

###Api

*   disable(type)：禁用某个时间， type为0|1|2，分别表示 时、分、秒 
*   enable(type)：启用某个时间选择
*   open：打开选择器
*   close: 关闭选择器
*   destroy: 摧毁对象
 
###Example

```html
<input type="text" id="timepicker" readonly="readonly" style="position: absolute; top: 500px;"/>
<script>
$('#timepicker').timepicker({
    disabled: ['hours']
}).on('timepicker:select', function(event, v, a){
    console.log(v, a);
    console.log($(this).timepicker('instance').getTime());
})
</script>
```