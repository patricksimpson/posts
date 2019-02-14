---
title: "Goodbye, Google Analytics"
date: "2019-02-13 10:40 PM"
summary: "Removed Google Analytics; added gzip for performance gains!"
tags: ["blog", "programming", "performance"]
---

Today, I've parted ways with Google Analytics (GA) 👋.

## CloudFront Analytics

For now, I will simply use [CloudFront's analytics](https://aws.amazon.com/cloudfront/reporting/). This is nice because it
tracks even non-HTML requests (like rss.xml, and robots.txt).
![](https://i.postimg.cc/sXttCQKb/cloud-front-analytics.png)

CloudFront also gives you additional information, misses, requests from cache, etc. This far exceeds the abilities of GA.

Lastly, CloudFront analytics are not blocked by [Brave or other content/source blockers](https://www.quantable.com/analytics/how-many-users-block-google-analytics/)
like GA. This is a huge win for me, and for you!

## Gzipping; Page Speed

After removing GA and adding the gzip step to my [deployment script](https://github.com/patricksimpson/blog/blob/master/deploy.js), I ran some performance tests.

### Results:

- Dropped "visually complete" load time by 0.2 seconds!
- Total size from 69KB to 7KB, 62KB reduction (wow, gzip).
- Dropped "fully loaded time" from 0.930 seconds to 0.435 seconds!

Impressed? 😏

### Speed Test Screen Shots

Before removing GA and adding gzip:

![](https://i.postimg.cc/nzBHXtJv/before-with-GA.png)

After removing GA and adding gzipping:

![](https://i.postimg.cc/52XWHM56/after-without-GA.png)
