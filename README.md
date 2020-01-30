# vue_sample_app
Sample vue.js app with npm/node for management

Initially based on this tutorial (please read it!)
https://www.vuemastery.com/courses/real-world-vue-js/vue-cli/


To set up the app:

1. Install node
1. Install npm
1. Install vue CLI `npm i -g @vue/cli`
1. Clone this repo
1. cd into hello-world directory and run `npm install`
1. Run `npm run serve`
1. Browse to http://localhost:8080


The code is all now based in the `src/` directory and as a starting point you should look at App.vue and then look at this changeset to see the files that are modified to add features:

https://github.com/petekelly/vue_sample_app/commit/d5e1cfed2b7c553652ac5c68754768a87532194e


As you change the code it will auto-recompile and you will see any errors on-screen.


To make a production build (just JS files, no node or npm you should run `npm run build` and then check the `dist/` directory
