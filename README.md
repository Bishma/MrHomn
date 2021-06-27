# MrHomn

MrHomn is the 3rd generation of my home automation setup<sup>*</sup>. This started because I wanted a project to help me learn docker compose. This could be accomplished using a HASSOS setup, but then I wouldn't be learning docker.

## Stack Elements

### hass

Home Assistant is the brain of the setup. It provides the UI's, device integrations, data recording, state tracking, events, and more.

### sql_db

I've gone with MariaDB for now. Home Assistant makes use of [SQLAcadamy](https://www.sqlalchemy.org/) which opens up a lot of DB options. At some point I may have more specific needs but for now the versatility of MariaDB seems like a good choice.

### appdaemon

AppDaemon is a great way to incorporate loosely coupled Python apps with home assistant. Most critically this is how I'll be creating my APIs to Home Assistant.

### nginx

Initially, at least, I'm going to need a public API to support my Alexa skill. Nginx is how I'll handing internal and external routing within my stack.

## Near Future Goals

#### Monitoring

I'm currently weighing [Prometheus](https://prometheus.io/) vs [Zabbix](https://www.zabbix.com/). I'd learn more implementing Prometheus but it's overkill for this project.

#### Log Management

https://hub.docker.com/r/graylog/graylog

#### RUM and Synthetics

This is running on my local network. I'm not going to have enough traffic for these to be of any use. ¯\\\_(ツ)_/¯ 

### Data Analysis

#### timeseries_db

SQL is well and good, but if you want to evaluate trends you want to be able to query for timeseries data. I am planning to use InfluxDB.

I will also make use of InfluxDB as the storage backend for Prometheus.

#### Grafana

It's a solid visualization platform that is common use. Understanding it at more than basic level will pay dividends.

### Purpose built sensors

It has been decades since I did anything with hobbyist electronics and I intend to make the time to relearn it. I intend to use ESP modules and simple sensors anywhere I can figure out how to power them. I'd like to sample the temp and humidity in each space of my house. I'd like to add CO<sub>2</sub>, Lux, dB, and in key areas. And I also want some manner particulate sensor(s) in my attic due to local wildfires. For added fun I can 3D Print each sensors' housing.

Additionally I'm planning to build an RPi based outdoor weather station.

#### ESPHome

Those purpose built sensors have to tell someone what they sense. That someone is [ESPHome](https://github.com/esphome/esphome) which I plan to deploy in the [docker](https://hub.docker.com/r/esphome/esphome) stack.

### Telegram Chatbot

My goal is to be able to duplicate a natural language interface for both voice assistants and telegram. Telegram has the extra benefit of being able to present options as buttons.

### No hardware requiring the cloud

#### Voice Assistant

#### Doorbell

### PyTorch

#### Nvidia Jetson

#### Face detection

Nothing creepy, but if MrHome recognizes a things in it's camera view as human then I can send intelligent proximity alerts. If I can get it to recognize ~~my many enemies~~ friends than I can ~~launch countermeasures~~ play harp music or something.

#### Routine Detection

This is a half-baked idea at this point, but I'd like to have MrHomn be able to do something like:

* Detect a recurring change to my day-to-day routine
* Generate a set up automation changes changes based on the change
* Send a Telegram message to suggest the change
* Implement the change if approved

E.g. "I've noticed you're going to bed later recently. Would you like me to delay your bedtime automation by 30 minutes?"

----

<sup>*</sup> <small>OK, yes, I promised, after naming my second home automation repo "[HomeAssistant TNG](https://github.com/Bishma/home-assistant-tng)," that I'd name my next one "Deep Space Nine." But [MrHomn](https://memory-alpha.fandom.com/wiki/Homn) was too good to pass up.

1. He was [Lwaxana Troy's](https://memory-alpha.fandom.com/wiki/Lwaxana_Troi) very diligent valet in Star Trek TNG
1. 3 syllable wake words tend to work best for VUIs
1. [Carel Struycken](https://en.wikipedia.org/wiki/Carel_Struycken) is awesome
1. Homn is a homonym of home</small>
