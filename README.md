# -<!DOCTYPE html>
<html lang="zh">
<head>
<meta charset="UTF-8">
<title>企业数据中心</title>

<script src="https://cdn.jsdelivr.net/npm/echarts/dist/echarts.min.js"></script>

<style>

body{
margin:0;
font-family:Arial;
background:#0f172a;
color:white;
}

.header{
padding:20px;
background:#020617;
display:flex;
justify-content:space-between;
}

.logo{
font-size:24px;
}

.container{
padding:30px;
}

.grid{
display:grid;
grid-template-columns:repeat(3,1fr);
gap:20px;
}

.card{
background:#1e293b;
padding:25px;
border-radius:10px;
transition:0.3s;
}

.card:hover{
background:#334155;
transform:translateY(-5px);
}

.card a{
color:#38bdf8;
text-decoration:none;
}

.chart{
margin-top:40px;
height:400px;
}

</style>

</head>

<body>

<div class="header">
<div class="logo">企业数据中心</div>
<div id="time"></div>
</div>

<div class="container">

<div class="grid">

<div class="card">
<h3>后台管理系统</h3>
<a href="/admin">进入</a>
</div>

<div class="card">
<h3>信誉评分系统</h3>
<a href="/credit">进入</a>
</div>

<div class="card">
<h3>保证金管理</h3>
<a href="/deposit">进入</a>
</div>

<div class="card">
<h3>税务督查</h3>
<a href="/tax">进入</a>
</div>

<div class="card">
<h3>异常提醒</h3>
<a href="/alerts">进入</a>
</div>

<div class="card">
<h3>数据报表中心</h3>
<a href="/report">进入</a>
</div>

</div>

<div id="chart" class="chart"></div>

</div>

<script>

function updateTime(){
document.getElementById("time").innerText=new Date().toLocaleString()
}

setInterval(updateTime,1000)

var chart=echarts.init(document.getElementById('chart'))

chart.setOption({
title:{text:'系统统计'},
tooltip:{},
xAxis:{
data:['信誉分','保证金','异常数']
},
yAxis:{},
series:[{
type:'bar',
data:[85,12000,3]
}]
})

</script>

</body>
</html>
