# statistweepy
A (still in work) simple tool that use tweepy to collect and use Twitter data. The data structure is simple `Status` object collected using tweepy. To collect the data you must have a 'consumer key', 'consumer secret', 'access token', and 'access secret', that can be obtained by [register for a Twitter application](http://apps.twitter.com/). These will be used to access Twitter API through your Twitter account, and should be kept private. Notice also that you should *read and peruse the Twitter Developer Agreement and Policy carefully*, you may not use the data carelessly for example to do surveillance, provoke negative conflicts, etc.

Requirements :
- [Tweepy](http://docs.tweepy.org/en/v3.5.0/)
- Numpy
- Matplotlib

Author : Arief Anbiya (anbarief@live.com), written in Python 3.

## Work Cycle : (Pose the Question) - Collect Data - Analyze Data - (Interpret Results)

## Collect Data :

Here is an example of how we can collect the data : 

```
import statistweepy.collection as collection
consumer_key = '****'
consumer_secret = '****'
access_token = '****'
access_secret = '****'
init = collection.Authentication(consumer_key, consumer_secret, access_token, access_secret) 
collect = collection.Collection(Init)
```
This first creates an 'authentication' object of `Authentication`, which access the Twitter API. This object is then required as input for `Collection` class. 

Next, we would like to collect data from @NatGeo account, by the `collect_user` method,

`data = Collect.collect_user('NatGeo', n = 250) # to include RTs, use keyword 'include_rts = True'.`

which returns a tuple of 2 elements. First is the list of 'tweet' objects, and the second is the time of collection.

## Analyze Data :

Currently, there are only two models, setup in `Authors` class and `Splits` class. 
