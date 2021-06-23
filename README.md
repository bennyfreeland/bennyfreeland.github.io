### Understanding the structure

- The site is broadly separated into *pages* and *posts*.
- Pages are *markdown* files (`.md` extension) and live at the top level of the directory. So, if you want to edit the *about page*, you would edit `about.md` at the root of the directory.
- The pages are `about.md`, `blog.md`, `drone.md`, `resume.md`, and `404.md`.
- Posts are also markdown files and live in the `_posts` directory.
- Files and media live in the `assets` directory. Drone footage is under `assets/drone`, general images under `assets/images`, and general files under `assets/files`.

---

Here is a list of things you might want to edit and how to configure them.

*Note: when editing any filepath, keep the format exactly the same as what's provided. Adding a "/" in the wrong place can mess up the whole thing.*

### General

- To add a new file or image, upload it to the appropriate subdirectory under `assets`. You can then link to it with the appropriate filepath format.

### Home page

- To change metadata such as title, description, email, and social links, configure the settings in `_config.yml`.
- To change the banner image, go to `_sass/layout/_banner.scss` and edit the filepath in `'background-image', 'url("../drone/DJI_0523.jpg"))'`.
- To change the title, description, or image, of the tiles, go to the markdown file for the page that corresponds to that tile and edit the `title`, `description`, or `image` values, respectively, at the top.

### About page

- To edit the description, edit the text within the `<p>...</p>` tags in `about.md`.
- To change the image, go to `about.md` edit the filepath in `<img src="{% link /assets/drone/DJI_0356.jpg %}"...`.

### Résumé page

- To update the PDF file, upload a new file to `assets/files` and then go to `resume.md` and edit the filepath in `<a href="/assets/files/benresume.pdf">`. Delete the old file.
- To update entries, edit the text within the `<li>` elements in `resume.md`. To add an entry, copy+paste a previous entry from `<li>` to `</li>` and then make changes.
- To add a new category, add a new `<h3>` element with the title and then create a new `<ul>` element similar to the ones present.

### Drone page

The page is divided into separate sections.

- To add a new section, simply copy+paste one of the preceding sections (starting with `<div class="box alt" >` and denoted by "Start section" and "End section" comments).
- To change the name of a section, edit the text within the `<h3>...</h3>` tags and edit the id name in `<div class="row 50% uniform" id="category1">` to match.
- To add an image, add a new line such as `<div class="6u"><span class="image fit"><img src="{% link assets/drone/DJI_0356.jpg %}" alt="" class="droneImage"/></span></div>` to the section and edit the filepath.
  - The value `class=6u` refers to the fraction of the width that the image takes up. The width is divided into 12 units, so `6u` means the image takes up half the alloted width and hence two images will fit in that row. You can enter anything from `1u` (1/12 total width) to `12u` (= total width) here.
- To add a video, just paste the iframe. Add a `class` value within the `<iframe>` tag to specify width, just like with images.
- To link to a specific section, add to the url a pound sign followed by the section name, e.g. `bennyfreeland.github.io/drone/#category1` (this is why editing the id name in a previous step is important).

### Blog page

The page shows a list of all the blog posts, and each post has its own page.

- To write a new blog post, create a markdown file under `_posts`. Name the file in this format: `yyyy-(m)m-dd-Title.md`, e.g. `2021-6-21-Test.md`. Make sure that the title starts with an uppercase letter; otherwise it will not work (e.g. `Test` not `test`). Add the following snippet to the top of the file, replacing the values of everything except for `layout: post`:
  ```
  ---
  layout: post
  title: Test
  description: Ipsum dolor sit amet
  image: assets/images/pic01.jpg
  ---
  ```
  Make sure that the value of `title` in this snippet matches the title you gave the post in the file name (again, starting character must be uppercase). The contents of the post will go beneath this snippet. They should be written in markdown, which is easy to learn (check the resources).
- To link to a specific post, use the url `bennyfreeland.github.io/blog/Title`. To change the format of the `blog/Title` part of the url (e.g. to something like `blog/date/Title` instead), edit the `permalink` value in `_config.yml`.

### Resources

- Jekyll: understanding [front matter](https://jekyllrb.com/docs/frontmatter/), how to [write posts](https://jekyllrb.com/docs/posts/), and how to [create pages](https://jekyllrb.com/docs/pages/).
- Markdown: [basics](https://markdownguide.org/getting-started/) and a handy [cheat sheet](https://markdownguide.org/cheat-sheet)
- HTML: [basics](https://impactplus.com/blog/21-basic-html-codes-everyone-whos-not-a-developer-should-know)

### Credit

Customization done by [Raj Kane](https://rajrkane.com).