# COVID-Tracker 

COVID-19 tracker made with [InfluxDB](https://www.influxdata.com/), and [Grafana](https://grafana.com/).  
Data used for the world map panel is from [TrackCorona API](https://www.trackcorona.live/api) and the data used for the CDR and Trend panels are from 
[Kaggle Novel Corona Virus 2019 Dataset](https://www.kaggle.com/sudalairajkumar/novel-corona-virus-2019-dataset?select=covid_19_data.csv).  
Project was made following this [tutorial](https://www.youtube.com/watch?v=CSzxHBlVkRw&ab_channel=techwithshakul).

----------------------------------------
## Usage
Install the requirements:
```sh
pip install requirements.txt
```

Start Grafana and Influx servers:
```sh
sudo systemctl start grafana-server
sudo systemctl start influxdb
```

Create the database:
```sh
influx
> create database covid
```

Insert the world map and metric data to database:
```sh
python map.py
python metric.py
```

Go to the local Grafana dashboard at [http://localhost:3000](http://localhost:3000) and create the appropriate panels for each data.
