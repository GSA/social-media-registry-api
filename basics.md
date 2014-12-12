---
layout: default
title: API Basics
nav: basics
---

### API basics

The interface described here uses the same method URLs and parameters for all response formats, including HTML5, JSON, and XML. If no response format is specified at request time, the results are returned as HTML5 (with the assumption that a user is accessing the API via a web browser). To specify alternate formats, append the result format to the method call:

* [http://registry.usa.gov/accounts?agency_id=usda](http://registry.usa.gov/accounts?agency_id=usda)
* [http://registry.usa.gov/accounts.json?agency_id=usda](http://registry.usa.gov/accounts.json?agency_id=usda)
* [http://registry.usa.gov/accounts.xml?agency_id=usda](http://registry.usa.gov/accounts.xml?agency_id=usda)

API requests can be called from remote sites via Javascript using the Cross-Origin Resource Sharing mechanism (CORS) supported in most browsers. All published API methods may be called from any domain.

If support for older browsers is required, JSON requests can be made with a callback parameter in order to return 

JSONP responses:

* [http://registry.usa.gov/accounts.json?agency_id=usda&callback=listaccounts](http://registry.usa.gov/accounts.json?agency_id=usda&callback=listaccounts)

### API Updates Using Feeds

Some API methods are also available as feeds in the ATOM format. These feeds can be added to any news feed reader to list recent changes.

The ATOM format is an XML feed standard; each entry contains a summary of the Registry change and a link to the Registry API to view more information.

### Feed Examples

List the most recently updated official Twitter accounts: [http://registry.usa.gov/accounts.atom?service_id=twitter](http://registry.usa.gov/accounts.atom?service_id=twitter)

List the most recently updated official accounts from the U.S. Department of Agriculture: [http://registry.usa.gov/accounts.atom?agency_id=usda](http://registry.usa.gov/accounts.atom?agency_id=usda)
