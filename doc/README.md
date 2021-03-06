# Overview

Sick of configuring every plugin separately, inconsistent naming and one plugin not knowing what the other does. Here comes the solution. One app config file for all your plugin. It works as follows:
At aurelia configuration you tell aurelia-config which plugin defaults it should load and the app config objects you want to merge into that sequentially. Then it (optionally) calls sequentially the plugin configurations on them with the (plugin namepsaced) merged settings. 
The merged settings (as an instance of [homefront](https://www.npmjs.com/package/homefront)) can be easily accessed from everywhere in your app or your plugins. The usage of aliass per plugins and a Configuration resolver even simplifies that.

- One config to rule them all
- Automatically load and merge plugin and app configs
- Namespaces and a Configuration resolver allow easier access of selected config segments
- All [homefront](https://www.npmjs.com/package/homefront) methods are available on the config instance.

## Used By

This library is used by plugins and applications.

## Uses

- [homefront](https://www.npmjs.com/package/homefront).

## Quick Homefront api overview

Since aurelia-configs Config class extends [homefront](https://www.npmjs.com/package/homefront), all of homefront's methods are available on the Config instance or a segments of it (when made with config.use('alias')). Some of the methods homefronts gives you are:

```js
  // contains the data in a single object
  .data            
  // recursively merges given sources into data.          
  .merge(sources)  
  // Fetches value of given key.
  .fetch(key, defaultValue)    
  //Convenience method. Calls .fetch(), and on null result calls .put() using provided toPut.
  .fetchOrPut(key, toPut)
  // Sets value for a key (creates object in path when not found).
  .put(key, value)    
  // Removes value by key.
  .remove(key)   
  // Search and return keys and values that match given string.
  .search(phrase)
```

Keys can be dot separated strings or an array of keys
