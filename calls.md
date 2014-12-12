---
layout: default
title: API Calls
nav: calls
---

## /accounts (GET)

List official U.S. government social media accounts entries in the registry. This method is also available as an ATOM feed.

### Parameters

* agency_id: ID (from /agencies)
* service_id: ID (from /services)
* tag: text
* page_size: integer
* page_number: integer

### Output

* page_count: integer
* page_number: integer
* total_items: integer

Accounts
* service_url: text
* verified : boolean
* service_id: ID
* account: text
* details_url: text
* organization: text
* agencies
  * agency_id: text
  * agency_name: text
  * agency_url: text

Example Calls

List all official accounts from the U.S. Department of Agriculture: [http://registry.usa.gov/accounts?agency_id=usda](http://registry.usa.gov/accounts?agency_id=usda)  
List all official Twitter accounts from the U.S. Department of Health and Human Services:
[http://registry.usa.gov/accounts?service=twitter&agency_id=hhs](http://registry.usa.gov/accounts?service=twitter&agency_id=hhs)

## /accounts/{service ID} (GET)

A synonym for /accounts?service_id={service}, provided for REST-style browsing.

## /accounts/{service ID}/{account} (GET)

A synonym for the /accounts/verify method, using a canonical service and account ID provided by that method. For example, the service and account ID for http://twitter.com/JPL_Bear might be twitter/JPL_Bear, making the canonical URL take the form http://registry.usa.gov/accounts/twitter/JPL_Bear

This is provided primarily for REST-style browsing.

## /accounts/verify (GET)

Check whether the provided URL is registered as an official government social media account.
Example: /accounts/verify?service_url=https%3A%2F%2Ftwitter.com%2F%23%21%2FJPL_Bear

### Parameters

service_url: URL (required)

### Output

* verified: boolean
* service_url: URL
* service_id: ID (from /services list)
* account: text
  
(if verified is true:)  
* details_url: URL
* organization: text
* info_url: text
* agencies
  * agency_id: text
  * agency_name: text
  * agency_url: text
* tags: list
* language: text
* display_name: text
* updated_by: text
* updated_at: ISO 8601 date

## /agencies (GET) 

List the sponsoring agencies that may be specified in the /accounts/add method.

### Parameters

* none

### Output

* page_count: integer
* total_items: integer
* page_number: integer
* agencies: list
* agency_id: text
* agency_name: text
* agency_url: text

## /services (GET)

List the social media services that are currently supported in the /accounts/add method.

### Parameters

* none

### Output

* page_count: integer
* total_items: integer
* page_number: integer
* services: list
* service_id: text
* service_name: text

## /tags (GET) 

List tags that are suggested for describing an account.

### Parameters

* keywords: text

### Output

* tags: list
* tag_id: text
* tag_text: text
