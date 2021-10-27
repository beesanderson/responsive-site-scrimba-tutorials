# 5 Page Layout Notes
Various notes of varying degree of importance for quick reference. 

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
```CSS
.container-nav {
    display: flex;
    justify-content: space-between;
}
```
can be renamed and applied to all three major sections like so: 
```CSS
.flex-container {
    display: flex;
    justify-content: space-between;
}
```

### Mobile First Approach
Make you page for "smaller screens" **FIRST** as it will make refactoring a whole lot easier. This is also kind of the standard because of that.

When you start with the "big screen" (or desktop version) first when you're ready to add in your mobile layouts you're basically going to be resetting everything to the default layouts. Basically you'd be doing everything backwards for no reason. Just start out with mobile then refactor/@media for larger screens. Basically just reverse everything. 
```CSS
.container-flex {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
}

header {
    background: #f8f8f8;
    padding: 2em 0;
    text-align: center;
}

@media (min-width: 675px) {
    .container-flex {
        flex-direction: row;
    }
    
    main {
        width: 75%;
    }
    
    aside: {
        width: 20%;
    }
}
```
instead of: 
```CSS
@media (max-width: 675px) {
    .container-flex {
        flex-direction: column;
    }
    
    header {
        text-align: center;
    }
}

main {
    width: 75%;
}

aside {
    width: 20%;
}
```
Small screens are much more simple. You'll only have to refactor once. Now you've got two columns again and nav-bar works properly. Only problem is spacing. Once again, *mobile first*. 

### How to change the visual layout with *FlexBox*
![first sub-article](five-page-layout-howtos/images/change-visual-layout-flexbox.png)


### Object-Fit for Images
```CSS
    .article-image {
        width: 100%;
        height: 400px;
        object-fit: cover;
    }
```

will make it look silly and sometimes can make it mess up its alignment in the sense it'll corp the image at an awkward location sometimes in which case just do:
```CSS
    .article-image {
        width: 100%;
        height: 400px;
        object-fit: cover;
        object-position: left;
    }
```
A good standard size is: 
```CSS
    .article-image {
        width: 100%;
        min-height: 250px;
        object-fit: cover;
    }
```

#### Use `min-height: ____;` more then regular height obviously 

### :last-child Pseudo Class Usage
Just like :hover or :focus its a pseudo class that allows you to target a specific element in this case the last child of the parent element. 
```CSS
.widget-recent-post:last-child {
    border: 0;
    margin: 0;
}
```
I was trying to get around this by adding a separate modifier class to the last of the `.article-recent` class in the `<main>` section but now I'm realizing I can change this
```HTML
<div class="article-recent-secondary">
    <img src="/five-page-layout-howtos/images/deco.jpg" alt="" class="article-image img-position">
    <p class="article-info">July 3, 2019 | 3 comments</p>
</div>
</article>
```
Which I modified the crop of within the @media query with the CSS of: 
```CSS
.img-position {
    object-position: left;
}
```
To this: 
```CSS

```
Okay wait never mind didn't work lol. Ignore me.