Hubot-es-logger
===================

[![Build Status](https://img.shields.io/travis/Gandi/hubot-es-logger.svg)](https://travis-ci.org/Gandi/hubot-es-logger)
[![Dependency Status](https://gemnasium.com/Gandi/hubot-es-logger.svg)](https://gemnasium.com/Gandi/hubot-es-logger)
[![Coverage Status](http://img.shields.io/codeclimate/coverage/github/Gandi/hubot-es-logger.svg)](https://codeclimate.com/github/Gandi/hubot-es-logger/coverage)

This [Hubot](https://hubot.github.com/) plugin enables various operations related to logging:

- record all messages on configured channels to an ElasticSearch server
- enable various commands to interact and query the logs
- serve web pages to browse the logs
- announce to users joining a channel where they can find the logs web page

If you only need to log to ElasticSearch, you can rather use [hubot-elasticsearch-logger](https://github.com/robinjmurphy/hubot-elasticsearch-logger) which only does that.

For low volume channel or for testing purpose, you can use the free service of [Bonsai.io](https://bonsai.io) elasticsearch hosting.

Warning: This plugin is still in alpha stage. use with caution. It is designed to work fine with the `hubot-irc` adapter. Later on it will be tested on slack, gitter and others.

Install
-----------

In your hubot dir:

    npm install hubot-es-logger --save

Then add to your external-scripts.json

    [ 'hubot-es-logger' ]


Configuration
-------------------

You will need to set various environment variables to get the logging configured

| Variable                     | required | default   | description                                       |
|------------------------------|----------|-----------|---------------------------------------------------|
| `ES_LOG_ENABLED`             | no       | 'true'    | useful to disable logging at bot start in dev env |
| `ES_LOG_ANNOUNCE`            | no       | 'true'    | if set, will private message to people joining the channel, signaling the url where to browse the logs |
| `ES_LOG_ES_URL`              | yes      |           | the url to your Elasticsearch server              |
| `ES_LOG_ROOMS`               | yes      |           | comma-separated list of channels to log           |
| `ES_LOG_INDEX_NAME`          | no       | 'irclogs' | name of the Elasticsearch index                   |
| `ES_LOG_SINGLE_INDEX`        | no       | 'false'   | if 'true', it will use only one index, but by default, one index is created per day |
| `ES_LOG_KIBANA_URL`          | no       |           | if you have a kibana access to your irc logs, it will be displayed on the web page |
| `ES_LOG_KIBANA_TEMPLATE`     | no       |           | the template used in kibana (for building the url) |



### Contribute

Feel free to open a PR if you find any bug, typo, want to improve documentation, or think about a new feature. 

Gandi loves Free and Open Source Software. This project is used internally at Gandi but external contributions are **very welcome**. 

Attribution
-----------

### Authors

- [@mose](https://github.com/mose) - author and maintainer

### License

This source code is available under [MIT license](LICENSE).

### Copyright

Copyright (c) 2016 - Gandi - https://gandi.net
