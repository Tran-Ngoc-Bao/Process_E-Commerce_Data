# Mini project - Data Engineering - Viettel Digital Talent 2024

## Project introduction
<ul>
  <li>Name of project: Analyze e-commerce information on Shopee</li>
  <li>Project objective:
    <ul>
      <li>Top well-rated products by item</li>
      <li>Top liked products by item</li>
      <li>Top products on strong sale</li>
      <li>Top products with the most comments</li>
      <li>Top best selling products</li>
    </ul>
  </li>
</ul>

## Data flow
  <img src="https://github.com/Tran-Ngoc-Bao/ProcessShopeeData/blob/master/illustration/DataFlow.png">

## Deploy system
<ul>
  <li>You should download images before</li>
  
```sh
docker pull { ... }
```

  <li>Move to clone project and Start system</li>
  
```sh
docker compose up -d
```

  <li>After start system, all port website of containers in <a href="https://github.com/Tran-Ngoc-Bao/ProcessShopeeData/blob/master/port.txt">here</a></li>
  <li>Start DAG in Airflow cluster</li>
  <li>Move to spark-iceberg container</li>

```sh
docker exec -it spark-iceberg bash
```

  <li>Run code pyspark in spark-iceberg</li>

```sh
bin/spark-submit /home/iceberg/code/main.py
```

  <li>Move to trino container</li>

```sh
docker exec -it trino bash
```

  <li>Run code sql in trino</li>

```sh
trino -f { /etc/trino/code/query1.sql, /etc/trino/code/query2.sql, /etc/trino/code/query3.sql, /etc/trino/code/query4.sql }
```

  <li>Visualize data in Superset website on local</li>
</ul>

## Output
### Top well-rated products by item
<img style="width:70%" src="https://github.com/Tran-Ngoc-Bao/ProcessShopeeData/blob/master/illustration/output/top_rate_Balo_%26_Tui_Vi_Nam.jpg">

### Top liked products by item
<img style="width:70%" src="https://github.com/Tran-Ngoc-Bao/ProcessShopeeData/blob/master/illustration/output/top_like_Thoi_Trang_Nam.jpg">

### Top products with the most comments
<img style="width:70%" src="https://github.com/Tran-Ngoc-Bao/ProcessShopeeData/blob/master/illustration/output/top_comment.jpg">

## Report
<ul>
  <li><a href="https://github.com/Tran-Ngoc-Bao/ProcessShopeeData/blob/master/report/report.pdf">Report</a></li>
  <li><a href="https://github.com/Tran-Ngoc-Bao/ProcessShopeeData/blob/master/report/slide.pptx">Slide</a></li>
</ul>
