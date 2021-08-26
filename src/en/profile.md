# Yuma Kitamura - Web Developer

Production started in Feb 2020, published in Mar 2020

![](https://i.imgur.com/sN5nHoS.jpg)

The profile page used to exist in my own [blog](blog.md). A blog was a blog site, and a profile was a clear division like a profile site. The profile `page` is twisted and twisted as a profile `site`, and it is currently operated on a different domain from the blog

## History for battle over profile

### Introduction myself

Using `webpack` at work was a lot of work, but at that time, start using [parcel](https://github.com/parcel-bundler/parcel). Create a simple profile site. However, without considering the operational aspect at all, deploy to the Production environment but set the status of this repository to `archived`. Also, it only means a project that I made for my first appearance at Kyoto dev cafe

By the way, this portal wasn't set to `archived` for a while for the purpose of tracking the trends of webpack and parcel

### Accompany the blog

The reason why I don't think about the operational aspect at all is the reason why I posted my profile on the blog. After the first appearance, I was made aware of it, and the momentum of creating a technical blog increased because I should emphasize the style of `transmitting knowledges` rather than introducing myself as an engineer

Taking advantage of this momentum, we started producing the blog that adopted Contentful for Headless CMS. Along with this, we have added a new route `/profile` as a profile page. In addition, since the information displayed here is (and preferably is) updated daily, the use of Graphcool as the API server was also served as a dynamic site

※ Graohcool was [ended](https://www.graph.cool/sunset-notice) its service in July 2020

### As a microservice

I checked every day with Google Analytics that I am allowed to put in the blog, but I did not earn access to the profile page. Also, since I sing it as a blog, I wonder if there is any reason to keep it as a profile page. However, it is still important to `transmit knowledges` rather than introduce myself as an engineer, and it is not necessary to change the blog. Therefore, I tried rebuilding it as a profile site again, and started the production by returning to a static site so far, so I tried to operate under a configuration that also included AWS as well as blog

## Technology stacks that make up the site

- normalize.css
- nekohack-ui
- Gatsby.js
- Gatsby.js PWA
- AWS S3
- AWS CLOUDFRONT
- Circle CI
- Github Actions
