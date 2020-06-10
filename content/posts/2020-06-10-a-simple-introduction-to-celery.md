---
title: A Simple Introduction to Celery
publishdate: 2020-06-10T19:16:03.525Z
tags:
  - python
  - automation
draft: true
---
If you're a Python developer, you have probably at least heard of a library called Celery. Its designed to make asynchronously scheduling a variety of different kinds of tasks easy via the advanced messaging queue protocol, or AMQP. While the potential for the different kinds of tasks one can automate with Celery are almost

![celery](https://cdn.mos.cms.futurecdn.net/M7e7tKGmULBz9tPT93U4GP-650-80.jpg)
<br>
*Healthy and delicious task scheduling*

## Installation and Setup

Before we install Celery, we first need to install and setup and AMPQ server. For Celery, the preferential option is RabbitMQ. 