# Rhino-h5

> A D&I project, simple animation h5, using raw SVG.

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build
```

For detailed explanation on how things work, checkout the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).

## Implementation
Each animation page is implemented by a svg page. Animation mostly use animate and animateTransform element.

## Suggestion
If you want to implementation h5 page with simple animation, here are some possible suggestions:
- Using Canvas, with javascript. Given priority if animation is complex.
- Using SVG, with SVG library, [Snap.svg](http://snapsvg.io/) e.g.. **DON't use raw SVG like this project.**
- Using CSS animation, but difference may exist between different platforms. Not recommended if animation is intensive.

Vue is totally redundant in this project. Simply gulp or webpack configuration can handle perfectly and lightweightly. Even `Wechat Mini Programs` may be better fit for the scene.

## So why did I implement like this
- Never used SVG before, lack experience
- Forgot the existence of SVG libraries
- Sooooo close deadline, without time to do the refactor
- Disinclined to configure webpack
