#ol3-echarts

echarts ol3 地图扩展

举例：
		// 初始化地图
        var ol3Ext = new OL3Extension(ol, echarts,{
            layers: [raster],
			target: 'newmap',
			view: new ol.View({
				center: ol.proj.transform([104.067923,30.679943], 'EPSG:4326', 'EPSG:3857'),
				zoom: 5
			})
        });
	    var container = ol3Ext.getEchartsContainer();
	    var option={
	    	........

		}
	    

	    if (myChart && myChart.dispose) {
			myChart.dispose();
		}
		//保证地图加载完成
		setTimeout(function(){
			myChart = ol3Ext.initECharts(container, curTheme);
			window.onresize = myChart.resize;
			ol3Ext.setOption(option, true);
			
		}, 1000); 


