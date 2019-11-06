# blog.template

This is a template for a [pushed.to](http://pushed.to) blog.

## Get Started

Fork this repository into your own GitHub user or organization space. When forked you can visit [pushed.to/GIT_USERNAME/GIT_REPOSITORY_NAME](http://pushed.to/GIT_USERNAME/GIT_REPOSITORY_NAME).

## .blog Reference

The `.blog` contains configurations for your blog. The template\`s `.blog`-file contains the following settings:

```json
{
  "title": "Blog Title",
  "dateFormat": "MMMM DD, YYYY",
  "postPerPage": 3,
  "description": "This is a sample blog template. You may not define any description at all. But, you can do here...",
  "topics": [
    "topic-a",
    "topic-b",
    "topic-c"
  ],
  "social": {
    "twitter": "someTwitterHandle",
    "linkedin": "https://www.linkedin.com/in/some-name-0000000"
  },
  "analyticsId": "UA-2075101-7",
  "disqusId": "pushed-to"
}
```

* **title** - This is the printed title of your blog.
* **dateFormat** - Is the format of how dates are formatted on your blog (e.g. posted at date).
* **postPerPage** - Number of posts per page in the blog\`s landing page and history.
* **description** - Optional. Is a short description of your blog, it will be displayed on the landing page of your blog.
* **topics** - A list of topics your blog contains. The topics are shown on the landing page and posts can be filtered based on these topics.
* **social** - A list of social accounts:
    * **twitter** - Optional. Your twitter handle (without the @).
    * **linkedin** - Optional. Your linkedin profile url.
* **analyticsId** - Your own tracking id for [Google Analytics](https://analytics.google.com/analytics/web/).
* **disqusId** - Your own project id from [Disqus](https://disqus.com/), if not set a default id will be used to render comments section.

> **Note** Other information like your name, location, website, etc. is taken from your GitHub profile.

## Writing Posts

Every markdown file you place in the master branch of your repository is considered to be a post (except `README.md`). [pushed.to](http://pushed.to) will update your blog within 15 minutes automatically. If you want to update your blog immediately you may also call `http://pushed.to/YOUR_USERNAME/YOUR_REPO/update`.

You can write any Markdown which also works on GitHub; [pushed.to](http://pushed.to) will use GitHub's Markdown rendering to render your blog, thus you may also use any kind of source code in your post which is supported/ rendered by GitHub. 

Apart from that there are some conventions you can use to properly interpret your posts.

### Defining a Post Title

The title of your blog post will be the first line of your markdown which should be a `H1` headline:

```markdown
# This will be your post title

And here starts your content.
```

### Separating the Post's Preview Part

Usually you want to split your post into two parts: A short TL;DR which is shown in the list of posts as well as on the top of the actual post view and the remaining content. You can easily split these parts with a horizontal line (`---`):

```markdown
# This will be your post title

TL;DR

---

The remaining content of your post.
```

### Including Images

For images you may use relative paths within your repository. [pushed.to](http://pushed.to) will properly resolve the relative paths. Every relative path **must** start with `.` or `..`.

```markdown
![Some image](./images/pic-1.jpg)
```

### Linking Topics

A post may be linked/ tagged with topics. To link your post with topics, use a code-block of type `topics` anywhere in your Markdown file. To work properly the code-block whould be after an empty line, and another empty line after it. A best bractice is to include this blog before your TL;DR/ Content separator:

````markdown
# This will be your post title

TL;DR

```topic
topic-a, topic-b
```

---

The remaining content of your post.
````

The `topic` code-block will not be printed in your post. It will be used to display tags and to find the post when filtering for a topic.