---
title: Project Charter
layout: default
---

## Project Charter
This cloud-based Fieldwork System is a proof of concept for KUB to develop mobile and dispatch applications. These will be implemented in Ember JS using Firebase hosting for data, photos, static web pages, database, and security. We are using GitHub for source control, Heroku for hosting as well as NodeJS applications.

### System Architecture
* Fieldwork-manager
  * Hosted on Heroku for testing purposes - It loads the Firebase database. It will not be used in final production.
* Fieldwork-dispatcher
  * Sees jobs as they are loaded into the Firebase database
  * Sees which workers are available
* Fieldwork-worker
  * Sees assignments as filtered for that worker -
  * job status: acknowledged, enroute, arrived, completed sent to the database where it displays on all authorized screens

![GitHub](./images/system-architecture.jpg)

                          Diagram by Amber Rivera
