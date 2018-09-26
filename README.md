# Apache Nutch and Apache Solr PoC on Docker Swarm
An ultra small PoC to show how to combine Apache Nutch and Apache Solr, crawling through web pages and storing the results in Solr for quering

## Why?
This is a very very very simple implementation with which any website can be crawled.
Everyone who is able to install Docker is able to run this.
##### Yeah, but why?
This example can be used for many purposes:
* (Security) testing how a search tree of a published website would look
* Searching for text on an unindexed (local?) websites to find content
* As a starting point of building your own Google (please don't, just don't, this stuff doesn't scale, use storm-crawler + Hadoop for that)
* Etc.

## Prerequisites
* [Docker desktop](https://www.docker.com/products/docker-desktop) (enable shared C: in its settings!)

## How to use
```bash
docker-compose up
```

## How it works
A default Solr instance with the default "mycore" core is used to store Nutch crawling results.
The approach of this PoC is to use as less custom configuration as possible so it can be used as a starting point for other uses.
Some important files:
* seed.txt: The starting urls on which the crawl should start
* regex-urlfilter.txt: The filter which is used to only filter out targeted urls
* index-writers.xml: The Nutch config which is used to link Nutch and Solr
* docker-compose.yml: The infrastructure configuration, including the Nutch start command

## Adjusting this demo
* The ```/nutch``` folder contains all Nutch configuration

## Author
* [Sebastiaan Raven](mailto:basraven@gmail.com)