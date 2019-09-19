# Redis

[How To Install and Use Redis] (https://www.digitalocean.com/community/tutorials/how-to-install-and-use-redis).

[How To Secure Your Redis Installation on Ubuntu (https://www.digitalocean.com/community/tutorials/how-to-secure-your-redis-installation-on-ubuntu-14-04).


*	Redis is an open source, BSD licensed.
*	in memory data structure store, used as database.
*	Redis stands for REmote DIctionary Server.
*	advanced key-value store.
*	read, write data as key-value.
*	there is no structure like table,row,column
*	keep data in cach
*	Redis is very fast. It can execute 100000 queries per second.
* 	Redis is written in ANSI C and mostly used for cache solution and session management
*	performence major feature
*	flexible
*	no statement like select insert update,
*	it has option to write data in disk and this option is configrable
*	master-slave replication feature
*	it is single threaded
*	Redis had a maximum of 2GB key length
*	It supports a server-side locking
*	Redis is portable.
*	It supports Atomic Operation.
*	It has got lots of client lib
*	Redis natively supports Publish/ Subscribe
*	It supports data structures such as strings, hashes, lists, sets, sorted sets with range queries, bitmaps, 
	hyperloglogs and geospatial indexes with radius queries.
*	any short lived data in your application like web application sessions, web page hit counts, etc.
*	Use redis-cli to access the server.
*	Redis can replicate data to any number of slaves.
*	Redis benchmark is the utility to check the performance of Redis by running n commands simultaneously.
*	Redis supports sharding. It is very easy to distribute the dataset across multiple Redis instances, like other key-value store.
*	redis-server is the Redis Server itself.
*	redis-sentinel is the Redis Sentinel executable (monitoring and failover).
*	redis-cli is the command line interface utility to talk with Redis.
*	redis-benchmark is used to check Redis performances.
*	redis-check-aof and redis-check-dump are useful in the rare event of corrupted data files.


![](redis.png)
	
##	Redis command

*	sudo service redis_6379 start
*	sudo service redis_6379 stop
*	sudo service redis_6379 restart
*	redis-cli ping
*	CONFIG get requirepass
*	CONFIG SET requirepass "LaxmanPassword"
*	AUTH password 
*	CONFIG GET *
*	CONFIG SET CONFIG_SETTING_NAME NEW_CONFIG_VALUE
*	config get maxclients
*	CLIENT LIST	
*	SAVE
*	BGSAVE

##	Pros of Redis:

*	it supports a wide variety of data types
*	great for large amounts of time-based events or logs.
*	it's simple to install and has no dependencies.
*	good platform for future analytical research into particular aggregations on event/log data.
*	easy to get started on a single cheap/free server.


##	Cons of Redis:

* 	The whole dataset always resides in RAM. It can cost you.
*	Persistency affects performance.
*	You should have more memory than your data requires.
*	data sets that can't be larger than memory.
*	Memory fragmentation issues. Writing and deleting huge amounts of data may result in performance degradation.
*	no joins or query language 


##	Redis Configration in ubuntu

*	Port           : 6379
*	Config file    : /etc/redis/6379.conf
*	Log file       : /var/log/redis_6379.log
*	Data dir       : /var/lib/redis/6379
*	Executable     : /usr/local/bin/redis-server
*	Cli Executable : /usr/local/bin/redis-cli


##	Install Redis
```js
	sudo apt-get update
	sudo apt-get install redis-server
	nano /etc/redis/redis.conf
		-	Make comment to bind line by adding #
		-	Find requirepass line and replace it with (PWD is password for making connection with redis) :
			requirepass PWD
		-	Find notify-keyspace-events "" and replace it with : 
			notify-keyspace-events "KEA"
	Restart Redis Server
		service redis-server restart
```