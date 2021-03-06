# Jersey Connector using `java.net.http.HttpClient`
A Jersey connector using `java.net.http.HttpClient` and supporting HTTP/1.1 and HTTP/2.0 with the same client. The protocol is selected based on the server capabilities.

# Usage
To build a JAX-RS client, you can use the following. 
```java
var Client = ClientBuilder.newClient(new ClientConfig().connectorProvider(HttpClientConnector::new))
```
If you want to customise the Java HTTP client you are using, you can use the following.
```java
var httpClient = HttpClient.newHttpClient();
var Client = ClientBuilder.newClient(
                            new ClientConfig()
                              .connectorProvider(
                                 (jaxRsClient, config) ->  new HttpClientConnector(httpClient)))
```

Inspired from Stackoverflow question without answer [Support HTTP/1.1 and HTTP/2 with a JAX-RS client](https://stackoverflow.com/questions/42348041/support-http-1-1-and-http-2-with-a-jax-rs-client).



[![Build Status](https://travis-ci.com/nhenneaux/jersey-httpclient-connector.svg?branch=master)](https://travis-ci.com/nhenneaux/jersey-httpclient-connector)
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/com.github.nhenneaux.jersey.connector.httpclient/jersey-httpclient-connector/badge.svg)](https://maven-badges.herokuapp.com/maven-central/com.github.nhenneaux.jersey.connector.httpclient/jersey-httpclient-connector)
[![Quality Gate Status](https://sonarcloud.io/api/project_badges/measure?project=nhenneaux_jersey-httpclient-connector&metric=alert_status)](https://sonarcloud.io/dashboard?id=nhenneaux_jersey-httpclient-connector)
[![Coverage](https://sonarcloud.io/api/project_badges/measure?project=nhenneaux_jersey-httpclient-connector&metric=coverage)](https://sonarcloud.io/dashboard?id=nhenneaux_jersey-httpclient-connector)
