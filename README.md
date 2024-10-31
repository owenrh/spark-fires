![Spark-fires - we set fire to Spark apps so you don't have to!](notebooks/img/this-is-fine-spark.jpeg?raw=true)

## Spark-fires - we set fire to Spark apps so you don't have to!

**Spark fires** is a anti-pattern playground where we deliberately break Spark applications in various ways so you can observe what happens and potentially recognise the issue when you come across it in your day-to-day development and support activities.

We plan to cover all the common scenarios you might hit in production, technical interview questions and a lot more.

### Scenarios
The Spark-fires playground is scenario-based. Each scenario is [documented and run via a Jupyter notebook](notebooks) - so you can step through it, see the impact of different fixes, try different settings yourself, all while viewing the application behaviour in the Spark UI. 

#### Bootstrapping
For ease of use, the project is self-contained and has a [Docker Compose](https://docs.docker.com/compose/) file capable of starting a local Spark cluster with three workers. 

##### Docker Requirements
The default cluster configuration will start three Spark Worker nodes with 2 cores and 2G memory each. If this is too much for your machine feel free to tweak as needed. _Note, the pre-baked scenarios will work best with the default configuration provided._

##### Roll-your-own
Alternatively, if you prefer you can download Spark directly, configure as desired and start the cluster components manually. 

##### Starting the cluster
The Spark cluster configuration is defined in the Docker Compose file here - [docker-compose.yaml](docker-compose.yaml). 

The Spark cluster can be started using the following command from the repo root directory:
```
docker compose up
```

Note, this will take a while the first time, as it will need to download the container images, etc. After that, it will only take a few seconds.

##### Cluster UIs
Once started the key cluster UIs should be available at:
 * Spark Master - http://localhost:8080/#/
 * Spark UI (once an app has been started) - http://localhost:4040/jobs/
 * Jupyter Lab - you can grab the URL or token from the docker compose output in your terminal (you may have to scroll up a little!)
   * http://127.0.0.1:8888/lab?token=<grab your token/URL from the startup logs>

#### Scenarios

*New scenarios are arriving in the coming weeks.*

Currently available scenarios are:
* [hot-node](notebooks/hot-node.ipynb) [(local Jupyter)](http://127.0.0.1:8888/lab/tree/work/hot-node.ipynb)
* [show on uncached dataframe](notebooks/show-on-uncached-df.ipynb) [(local Jupyter)](http://127.0.0.1:8888/lab/tree/work/show-on-uncached-df.ipynb)
* [premature dataframe caching](notebooks/premature-caching.ipynb) [(local Jupyter)](http://127.0.0.1:8888/lab/tree/work/premature-caching.ipynb)
* [more cores than partitions](notebooks/more-cores-than-partitions.ipynb) [(local Jupyter)](http://127.0.0.1:8888/lab/tree/work/more-cores-than-partitions.ipynb)
* [the perils of small files](notebooks/small-files-issues.ipynb) [(local Jupyter)](http://127.0.0.1:8888/lab/tree/work/small-files-issues.ipynb)
* [unnecessary UDFs](notebooks/unnecessary-udfs.ipynb) [(local Jupyter)](http://127.0.0.1:8888/lab/tree/work/unnecessary-udfs.ipynb)

### Accompanying videos

*[Coming soon, if folk show some interest!](https://www.youtube.com/@spark-fires-kz5qt/community)*
