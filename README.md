<!DOCTYPE html>
<html>
   
   <head>
      <script type = "text/javascript" src = "js/d3.min.js"></script>
      <style>
         /*svg rect {
            fill: #0000ff;
         }/*
         
         svg text {
            fill: #ffffff;
            font: 12px sans-serif;
            text-anchor: end;
         }
      </style>
   </head>
   

   <body>
        <svg width = "400" height = "400"></svg>
        <H3>Exercícios aula da aula de visualização do conhecimento </H3>
        <p><a href="baschart.html">Exemplo de gráfico de barras</a></p>
        <p><a href="animated_baschart.html">Exemplo de gráfico de barras animado</a></p>
        <p><a href="donutchart.html">Exemplo de gráfico de donuts</a></p>
        <p><a href="circlechart.html">Exemplo de gráfico de setores</a></p>
        <p><a href="lineghaph.html">Exemplo de gráfico de círculos</a></p>
        <p><a href="piechart.html">Exemplo de gráfico de torta</a></p>

        <iframe src="barchart.html" style="height:200px;width:300px;"></iframe> 

        <script>
            var data = [10, 5, 12, 15, 20, 70];
            var colors = ['green', 'purple', 'yellow' , 'magenta' , 'blue' , 'brown'];
            
            var width = 700 
                scaleFactor = 10, 
                barHeight = 30;
            
            var graph = d3.select("body")
                .append("svg")
                .attr("width", width)
                .attr("height", barHeight * data.length);
            
            var bar = graph.selectAll("g")
                .data(data)
                .enter()
                .append("g")
                .attr("transform", function(d, i) {
                return "translate(0," + i * barHeight + ")";      
                })
            .attr("fill", function(d, i){
                    return colors[i];
            })
                bar.append("rect").attr("width", function(d) {
                    return d * scaleFactor;
                })
            
            .attr("height", barHeight - 1);
            
            bar.append("text")
                .attr("x", function(d) { return (d*scaleFactor); })
                .attr("y", barHeight / 2)
                .attr("dy", ".35em")
                .text(function(d) { return d; });
        </script>

     
   </body>
</html>
