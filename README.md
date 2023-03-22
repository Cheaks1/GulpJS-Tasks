# GulpJS-Tasks
This is all tasks that i work with it

## Content

- [**my libraries**](#my-libraries)
- [**Css Task**](#css-task)


## My Libraries

```
var gulp = require("gulp");
GulpUglify = require("gulp-uglify");
concat = require("gulp-concat");
prefix = require("gulp-autoprefixer");
sass = require("gulp-sass")(require("sass"));
pug = require("gulp-pug");
source = require("gulp-sourcemaps");
uglify = require("gulp-uglify");
notify = require("gulp-notify");
zip = require("gulp-zip");
babel = require("gulp-babel");
```
#### Notes :
You must add all these libraries into your gulp.file to can use these tasks

## \#01 -------------------------------------- CSS Task -------------------------------------------
This is a **JavaScript code snippet** that defines a Gulp task named" css. **Gulp** is a build system that automates repetitive tasks in web development workflows.
```
gulp.task("css", async function () {
  return gulp
    .src("project/css/sass/*.scss")
    .pipe(sass({ outputStyle: "compressed" }))
    .pipe(prefix("last 2 versions"))
    .pipe(concat("style.css"))
    .pipe(gulp.dest("dist/css"))
    .pipe(notify("Css task is done"));
});

```

**Here's a step-by-step breakdown of what this code is doing:**

-1 The task is defined using the ``gulp.task()`` function, which takes two arguments: the task name ("css"), and a **callback function** that performs the task.

-2 The task function starts by using the ``gulp.src()`` method to select the source files to process. In this case, it's selecting all **.scss files** in the **project/css/sass** directory.
```
.src("project/css/sass/*.scss")
```

3- The selected files are then passed through the ``sass()`` function, which compiles the Sass code to CSS. The outputStyle option is set to **"compressed"** , which means the resulting CSS will have no whitespace and be as small as possible.

```
.pipe(sass({ outputStyle: "compressed" }))
```

4- The compiled CSS is then passed through the ``prefix()`` function, which adds **vendor prefixes** to CSS properties to ensure cross-browser compatibility. In this case, it's adding prefixes for the **last 2 versions** of all major browsers.

```
.pipe(prefix("last 2 versions"))
```

5- The prefixed CSS is then passed through the ``concat()`` function, which concatenates all the CSS files into a single file named " **style.css** ".
```
.pipe(concat("style.css"))
```

6-The concatenated CSS is then written to the dist/css directory using the gulp.dest() method.
```
.pipe(gulp.dest("dist/css"))
```

7- Finally, the ``notify()`` method is used to display a notification message that the CSS task is done. This is an optional step and requires a notification plugin to be installed.

````
.pipe(notify("Css task is done"));
````

Overall, this task takes Sass files, compiles them to CSS, adds vendor prefixes, concatenates them into a single file, and writes the result to a specified directory.
