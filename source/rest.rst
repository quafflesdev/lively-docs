Calendar API
============

.. http:post:: /lively-calendar
    :noindex:

Creates a lively calendar workspace

Request Body:

.. sourcecode:: json

    {
        "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoiU2h5YW0gU3dhcm9vcCIsInVzZXJJRCI6IjYwODI5ZmYwMTU3ODI4N2I0ZTY2OGI4NyIsImlhdCI6MTYyMTQwMTgzMH0.EzUGoj3GLIqmkMJ7iErntk4Zbk6vdwTOvUJdUmxb9Q4",
        "name": "course w4118",
        "description": "operating systems class spring 2021"
    }

Sample Response

.. sourcecode:: json

    {
        "success": true,
        "resp": {
            "body": {
                "_index": "calendars",
                "_type": "_doc",
                "_id": "MDxynHkBXyLJnEnV0Ee6",
                "_version": 1,
                "result": "created",
                "_shards": {
                    "total": 2,
                    "successful": 1,
                    "failed": 0
                },
                "_seq_no": 9,
                "_primary_term": 1
            },
            "statusCode": 201,
            "headers": {
                "location": "/calendars/_doc/MDxynHkBXyLJnEnV0Ee6",
                "content-type": "application/json; charset=UTF-8",
                "content-length": "176"
            },
            "meta": {
                "context": null,
                "request": {
                    "params": {
                        "method": "POST",
                        "path": "/calendars/_doc",
                        "body": "{\"name\":\"course w4118\",\"description\":\"operating systems class spring 2021\",\"organizerID\":\"60829ff01578287b4e668b87\",\"organizerName\":\"Shyam Swaroop\"}",
                        "querystring": "",
                        "headers": {
                            "user-agent": "elasticsearch-js/7.12.0 (darwin 19.6.0-x64; Node.js v14.16.1)",
                            "x-elastic-client-meta": "es=7.12.0,js=14.16.1,t=7.12.0,hc=14.16.1",
                            "content-type": "application/json",
                            "content-length": "148"
                        },
                        "timeout": 30000
                    },
                    "options": {},
                    "id": 1
                },
                "name": "elasticsearch-js",
                "connection": {
                    "url": "http://quaffles.com:9200/",
                    "id": "http://quaffles.com:9200/",
                    "headers": {},
                    "deadCount": 0,
                    "resurrectTimeout": 0,
                    "_openRequests": 0,
                    "status": "alive",
                    "roles": {
                        "master": true,
                        "data": true,
                        "ingest": true,
                        "ml": false
                    }
                },
                "attempts": 0,
                "aborted": false
            }
        }
    }

.. http:get:: /lively-calendar?query&from&size

Get all calendars

.. sourcecode:: json

    {
        "success": true,
        "resp": {
            "body": {
                "took": 0,
                "timed_out": false,
                "_shards": {
                    "total": 1,
                    "successful": 1,
                    "skipped": 0,
                    "failed": 0
                },
                "hits": {
                    "total": {
                        "value": 2,
                        "relation": "eq"
                    },
                    "max_score": 1,
                    "hits": [
                        {
                            "_index": "calendars",
                            "_type": "_doc",
                            "_id": "LzybiXkBXyLJnEnVvUc5",
                            "_score": 1,
                            "_source": {
                                "name": "course w4118",
                                "description": "operating systems class spring 2021",
                                "organizerID": "60829ff01578287b4e668b87",
                                "organizerName": "Shyam Swaroop",
                                "usersJoined": [
                                    {
                                        "name": "Shyam Swaroop",
                                        "userID": "60a0e49523d6b211f778d2b2"
                                    }
                                ]
                            }
                        },
                        {
                            "_index": "calendars",
                            "_type": "_doc",
                            "_id": "MDxynHkBXyLJnEnV0Ee6",
                            "_score": 1,
                            "_source": {
                                "name": "course w4118",
                                "description": "operating systems class spring 2021",
                                "organizerID": "60829ff01578287b4e668b87",
                                "organizerName": "Shyam Swaroop"
                            }
                        }
                    ]
                }
            },
            "statusCode": 200,
            "headers": {
                "content-type": "application/json; charset=UTF-8",
                "content-length": "713"
            },
            "meta": {
                "context": null,
                "request": {
                    "params": {
                        "method": "POST",
                        "path": "/calendars/_search",
                        "body": "{\"query\":{\"match_all\":{}}}",
                        "querystring": "from=0&size=40",
                        "headers": {
                            "user-agent": "elasticsearch-js/7.12.0 (darwin 19.6.0-x64; Node.js v14.16.1)",
                            "x-elastic-client-meta": "es=7.12.0,js=14.16.1,t=7.12.0,hc=14.16.1",
                            "content-type": "application/json",
                            "content-length": "26"
                        },
                        "timeout": 30000
                    },
                    "options": {},
                    "id": 2
                },
                "name": "elasticsearch-js",
                "connection": {
                    "url": "http://quaffles.com:9200/",
                    "id": "http://quaffles.com:9200/",
                    "headers": {},
                    "deadCount": 0,
                    "resurrectTimeout": 0,
                    "_openRequests": 0,
                    "status": "alive",
                    "roles": {
                        "master": true,
                        "data": true,
                        "ingest": true,
                        "ml": false
                    }
                },
                "attempts": 0,
                "aborted": false
            }
        }
    }

.. http:get:: /lively-calendar?query=columbia&from&size

    :query string: query -- the search text
    :query number: from -- result start index
    :query number: size -- number of results to fetch

Sample Response

.. sourcecode:: json

    {
        "success": true,
        "resp": {
            "body": {
                "took": 0,
                "timed_out": false,
                "_shards": {
                    "total": 1,
                    "successful": 1,
                    "skipped": 0,
                    "failed": 0
                },
                "hits": {
                    "total": {
                        "value": 0,
                        "relation": "eq"
                    },
                    "max_score": null,
                    "hits": []
                }
            },
            "statusCode": 200,
            "headers": {
                "content-type": "application/json; charset=UTF-8",
                "content-length": "160"
            },
            "meta": {
                "context": null,
                "request": {
                    "params": {
                        "method": "POST",
                        "path": "/calendars/_search",
                        "body": "{\"query\":{\"query_string\":{\"query\":\"columbia\",\"fields\":[\"name\",\"description\"]}}}",
                        "querystring": "from=0&size=40",
                        "headers": {
                            "user-agent": "elasticsearch-js/7.12.0 (darwin 19.6.0-x64; Node.js v14.16.1)",
                            "x-elastic-client-meta": "es=7.12.0,js=14.16.1,t=7.12.0,hc=14.16.1",
                            "content-type": "application/json",
                            "content-length": "79"
                        },
                        "timeout": 30000
                    },
                    "options": {},
                    "id": 3
                },
                "name": "elasticsearch-js",
                "connection": {
                    "url": "http://quaffles.com:9200/",
                    "id": "http://quaffles.com:9200/",
                    "headers": {},
                    "deadCount": 0,
                    "resurrectTimeout": 0,
                    "_openRequests": 0,
                    "status": "alive",
                    "roles": {
                        "master": true,
                        "data": true,
                        "ingest": true,
                        "ml": false
                    }
                },
                "attempts": 0,
                "aborted": false
            }
        }
    }