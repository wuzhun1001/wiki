## #DAC API


<div class="bi-table">
  <table>
    <colgroup>
      <col width="90px" />
      <col width="90px" />
    </colgroup>
    <tbody>
      <tr>
        <td rowspan="1" colSpan="1">
          <div data-type="p">API</div>
        </td>
        <td rowspan="1" colSpan="1">
          <div data-type="p">说明</div>
        </td>
      </tr>
      <tr>
        <td rowspan="1" colSpan="1">
          <div data-type="p">DAC.open(id)</div>
        </td>
        <td rowspan="1" colSpan="1">
          <div data-type="p"><span data-type="color" style="color:#F5222D">功能：</span>打开dac</div>
          <div data-type="p"><span data-type="color" style="color:#F5222D">参数：</span> id:和板级配置文件中的id保持一致</div>
          <div data-type="p"><span data-type="color" style="color:#F5222D">返回值：</span>成功：回资源handle，失败：-1</div>
        </td>
      </tr>
      <tr>
        <td rowspan="1" colSpan="1">
          <div data-type="p">DAC.close(handle)</div>
        </td>
        <td rowspan="1" colSpan="1">
          <div data-type="p"><span data-type="color" style="color:#F5222D">功能：</span>关闭dac </div>
          <div data-type="p"><span data-type="color" style="color:#F5222D">参数：</span> handle:资源handle，为DAC.open的返回值; </div>
          <div data-type="p"><span data-type="color" style="color:#F5222D">返回值：</span>0=ok other=fail </div>
          <div data-type="p"></div>
        </td>
      </tr>
      <tr height="34px">
        <td rowspan="1" colSpan="1">
          <div data-type="p">DAC.setVol(handle,vol)</div>
        </td>
        <td rowspan="1" colSpan="1">
          <div data-type="p"><span data-type="color" style="color:#F5222D">功能：</span>设置dac输出电压 </div>
          <div data-type="p"><span data-type="color" style="color:#F5222D">参数：</span> handle:资源handle，为DAC.open的返回值;  </div>
          <div data-type="p">           vol：电压值 </div>
          <div data-type="p"><span data-type="color" style="color:#F5222D">返回值：</span>0=ok other=fail </div>
          <div data-type="p"></div>
        </td>
      </tr>
      <tr height="34px">
        <td rowspan="1" colSpan="1">
          <div data-type="p">DAC.getVol(handle)</div>
        </td>
        <td rowspan="1" colSpan="1">
          <div data-type="p"><span data-type="color" style="color:#F5222D">功能：</span>获取当前dac电压; </div>
          <div data-type="p"><span data-type="color" style="color:#F5222D">参数：</span> handle:资源handle; </div>
          <div data-type="p"><span data-type="color" style="color:#F5222D">返回值：</span>电压值;
          </div>
        </td>
      </tr>
    </tbody>
  </table>
</div>


## #板级配置参数


<div class="bi-table">  <table>    <colgroup>      <col width="90px" />      <col width="90px" />      <col width="90px" />    </colgroup>    <tbody>      <tr height="34px">        <td rowspan="1" colSpan="1">          <div data-type="p"><span data-type="color" style="color:rgb(38, 38, 38)"><span data-type="background" style="background-color:rgb(250, 250, 250)">参数名</span></span>          </div>        </td>        <td rowspan="1" colSpan="1">          <div data-type="p">类型/功能/值</div>        </td>        <td rowspan="1" colSpan="1">          <div data-type="p">说明</div>        </td>      </tr>      <tr height="34px">        <td rowspan="1" colSpan="1">          <div data-type="p">&quot;id&quot;</div>        </td>        <td rowspan="1" colSpan="1">          <div data-type="p"><span data-type="color" style="color:#F5222D">功能：</span>资源唯一性标志; </div>          <div data-type="p">            <span data-type="color" style="color:#F5222D">类型：</span>string </div>          <div data-type="p">            <span data-type="color" style="color:#F5222D">值：</span>任意，保持数组内id值唯一;</div>        </td>        <td rowspan="1" colSpan="1">          <div data-type="p">该id值和js层GPIO.open时的id值保持一致;</div>        </td>      </tr>      <tr height="34px">        <td rowspan="1" colSpan="1">          <div data-type="p">&quot;port&quot;</div>        </td>        <td rowspan="1" colSpan="1">          <div data-type="p"><span data-type="color" style="color:#F5222D">功能：</span>端口值; </div>          <div data-type="p"><span data-type="color" style="color:#F5222D">类型：</span>number </div>          <div data-type="p">            <span data-type="color" style="color:#F5222D">值：</span>和板级资源描述保持一致；</div>        </td>        <td rowspan="1" colSpan="1">          <div data-type="p">该port值和HAL层API对应的port保持一致；</div>        </td>      </tr>      <tr height="34px">        <td rowspan="1" colSpan="1">          <div data-type="p">&quot;voltage&quot;</div>        </td>        <td rowspan="1" colSpan="1">          <div data-type="p"><span data-type="color" style="color:#F5222D">功能：</span>默认输出电平; </div>          <div data-type="p">            <span data-type="color" style="color:#F5222D">类型：</span>number </div>          <div data-type="p">            <span data-type="color" style="color:#F5222D">值：</span>依据实际情况进行配置；</div>        </td>        <td rowspan="1" colSpan="1">          <div data-type="p"></div>        </td>      </tr>    </tbody>  </table></div>

## #板级配置示范
```json
/*apps/js/board_config.json*/
{

	"DAC":[
		{
		"id":"led",
		"port":1,
		"voltage":255
		}
	]

}
```
## #ESP32之LED模块
### #硬件

1)esp32Kit开发板
2)LED模块


![1.png | left | 425x456](https://cdn.yuque.com/lark/0/2018/png/66207/1525864337606-ccbd6660-dd79-4ab4-99aa-c2ab4f41ec9b.png "")

### #接线

EPS32 IO25引脚 连接 LED模块的正极；
EPS32 GND引脚 连接 LED模块的负极；

### #配置

```json
/*apps/js/board_config.json*/
{

	"DAC":[
		{
		"id":"led",
		"port":1,
		"voltage":255
		}
	]

}
```

### #代码

```javascript
var led_handle = DAC.open('led');
var cur_voltage = DAC.getVol(led_handle);
console.log('cur_voltage:'+cur_voltage);
setInterval(function(){

	cur_voltage  = cur_voltage + 1;
	if(cur_voltage >= 255){
		cur_voltage = 0;
	}
	DAC.setVol(led_handle,cur_voltage);
},50);
```

### #现象

LED亮度由弱变强，当低于某个值是，LED完全熄灭；

## #TODO


 