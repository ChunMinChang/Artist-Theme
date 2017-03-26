# Artist Theme: A Free Theme for Jekyll Sites
Forked from [ninapetrop/Artist-Theme](https://github.com/ninapetrop/Artist-Theme).

## Dependencies
1. Jekyll
2. Gulp
3. Sass
4. Jade

## Installing markdown parser
We use ```redcarpet``` here.
Run ```$ gem install redcarpet``` (You may need to add ```sudo```).
Or you could replace parser to ```kramdown``` in ```markdown``` of ```_config.yml```.

## Run Gulp with jekyll

Read [this](https://aaronlasseigne.com/2016/02/03/using-gulp-with-jekyll/) first.
Make sure we have ```exclude: ["node_modules", "gulpfile.js", "package.json"]```
in ```_config.yml```.

### Installing Gulp

- Install gulp available as a system wide command:
  - ```$ npm install --global gulp```
- Saves it to the local ```node_modules``` directory
  and adds it to your ```package.json```:
  - ```$ npm install --save-dev gulp```
- Install all required modules in ```gulpfile.js```.
  - ```$ npm install --save-dev gulp-util``` for ```child_process```
  - ```$ npm install --save-dev browser-sync``` for ```browser-sync```
  - ```$ npm install --save-dev gulp-autoprefixer``` for ```gulp-autoprefixer```
  - ```$ npm install --save-dev gulp-jade``` for ```gulp-jade```
  - ```$ npm install --save-dev gulp-sass``` for ```gulp-sass```
- Or you can run a one-line command:
  - ```npm install --save-dev gulp browser-sync gulp-autoprefixer gulp-jade gulp-util gulp-sass```

### Running websites
Run: ```$ gulp```

### Changing the default behavior
Check what you run in ```gulp.task('default', ['browser-sync', 'watch'])```.

## Category
Just need to add your category-name into ```categories``` in the post.
We will automatically list them in ```nav.html```.

### Old way in original repo
Originally, we need to put something like below into a html page
(e.g. ```category1.html```), and move it into ```/categories```.
```
{% for post in site.categories.category1 %}
  <div class='listing'>
    <a class='post-title' href='{{ post.url }}'>{{ post.title }}</a>
    <p class='meta'>{{ post.date | date_to_long_string }} / by {{ post.author }}</p>
  </div>
{% endfor %}
```
Then we need to add ```a(href='{{ site.url }}/categories/category1.html') Category 1```
into ```nav.jade``` to generate a new ```nav.html```.
