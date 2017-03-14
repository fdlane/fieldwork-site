---
title: System Architecture
layout: default
---

## System Architecture

#### Fieldwork-manager is hosted on Heroku for testing purposes. It loads the Firebase database right now.
#### Fieldwork-dispatcher sees any changes to the Firebase database including which workers are available. This is similar to the flow shown by the lines.
#### Fieldwork-worker recieves assignments, filter for that worker, from the dispatcher. As work is completed, the worker sends the change of status to the database and the dispatcher sees this immediately.

![GitHub](./images/system-architecture.jpg)


                          Diagram by Amber Rivera
