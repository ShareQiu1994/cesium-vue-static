<template>
   <div id="cesiumContainer">


         <div style="z-index:9999;position: absolute;top: 20px;left: 20px; color:#fff;">
    <input class="draw" type="radio" name="draw" value="0" checked="checked">贴地形
    <input class="draw" type="radio" name="draw" value="1">空间
</div>
<div style="z-index:9999;position: absolute;top: 50px;left: 20px;">
    <button id="point">画点</button>
    <button id="line">画线</button>
    <button id="polygon">画面</button>
    <button id="elevation">量高</button>
    <button id="mpoint">m画点</button>
    <button id="mline">m画线</button>
    <button id="mpolygon">m画面</button>
    <button id="melevation">m量高</button>
    <button id="remove">移除</button>
</div>


   </div>
</template>
<script>
export default {
  name: 'cesiumContainer',
  mounted(){
      var viewer = new Cesium.Viewer('cesiumContainer');
       viewer.extend(Cesium.viewerCesiumNavigationMixin, {});
      
       const tool =  new Cesium.DrawTool({
	        viewer:viewer,
	        isMeasure:true,  // 是否开启测量模式
	        isClampGround:true,  // 是否开启贴地模式
	        // lineWidth:1.0    // 设置线宽
       });
      
      	 document.getElementById('point').onclick = function() {
		        tool.startPoint()  // 画点
		    };
		    document.getElementById('line').onclick = function() {
		        tool.startPolyline()  // 画线
		    };
		    document.getElementById('polygon').onclick = function() {
		        tool.startPolygon();  // 画面
		    };
		    document.getElementById('elevation').onclick = function() {
		        tool.startElevation();  // 量高
		    };
		    document.getElementById('mpoint').onclick = function() {
		        tool.startModelPoint() // 模型画点
		    };
		    document.getElementById('mline').onclick = function() {
		        tool.startModelPolyline()  // 模型画线
		    };
		    document.getElementById('mpolygon').onclick = function() {
		        tool.startModelPolygon();  // 模型画面
		    };
		    document.getElementById('melevation').onclick = function() {
		        tool.startModelElevation();  // 模型量高
		    };
		    document.getElementById('remove').onclick = function() {
		        tool.destory()
		    };

		   const radios = document.getElementsByName('draw');
		   for(let item of radios){
		        item.onclick = function() {
		            if(item.checked && item.value == 0){
		                tool.setIsClampGround(true)  // 设置是否开启贴地模式
		            }else{
		                tool.setIsClampGround(false)
		            }
		        }
        }
        
  }
}
</script>
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>