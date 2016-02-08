<!DOCTYPE html>
<head>
    <meta charset="utf-8">
    <title>ECharts</title>
</head>
<body>

<h1 style="text-align:center;">About Cancer</h1>
<h2 style="text-align:center;">datas from WHO</h2>

<p>This artical is about cancer globally.All contents comes from WHO's report in 2015--Health in 2015 from MDGs to SDGs.Here are what we should pay attention.We will analyse it.</p>
<p>In 2012, the worldwide incidence of cancer rose to an estimated 14 million new cases per year, with an estimated 8.2 million cancer deaths.Globally, in 2012 the most common cancers diagnosed were those those of
the lung (1.8 million cases, 13% of the total), breast (1.7 million, 11.9%) and colon (1.4 million, 9.7%):</p>



   
    <div id="main1" style="height:400px"></div>
   
    <script src="http://echarts.baidu.com/build/dist/echarts.js"></script>
    <script type="text/javascript">
      
        require.config({
            paths: {
                echarts: 'http://echarts.baidu.com/build/dist'
            }
        });
        
       
        require(
            [
                'echarts',
                'echarts/chart/pie' 
            ],
            function (ec) {
                
                var myChart = ec.init(document.getElementById('main1')); 
                
               var labelTop = {
    normal : {
        label : {
            show : true,
            position : 'center',
            formatter : '{b}',
            textStyle: {
                baseline : 'bottom'
            }
        },
        labelLine : {
            show : false
        }
    }
};
var labelFromatter = {
    normal : {
        label : {
            formatter : function (params){
                return 100 - params.value + '%'
            },
            textStyle: {
                baseline : 'top'
            }
        }
    },
}
var labelBottom = {
    normal : {
        color: '#ccc',
        label : {
            show : true,
            position : 'center'
        },
        labelLine : {
            show : false
        }
    },
    emphasis: {
        color: 'rgba(0,0,0,0)'
    }
};
var radius = [40, 55];
option = {
    legend: {
        x : 'center',
        y : 'center',
        data:[
              'lung cancer','breast cancre','colon cancer'
        ]
    },
    title : {
        text: 'The Most Common Cancer Worldwide in 2012',
        subtext: 'from WHO',
        x: 'center'
    },
    toolbox: {
        show : true,
        feature : {
            dataView : {show: true, readOnly: false},
            magicType : {
                show: true, 
                type: ['pie', 'funnel'],
                option: {
                    funnel: {
                        width: '20%',
                        height: '30%',
                        itemStyle : {
                            normal : {
                                label : {
                                    formatter : function (params){
                                        return 'other\n' + params.value + '%\n'
                                    },
                                    textStyle: {
                                        baseline : 'middle'
                                    }
                                }
                            },
                        } 
                    }
                }
            },
            restore : {show: true},
            saveAsImage : {show: true}
        }
    },
    series : [
        {
            type : 'pie',
            center : ['20%', '30%'],
            radius : radius,
            x: '0%', // for funnel
            itemStyle : labelFromatter,
            data : [
                {name:'other', value:87, itemStyle : labelBottom},
                {name:'lung cancer', value:13,itemStyle : labelTop}
            ]
        },
        {
            type : 'pie',
            center : ['50%', '30%'],
            radius : radius,
            x:'20%', // for funnel
            itemStyle : labelFromatter,
            data : [
                {name:'other', value:88, itemStyle : labelBottom},
                {name:'breast cancer', value:12,itemStyle : labelTop}
            ]
        },
        {
            type : 'pie',
            center : ['80%', '30%'],
            radius : radius,
            x:'40%', // for funnel
            itemStyle : labelFromatter,
            data : [
                {name:'other', value:90, itemStyle : labelBottom},
                {name:'colon cancer', value:10,itemStyle : labelTop}
            ]
        },
        ]
};
                    
                
                myChart.setOption(option); 
            }
        );
    </script>


<p>The most common causes of cancer death were cancers of the lung (1.6 million, 19.4% of total cancer deaths),liver (0.7 million, 9.1%) and stomach (0.7 million, 8.8%).</p>



    <div id="main2" style="height:400px"></div>
    
    <script src="http://echarts.baidu.com/build/dist/echarts.js"></script>
    <script type="text/javascript">
        
        require.config({
            paths: {
                echarts: 'http://echarts.baidu.com/build/dist'
            }
        });
        
        
        require(
            [
                'echarts',
                'echarts/chart/bar'
            ],
            function (ec) {
                
                var myChart = ec.init(document.getElementById('main2')); 
                
               option = {
    title : {
        text: 'The Most Common Cause of Cancer Death',
        subtext: 'from WHO'
    },
    tooltip : {
        trigger: 'axis'
    },
    legend: {
        data:['population','percent']
    },
    toolbox: {
        show : true,
        feature : {
            mark : {show: true},
            dataView : {show: true, readOnly: false},
            magicType : {show: true, type: ['line', 'bar']},
            restore : {show: true},
            saveAsImage : {show: true}
        }
    },
    calculable : true,
    xAxis : [
        {
            type : 'category',
            data : ['lung cancer','liver cancer','colon cancer']
        }
    ],
    yAxis : [
        {
            type : 'value'
        }
    ],
    series : [
        {
            name:'population',
            type:'bar',
            data:[1.6, 0.7, 0.7],
            
        },
        {
            name:'percent',
            type:'line',
            data:[19.4,9.1,8.8,],
           
        }
    ]
};
    
               
                myChart.setOption(option); 
            }
        );
                    
    </script>

<h3>HORRIBLE CANCER</h3>
<p>Six leading cancer causes of death globally, by sex, 2012</p>
<p>Firstly,it is the datas of females.</p>
    
    <div id="main3" style="height:400px"></div>
    
    <script src="http://echarts.baidu.com/build/dist/echarts.js"></script>
    <script type="text/javascript">
       
        require.config({
            paths: {
                echarts: 'http://echarts.baidu.com/build/dist'
            }
        });
        
        
        require(
            [
                'echarts',
                'echarts/chart/bar' 
            ],
            function (ec) {
              
                var myChart = ec.init(document.getElementById('main3')); 
                
                var labelRight = {normal: {label : {position: 'right'}}};
option = {
    title: {
        text: 'Six Leading Cancer Causes of Death Globallyof Females',
        subtext: 'From WHO',    
    },
    tooltip : {
        trigger: 'axis',
        axisPointer : {            
            type : 'shadow'       
        }
    },
    toolbox: {
        show : true,
        feature : {
            mark : {show: true},
            dataView : {show: true, readOnly: false},
            magicType : {show: true, type: ['line', 'bar']},
            restore : {show: true},
            saveAsImage : {show: true}
        }
    },
    grid: {
        y: 80,
        y2: 30
    },
    xAxis : [
        {
            type : 'value',
            position: 'top',
            splitLine: {lineStyle:{type:'dashed'}},
        }
    ],
    yAxis : [
        {
            type : 'category',
            axisLine: {show: false},
            axisLabel: {show: false},
            axisTick: {show: false},
            splitLine: {show: false},
            data : ['breast cancer', 'trachea/bronchus/lung cancers', 'colon/rectum cancers', 'Cervix uteri cancer', 'Stomach cancer', 'Liver cancer']
        }
    ],
    series : [
        {
            name:'trends in the death rates',
            type:'bar',
            stack: '????',
            itemStyle : { normal: {
                color: 'orange',
                borderRadius: 5,
                label : {
                    show: true,
                    position: 'left',
                    formatter: '{b}'
                }
            }},
            data:[
                {value:-8, itemStyle:labelRight},
                 9,
                {value:-8, itemStyle:labelRight},
                 
                {value:-12, itemStyle:labelRight},
     
                {value:-21, itemStyle:labelRight},
                7,
                
            ]
        }
    ]
};
                    
        
                
                myChart.setOption(option); 
            }
        );
    </script>

<p>Secondly,it is the datas of males</p>

  
    <div id="main4" style="height:400px"></div>
    
    <script src="http://echarts.baidu.com/build/dist/echarts.js"></script>
    <script type="text/javascript">
        
        require.config({
            paths: {
                echarts: 'http://echarts.baidu.com/build/dist'
            }
        });
      
        require(
            [
                'echarts',
                'echarts/chart/bar'
            ],
            function (ec) {
                
                var myChart = ec.init(document.getElementById('main4')); 
                
                var labelRight = {normal: {label : {position: 'right'}}};
option = {
    title: {
        text: 'Six Leading Cancer Causes of Death Globally of Males',
        subtext: 'From WHO',    
    },
    tooltip : {
        trigger: 'axis',
        axisPointer : {           
            type : 'shadow'       
        }
    },
    toolbox: {
        show : true,
        feature : {
            mark : {show: true},
            dataView : {show: true, readOnly: false},
            magicType : {show: true, type: ['line', 'bar']},
            restore : {show: true},
            saveAsImage : {show: true}
        }
    },
    grid: {
        y: 80,
        y2: 30
    },
    xAxis : [
        {
            type : 'value',
            position: 'top',
            splitLine: {lineStyle:{type:'dashed'}},
        }
    ],
    yAxis : [
        {
            type : 'category',
            axisLine: {show: false},
            axisLabel: {show: false},
            axisTick: {show: false},
            splitLine: {show: false},
            data : [ 'trachea/bronchus/lung cancers','Liver cancer', 'Stomach cancer', 'colon/rectum cancers','Prostate cancer','Oesophagus cancer' ]
        }
    ],
    series : [
        {
            name:'trends in the death rates',
            type:'bar',
            stack: '????',
            itemStyle : { normal: {
                color: 'orange',
                borderRadius: 5,
                label : {
                    show: true,
                    position: 'left',
                    formatter: '{b}'
                }
            }},
            data:[
                {value:-4, itemStyle:labelRight},
                 
                {value:-2, itemStyle:labelRight},
                 
                {value:-20, itemStyle:labelRight},
     
                {value:-7, itemStyle:labelRight},
              {value:-8,itemStyle:labelRight},
              {value:-8,itemStyle:labelRight},
      
            ]
        }
    ]
};
                    
                
                myChart.setOption(option); 
            }
        );
    </script>

<h4>Here are trends in the death rates globally and by region, 2000?C2012.</h4>
<table border="1">
<tr>
  <th>Global 2012 rank</th>
  <th>Cancer type</th>
  <th>AFR</th>
  <th>AMR</th>
  <th>SEAR</th>
  <th>EUR</th>
  <th>EMR</th>
  <th>WPR</th>
  <th>High income OECD</th>
</tr>

<tr>
  <th colspan="9">Females</th>
</tr>

<tr>
  <th>1</th>
  <th>Breast cancer</th>
  <td bgcolor="blue"></td>
  <td bgcolor="yellow"></td>
  <td bgcolor="red"></td>
  <td bgcolor="yellow"></td>
  <td bgcolor="yellow"></td>
  <td bgcolor="blue"></td>
  <td bgcolor="red"></td>
</tr>

<tr>
  <th>2</th>
  <th>Trachea, bronchus, lung cancers</th>
  <td bgcolor="yellow"></td>
  <td bgcolor="yellow"></td>
  <td bgcolor="blue"></td>
  <td bgcolor="yellow"></td>
  <td bgcolor="red"></td>
  <td bgcolor="blue"></td>
  <td bgcolor="yellow"></td>
</tr>

<tr>
  <th>3</th>
  <th>Colon and rectum cancers</th>
   <td bgcolor="yellow"></td>
 <td bgcolor="yellow"></td>
 <td bgcolor="yellow"></td>
 <td bgcolor="yellow"></td>
 <td bgcolor="yellow"></td>
 <td bgcolor="blue"></td>
 <td bgcolor="red"></td>
</tr>

<tr>
  <th>4</th>
  <th>Cervix uteri cancer</th>
  <td bgcolor="red"></td>
<td bgcolor="red"></td>
<td bgcolor="red"></td>
<td bgcolor="red"></td>
<td bgcolor="red"></td>
 <td bgcolor="blue"></td>
<td bgcolor="red"></td>
</tr>

<tr>
  <th>5</th>
  <th>Stomach cancer</th>
  <td bgcolor="red"></td>
<td bgcolor="red"></td>
<td bgcolor="yellow"></td>
</td>td bgcolor="red"></td>
<td bgcolor="red"></td>
<td bgcolor="red"></td>
<td bgcolor="red"></td>
</tr>

<tr>
  <th>6</th>
  <th>Liver cancer</th>
  <td bgcolor="red"></td>
<td bgcolor="red"></td>
<td bgcolor="yellow"></td>
<td bgcolor="yellow"></td>
<td bgcolor="blue"></td>
<td bgcolor="blue"></td>
 <td bgcolor="red"></td>
</tr>

<tr>
  <th colspan="9">Males</th>
</tr>

<tr>
  <th>1</th>
  <th>Trachea, bronchus, lung cancers</th>
  <td bgcolor="red"></td>
<td bgcolor="red"></td>
<td bgcolor="blue"></td>
<td bgcolor="red"></td>
<td bgcolor="yellow"></td>
<td bgcolor="blue"></td>
<td bgcolor="red"></td>
</tr>

<tr>
  <th>2</th>
  <th>Liver cancer</th>
  <td bgcolor="red"></td>
<td bgcolor="yellow"></td>
<td bgcolor="blue"></td>
<td bgcolor="yellow"></td>
<td bgcolor="blue"></td>
<td bgcolor="yellow"></td>
 <td bgcolor="red"></td>
</tr>

<tr>
  <th>3</th>
  <th>Stomach cancer</th>
 <td bgcolor="red"></td>
<td bgcolor="red"></td>
<td bgcolor="blue"></td>
<td bgcolor="red"></td>
<td bgcolor="red"></td>
<td bgcolor="red"></td>
<td bgcolor="red"></td>
</tr>

<tr>
  <th>4</th>
  <th>Colon and rectum cancers</th>
  <td bgcolor="blue"></td>
<td bgcolor="blue"></td>
<td bgcolor="blue"></td>
<td bgcolor="blue"></td>
<td bgcolor="yellow"></td>
<td bgcolor="yellow"></td>
<td bgcolor="red"></td>
</tr>

<tr>
  <th>5</th>
  <th>Prostate cancer</th>
 <td bgcolor="yellow"></td>
<td bgcolor="yellow"></td>
<td bgcolor="blue"></td>
<td bgcolor="blue"></td>
<td bgcolor="blue"></td>
<td bgcolor="blue"></td>
</tr>

<tr>
  <th>6</th>
  <th>Oesophagus cancer</th>
<td bgcolor="red"></td>
<td bgcolor="red"></td>
  <td bgcolor="blue"></td>
<td bgcolor="red"></td>
<td bgcolor="red"></td>
<td bgcolor="red"></td>
<td bgcolor="red"></td>
</tr>
</table>

<h4>graphic symbol</h4>
<table border="1">
<tr>
<td bgcolor="red">ASDR decreased by more than 5%</td>
</tr>
<tr>
<td bgcolor="blue">ASDR increased by more than 5%</td>
</tr>
<tr>
<td bgcolor="yellow">Between -5% and 5% change in ASD</td>
</tr>
</table>

<p>Lack of access to effective, timely diagnosis and treatment: In the absence of effective early detection programmes such as cancer awareness or screening, patients are diagnosed at very late stages when curative treatment is no longer an option. Population-based screening methods have been implemented for cancer of the cervix, breast and colon-rectum in some high-income countries. Screening,
however, is not widely implemented as the necessary resources
are not available in most regions. Furthermore, diagnostic services
including histopathology and treatment access are poor in many
low- and lower-middle-income countries, resulting in high cancerrelated
mortality. Immediate investment in human resources, health
services and sustainable supply chains are needed to provide timely
diagnosis and treatment.
</p>
<p>From WHO's report about cancer,we humankinds should take care of our own health,not only the money and other material things.</p>
</body>
    


</body>