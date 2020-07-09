<!-- [![Actions Status](https://github.com/msantino/publish-event-sns/workflows/CI/badge.svg)](https://github.com/msantino/publish-event-sns/actions) -->
[![Python 3.7](https://img.shields.io/badge/python-3.7-blue.svg)](https://www.python.org/downloads/release/python-370/)
[![PyPI version](https://badge.fury.io/py/publish-event-sns.svg)](https://badge.fury.io/py/publish-event-sns)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
<!-- [![Language grade: Python](https://img.shields.io/lgtm/grade/python/g/msantino/publish-event-sns.svg?logo=lgtm&logoWidth=18)](https://lgtm.com/projects/g/msantino/publish-event-sns/context:python) -->
[![Twitter Follow](https://img.shields.io/twitter/follow/msantino.svg?style=social&label=Follow)](https://twitter.com/msantino)




# Publish Data Event to SNS Topic

This package helps you to publish a dict object as JSON into SNS Topic, including fields as attributes

```bash
pip install publish-event-sns
```

```python
from publish_event_sns import publish


my_dict = {
    "foo": "bar"
}

response = publish("topic_name", my_dict)
```

This code will transform DICT into JSON and publish into SNS Topic with `foo` as attribute as `bar` value. 

> `publish` function will automaticaly exclude from attributes non primitive values (dict, object, etc)

## Parameters

Some aditional configuration is possible while publishing event:

* `region_name`: Region name to use in internal boto3 client;
* `session`: If you need to provide a existing boto3 session
* `attr_exclude`: A list of fields to force exclusion while including fields as attributes
