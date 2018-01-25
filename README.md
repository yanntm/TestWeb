# TestWeb


My firs chart !



  <script type="text/javascript" src="https://www.gstatic.com/charts/loader.js"></script>
  <script type="text/javascript">
    google.charts.load('current', {'packages':['gauge']});
    google.charts.setOnLoadCallback(drawGauge);

    var gaugeOptions = {min: 0, max: 280, yellowFrom: 200, yellowTo: 250,
      redFrom: 250, redTo: 280, minorTicks: 5};
    var gauge;

    function drawGauge() {
      gaugeData = new google.visualization.DataTable();
      gaugeData.addColumn('number', 'Engine');
      gaugeData.addColumn('number', 'Torpedo');
      gaugeData.addRows(2);
      gaugeData.setCell(0, 0, 120);
      gaugeData.setCell(0, 1, 80);

      gauge = new google.visualization.Gauge(document.getElementById('gauge_div'));
      gauge.draw(gaugeData, gaugeOptions);
    }

    function changeTemp(dir) {
      gaugeData.setValue(0, 0, gaugeData.getValue(0, 0) + dir * 25);
      gaugeData.setValue(0, 1, gaugeData.getValue(0, 1) + dir * 20);
      gauge.draw(gaugeData, gaugeOptions);
    }
  </script>
 </head>
 <body>
  <div id="gauge_div" style="width:280px; height: 140px;"></div>
  <input type="button" value="Go Faster" onclick="changeTemp(1)" />
  <input type="button" value="Slow down" onclick="changeTemp(-1)" />
 </body>

