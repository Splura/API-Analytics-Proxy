**API Analytics Proxy**
===================

### Background

Given the growing popularity during the last years of the *API-first* and *API-only* WEB architectures ([API-first.com](http://www.api-first.com/)) that clearly splits server-side from client-side and the subsequent arise of the API Managers as the perfect partners to publish and manage your public or semi-public API, API-based analytics had become a relevant topic not enough addressed when it comes to dive into the contents an API is delivering.
API Managers such as **3scale**, **Mashery**, **Apigee** or opensourced ones like **Tyk** deliver very basic just-technical-level statistics that allows to know how fast is the API responding and which are most popular endpoints/requests but they will never dive into the content data the API is exchanging which contains a lot of business-relevant data that can "easily" be crawled, stored and analyzed.
There are a certain number of *SaaS* business intelligence software solutions that normally consist on collecting relevant *KPIs* from third-parties systems and generate analytics based on a predefined logic: This is frequently e-commerce related such as sale funnels, shopping conversion rates, etc... This approach has a huge impact in the consumer application software development cycle since this KPI's need to be implemented in the application software itself, adding a lot of extra complexity to the usual software development cycle. This is why we want to opt for a fully unobtrusive solution based on an *API Proxy*, very similarly to how popular *API Managers* work.

> We want to write an open-source software system that easily allows to proxy an API and then extract, and store relevant data out of it for further data analysis.

### Target audience

The target group user will be high proficient technical users, normally software developers, dev-ops or system administrators who are running and API and need an unobtrusive (from the business application software point of view) solution to do analytics on an API.
This approach will require no implementation (neither in Backend nor Frontend) on the already existing consumer's software. This makes integration a seamless, fast, and architecturally clean integration process.
Consumers will only require to configure the proxy in order to track and store the appropriate "crawls" in the *data lake*.

> **API Analytics Proxy** will be intended for any API architects, developers or product managers who want to implement a data-analytics solution without impacting on the software development processes of the project.


### Solution

We want to build a transparent proxy that forwards requests and responses "as-it-is" meant with no relevant change at data-transportation level.
Once APIs are proxied the analytics module *crawls* both requests and responses and takes user-defined data to be stored in a *data lake* where this data can be post-processed, analyzed or just displayed for any kind of purpose.

The crawler will be configurable through specific DSL (and optionally through WEB interface). Crawls consist in collected data or data structures (Collections or Maps) dumped into key-value stores.
Crawler works concurrently with the proxy in a non-blocking way, so that it adds no extra latency to proxied requests.
Crawler stores measures in the data lake as-it-happens, this means it can be processed or displayed nearly in real-time.

The resulting outcome of **API Analytics Proxy** will be custom structured data stored in a statistical key-value DB engine like *InfluxDB* or *GraphiteDB*.
This engines are designed to be used as data-analytics oriented database engines. There are a number of well-known projects focused on data treatment and visualization using this engines as data sources, like *[Grafana](http://grafana.org/)*, which opens a lot of possibilities to integrate crawled data with final-user applications at a very low development cost.


----------
### Conclusions

> An open-source **API Analytics Proxy** habilitates software and
systems engineers to proxy, track, and deep-analyze every single chunk
of data that is either queried or delivered on their APIs.
 
> An open-source **API Analytics Proxy** is a great complement for the popular API Managers, enabling API owners to know much more about what's happening in their API stream.

> An open-source **API Analytics Proxy** is a long-term solid data-analytics (and business intelligence) strategy given the increasing popularity of *API-first* and *API-only* strategies as a WEB architecture.
