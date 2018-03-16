# Performance matters

## Project setup

This project serves an adapted version of the [Bootstrap documentation website](http://getbootstrap.com/). It is based on the [github pages branche of Bootstrap](https://github.com/twbs/bootstrap/tree/gh-pages). 

Differences from actual Bootstrap documentation:

- Added custom webfont
- Removed third party scripts
- The src directory is served with [Express](https://expressjs.com/).
- Templating is done with [Nunjucks](https://mozilla.github.io/nunjucks/)

## Getting started

- Install dependencies: `npm install`
- Serve: `npm start`
- Expose localhost: `npm run expose`

## First

The base loading time for the entire page without optimalisation is around 30 seconds. Large 
files had to be downloaded every time you loaded the page.

![ZonderAanpassingen](https://github.com/RobinFrugte97/performance-matters/blob/master/images/zonderaanpassing.png)

## Minified code

First off, if minified `bootstrap.css` and `docs.css`. After that, I minified the HTML files and JS files.

This is the result of minifying the code:
![MinifiedCSS](https://github.com/RobinFrugte97/performance-matters/blob/master/images/minifyedcss.png)

The first paint is slightly faster and some files were smaller in size to download.

## Compressed JPG

The site uses a couple of JPG files, which were quite large to download everytime.

I used [TinyJPG](https://tinyjpg.com/) to compress said JPGs. This reduced them in size significantly.

This is the result of compressing the JPG files:

![CompressedJPG](https://github.com/RobinFrugte97/performance-matters/blob/master/images/minifyedcssandcompressedjpg.png)

The total loading time is cut by around 8 seconds.

## Font swap

The next large file that is downloaded everytime is the `fonts.css` file. The file was already minified, but loading the custom fonts delayed text from showing up on the site. 

I used `font-display: swap` to make text show up much quicker. This makes it so the default font is displayed until the custom font is loaded in.

![fontswap](https://github.com/RobinFrugte97/performance-matters/blob/master/images/minifiedjsandfontswap.png)

The first paint is at around 2.5 seconds, instead of 6 seconds.

## Critical css

To further increase the speed of the first paint, I added critical css.

I tried using NPM Critical, but I could not get this to work out. 

Instead, I used an online tool: [Critical Path CSS Generator](https://jonassebastianohlsson.com/criticalpathcssgenerator/)

![CriticalCSS](https://github.com/RobinFrugte97/performance-matters/blob/master/images/criticalcss.png)

The first paint is now at around 380ms.



