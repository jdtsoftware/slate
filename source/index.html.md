---
title: API Reference

language_tabs:
  - shell
  - php

toc_footers:
  - <a href='mailto:support@thejobspace.com'>Support Email</a>
  - <a href='mailto:api@thejobspace.com'>Request Developer Key</a>

includes:
  - authentication/authentication
  - authentication/password
  - authentication/refresh
  - authentication/basic_auth
  - job/readall
  - job/read
  - job/create
  - job/update
  - job/delete
  - lookups/options
  - errors  

search: true
---

# Introduction

Welcome to The Job Space API! 

The Job Space is a SaaS based job board and this documentation can be used for any job board powered by The Job Space.

<aside class="notice">
To access this api you will need the following:
<ul>
    <li>client_id</li>
    <li>client_secret</li>
    <li>base_url</li>
</ul>
</aside>

## Supply data to all requests
You will need to supply the following headers to all requests.

### Headers

Parameter | Value | Description
--------- | ------- | -----------
Accept | application/vnd.jb.v1+json | Your api client secret. 