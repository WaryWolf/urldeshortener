# urldeshortener

# Description

urldeshortener is a system for de-shortening short urls, i.e. bit.ly, t.co, tinyurl links, as well as a database that stores information about these short urls. It provides an API inside AWS using lambda, API gateway and DynamoDB. There are also a collection of clients to harvest large amounts of short urls and populate the database with them. In the future there will be a website frontend to view statistics for the database and to submit urls you would like to de-shorten.

My aim in creating this project was to preserve and catalogue all url shortening services' links, in the event that any of them are shut down or forced to close. The closure of a url shortening service could pose a problem when viewing old forum posts, internet articles, etc. 

In the future I may offer copies of the database for distribution or archive by other parties. Let's get up and running first :)

This project follows in the footsteps of [archive.org] and [301works] - see [this article] for more info.

# TODO:
- tinyurl client:
  - use tornado for grabbing all of these urls
  - need to check if tornado can do HTTP HEAD and has proxy support... hmm
  - investigate proxy grabbing library - 
  - tinyurl have their own 404 detection and send you to an interstitial, make sure you handle those, we just want the end url
- lambda/dynamodb bridge:
    - look into batch submissions, we'll need it (INPROGRESS)
    - separate API call functions from dynamodb functions so we can reuse code
    - create API request to do url lookup inside lambda - for use on website
- website/frontend:
    - look into some kind of minimal javascript library to handle ajax calls, data binding, etc. modern equivalent of jquery?
    - function first, pretty later!



[this article]: <http://boingboing.net/2009/11/13/url-shorteners-suck.html>
[301works]: <https://archive.org/details/301works-faq>
[archive.org]: <https://archive.org>
