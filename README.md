Crossing
========

Crossing is JavaScript URL utility library that aims to help you manage and generate dynamic urls.

[![browser support](https://ci.testling.com/lincolnloop/crossing.png)
](https://ci.testling.com/lincolnloop/crossing)

### Install

  ```npm install crossing```


### Basic Use


```javascript

  var Crossing = require('crossing');

  // create your crossing instance
  var urls = new Crossing();

  // load your url list
  urls.load({
    'team:detail': '/teams/<slug>/',
    'discussion:detail': '/<team_slug>/<discussion_id>/<slug>/',
    'search': '/search/'
  });

  // get a url
  var path = urls.get('team:detail', {'slug': 'lincolnloop'}); // -> /teams/lincolnloop/

  // resolve a path to get the url name and attrs
  var urlName = urls.resolve('/loop/23/discussion-name/'); // -> {'name': 'discussion:detail', 'kwargs': {'team_slug': 'loop', 'discussion_id': 23, 'slug': 'discussion-name'}}

```

That's all there is to it! Enjoy!

### Run Tests

    npm test
