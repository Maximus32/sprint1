# SWE Project Coding Guidelines

*Links DO NOT open a new tab for you*

### General
- **SPACING**: A 'tab' in all file formats (html, css, js) should be TWO (2) SPACES. There's ways to automatically configure this in Sublime (and pretty sure other editors), and to convert tabs into spaces (i.e. when you hit 'tab', it'll actually write two spaces). People how use spaces over tabs make MORE MONEY <sup>[[1]](#note1)</sup><sup>[[2]](#note2)</sup>
- No globals in [production](#Vocab). Only use them for debugging
- Write **descriptive** variable and function names (< 50 characters), so your code speaks for itself. Comments are _lies waiting to happen_ <sup>[[3]](note3)</sup>, therefore only use them to document high level logic, or external APIs functionality.
- Make your code 'maintainable' and modular, meaning it'll be easy to extend with as little changes as possible (meaning 1, **AT MOST 2** changes), and that these changes don't break something else
    - Eg. Don't hard code or rely in constant sizes (lengths/widths) for 2D Arrays
    - *More examples in the works*


*Below sub-sections are in the works*

### Heroku
- Add an 'env' file with the environment variables available in Heroku so process.env.VARIABLE_NAME works while in [development](#Vocab)

### JavaScript, bad vs better
- JS Specific examples of bad vs better code (*need **more***)
    ``` javascript
    // bad
    var config,
        longer_variable;

    // better
    var config;
    var longer_variable;
    ```

### CSS/Styling
- Avoid styling/CSS in HTML files. If you need it, keep it to only one property
- Having issues with placing/moving things around the page? Try out CSS Grids:
    - [Slides](https://www.slideshare.net/mor10/css-grid-changes-everything-about-web-layouts-wordcamp-europe-2017/22)
    - [Entire Video, watch at 1.5x](https://www.youtube.com/watch?v=7kVeCqQCxlk)
    - [To the points](https://youtu.be/7kVeCqQCxlk?t=337)
    - [Actual documentation](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout/CSS_Grid_and_Progressive_Enhancement)
    - [Browser Support](http://caniuse.com/#feat=css-grid)

## TO DECIDE:
- Naming convention: CamelCase vs name_with_underscores
- Chaining of functions in JavaScript, specially for dreaded promises...
    ``` javascript
    Listings.getAll().then(
      function(response) {
        $scope.loading = false;
        $scope.listings = response.data;
      },
      function(error) {
        $scope.loading = false;
        $scope.error = 'Unable to retrieve listings!'
        console.log(error);
      }
    );
    ```


## TO DO: Write linter to enforce this

## Vocab
- Production => Customer Facing Environment, i.e. REAL Application
- Development => 'Plz work'/Stitching everything together Environment
- Sources:
    + <a id="note1">1</a>: [Spaces Article](https://stackoverflow.blog/2017/06/15/developers-use-spaces-make-money-use-tabs/)
    + <a id="note2">2</a>: [Salaries Chart](http://evelinag.com/blog/2017/06-20-stackoverflow-tabs-spaces-and-salary/salary_distribution_junior-1.png)
    + <a id="note3">3</a>: [Comments Article](http://codelikethis.tumblr.com/post/35280704192/comment-like-this)