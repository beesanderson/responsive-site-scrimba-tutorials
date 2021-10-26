# 5 Page Layout Notes


## Home Page Notes of Mention---

### Article HTML Semantics: 
Its kind of "Best Practice" to list out the correct order of an article's content "decent" for those using screen readers. So even though this layout is different from our HTML markup it can still be displayed properly by using a "newer" **FlexBox** feature to move things around. 
- Example: 
```HTML
<article class="article-featured">
    <h2 class="article-title"></h2>
    <img src="" alt="" class="article-image">
    <p class="article-info"></p>
    <p class="article-body"></p>
    <a href="#" class="article-read-more"></a>
</article>
```
- So a screen reader (or if CSS doesn't load properly or at all, this HTML text would be displayed in this sequence) would read the title first then describe the image then the article info (in this case the date it was written and number of comments) then read the article description (or body) and finally read the link to "read more" 


### Container Tips: 
A nice little tip is to just use "reusable" or standardized/general container classes so you can keep things simple and straightforward for yourself. In the case of this project we can easily reuse the `.container-nav` from the `<nav>` bar for the `.flex-container` we are going to create and use for the `<main>` article section and the `<aside>` section. This is because they both will be using the same simplistic parent element layout 

```html
.container-nav {
    display: flex;
    justify-content: space-between;
}
```
can be renamed and applied to all three major sections like so: 
```HTML
.flex-container {
    display: flex;
    justify-content: space-between;
}
```