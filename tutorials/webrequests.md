---
order: 10
---

Web requests are made through specific functions such as `get()`, `request()`, `post()`, etc., and the Python Requests module gives access to these functions. API keys are used to verify the program or application making the API call. There are different types of APIs, such as Web APIs or Web Service APIs, and REST API is a special type of Web API. There are different packages for making web requests, but `requests` is the most widely used.

To make a `GET` request using Python Requests, you can use the `get()` method with the website's URL passed in. You can also print other attributes related to the response such as the status code. To limit the data returned by the request, you can add a query parameter in the request using a Python dictionary with the desired parameter as the key and the desired value as the value, and pass it to the `get()` method using the `params` parameter. The response will be returned in JSON format, which can be easily read using the `.json()` method. 

Roadblocks you can run into are headers, coockies or api keys that are needed to get access to a page.

```py
import requests

headers={'User-agent': 'Mozilla/5.0 (compatible; Discordbot/2.0; +https://discordapp.com)'}
response = requests.get(https://URL_HERE)
json = response.json()
status = response.status_code
# ...

```