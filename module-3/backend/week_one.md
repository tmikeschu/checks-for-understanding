## Week One - Module 3 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON!). 

Note: When you're done, submit a PR. 

1. What is `json` and why is it important?

  * java(s)cript object notation
  * It is important because it serves as a standardized format for programs to interact with other programs. Many languages have some type of key: value pair data structure, and JSON allows data to be transmitted universally, and parsed for specific languages with JSON libraries. 
  * Also key, it is both human and machine read-able.

2. What's the difference between `joins` and `includes` in ActiveRecord?
  
  * .includes 'eagerly loads' the joined table attributes, so any following queries on the joined table will not require a full db query. It's kind of like a cache. In a joins table, further queries on the joined table would require an additional db query (the n + 1 problem).
  
3. What's an API?

  * Application program interface : apps provide these to allow other apps to consume valuable information. 
  
4. How do we test an internal API (in general)?

  * We use request specs, which test to make sure the request returns a successful HTTP response, and the page renders the data in json format.
  
5. What are two different ways to customize your `json`?

  * Serializers and jBuilder
