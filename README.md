# Werkstudent:in Shop-Entwicklung 

## Aufgabe  1 📑 / Task 1

Create 2 buttons to be able to click in a blog article to the next and to the previous blog article. (using HTML5 and Shopify Liquid)

Please send us the code you would use.

## Usage
### Step 1: 
Adding code to `main-article.liquid` in the `Sections` directory. 

```twig
  <!--   Blog next and previous button starts -->
  {% if blog.next_article or blog.previous_article %}
      <hr>
      <div class="article-template__back element-margin-top center">
          {% if blog.previous_article %}
            <a href="{{ blog.previous_article }}" class="article-navigation_link link animate-arrow">
              <span class="icon-wrap-left">{% render 'icon-arrow' %}</span>
              {{ 'blogs.article.older_post' | t  }}: {{blog.previous_article.title}}
            </a>
          {% endif %}
          {% if blog.next_article %}
            <a href="{{ blog.next_article }}" class="article-navigation_link link animate-arrow">
              {{ 'blogs.article.newer_post' | t }}: {{blog.next_article.title}}
              <span class="icon-wrap">{% render 'icon-arrow' %}</span>
            </a>
          {% endif %}
        </div>
  {% endif %}
  <!--   Blog next and previous button end  -->
```
### Step 2:
Adding code to `
section-blog-post.css` in the `Assets` directory. 

```css
.article-navigation_link {
  font-size: 1.8rem;
  display: flex;
  justify-content: center;
  align-items: center;
  text-decoration: none;
}

.article-navigation_link .icon-wrap-left {
  display: flex;
  margin-right: 1rem;
  transform: rotate(180deg);
}
.article-navigation_link .icon-wrap {
  display: flex;
  margin-left: 1rem;
}

```
### Step 3:
Adding object value for languages in the `Locales` directory. 

```json
      "newer_post": "Next",
      "older_post": "Previous",
```
these values inside `blog` object


