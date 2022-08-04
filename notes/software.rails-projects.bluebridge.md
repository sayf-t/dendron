---
id: agu9f2czwtburirt5k6puee
title: Bluebridge
desc: ''
updated: 1659601483271
created: 1659578148518
---

## BB Estimator 

### Setting up
Fork/Clone repo from `https://github.com/wongwf82/project1`

Run command to seed list
```shell
rake import:variant_and_spec
```

Run server with 
```shell
./bin/dev
```


### Fixes

**Issue**: Getting UJS to load with Rails7  
**Solution**: https://stackoverflow.com/questions/70767231/rails-ujs-not-firing-with-rails-7
- To add rails-ujs to Rails 7 you should to do following steps:

- Pin it, to let the application know, which package to use. Enter in bash:
```bash
./bin/importmap pin @rails/ujs
```

And now you have in your config/importmap.rb file something like this:
```rb
pin "@rails/ujs", to: "https://ga.jspm.io/npm:@rails/ujs@7.0.1/lib/assets/compiled/rails-ujs.js"
```
Now include `@rails/ujs` to your javascript. In file javascript/controllers/application.js add:
```js
import Rails from '@rails/ujs';

Rails.start();
```
Restart your application server


### Questions

- How does the data generation work for `lib/tasks/import.rake`?
- In the models, how does the `is_valid?` function work, with the `DISALLOWED_NAMES` array