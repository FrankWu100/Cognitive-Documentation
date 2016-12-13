<!-- 
NavPath: Computer Vision API
LinkLabel: CV-FAQ
Url: Computer-Vision-API/CV-FAQ.md
Weight: ???
-->

# Computer Vision API Frequently Asked Questions

### Question: 
The Computer Vision API offers at least two ways of obtaining tags for an image. According to the documentation there's a list of tags for "description", as well as a top level "tags" list. The "tags" list additionally contains confidence-levels, the "description tags" list does not. However, the description tag list seems to be much more exhaustive than the top level tags list, usually showing 5 to 10 times as many tags. Why are there two different lists of tags and what's the use case for each list? Also, is there a reason why the description-tags list shows way more tags than the top-level tags list? 
### Answer:
Although the list is similar today, there is no guarantee for now or for the future that these lists remain this way. The idea for the tags inside the description was to give API users an option to construct a sentence of their liking using these tags if the confidence for the natural-language sentence was low.

**Note:** In both the tags and description.tags cases, the terms are in descending confidence order.
