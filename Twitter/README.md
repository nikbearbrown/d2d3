# Python Twitter

A well written and easy to use Python wrapper around the Twitter API.


==========
Installing
==========

You can install python-twitter using::

    $ pip install python-twitter


==========
Tutorials
==========

    * 1_python-twitter_quick_start.ipynb  
	   This should be the first notebook if unfamilar with the python-twitter library.
	   
	   
------
Models
------


*python-twitter* is one of the many libraries that make it easy to query Twitter data.  

Twitter has provided `REST API's ` [https://dev.twitter.com/rest/public](https://dev.twitter.com/rest/public) which can be used by
developers to access and read Twitter data. They have also provided a
`Streaming API ` [https://dev.twitter.com/streaming/overview](https://dev.twitter.com/streaming/overview) which can
be used to access Twitter Data in real-time.

To use the Streaming API one needs to get an access key by applying for a Twitter developer account [https://developer.twitter.com/en/apply-for-access](https://developer.twitter.com/en/apply-for-access)  

All new developers must apply for a developer account to access the Twitter developer platform. Once approved, you can begin to use the new Twitter API v2, or the v1.1 standard and premium APIs.   

Most of the software written to access Twitter data provide a library
which functions as a wrapper around Twitter's Search and Streaming API's
and are therefore constrained by the limitations of the API's.

With Twitter's Search API you can only send 180 Requests every 15
minutes. With a maximum number of 100 tweets per Request, you
can mine 72 tweets per hour (4 x 180 x 100 =72) . By using
TwitterScraper you are not limited by this number but by your internet
speed/bandwith and the number of instances of TwitterScraper you are
willing to start.

One of the bigger disadvantages of the Search API is that you can only access Tweets written in the **past 7 days**. This is a major bottleneck for anyone looking for older data. With TwitterScraper there is no such limitation.

The library utilizes models to represent various data structures returned by Twitter. Those models are:
    * twitter.Category   
    * twitter.DirectMessage   
    * twitter.Hashtag   
    * twitter.List   
    * twitter.Media   
    * twitter.Status   
    * twitter.Trend   
    * twitter.Url   
    * twitter.User   
    * twitter.UserStatus   
    

To read the documentation for any of these models, run::

    $ pydoc twitter.[model]

---
API
---

The API is exposed via the ``twitter.Api`` class.





For full details see the `Twitter OAuth Overview <https://dev.twitter.com/oauth/overview>`_

To create an instance of the ``twitter.Api`` with login credentials (Twitter now requires an OAuth Access Token for all API calls)::

```python

    >>> import twitter
    >>> api = twitter.Api(consumer_key='consumer_key',
                          consumer_secret='consumer_secret',
                          access_token_key='access_token',
                          access_token_secret='access_token_secret')
                          
                          
```


To see if your credentials are successful::


```python
    >>> print(api.VerifyCredentials())
    {"id": 16133, "location": "Boston", "name": "bear"}
    
```    


There are many more API methods, Read the full API documentation either
check out the documentation on [https://python-twitter.readthedocs.io](https://python-twitter.readthedocs.io)  


build the documentation locally with:  

```bash
    $ make docs
```    

or check out the inline documentation with:  

```bash

    $ pydoc twitter.Api

```  




