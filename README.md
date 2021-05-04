# dream_car_unrender

## Requirements
>>We are looking for someone to help us translate XD files into Nuxt.js applications and integrate them with wordpress sites (We have prepared well written api docs)

Our highest priority is to write clean code, so it's easily maintainable for other developers (like myself), when I need to do quick fixes for clients.
Here is the task
So this is the task:

Build a Nuxt.js application for this Page: https://wunschauto.onrender.com/ (only homepage)

1. Use Nuxt.js as a framework
2. Use Bootstrap-vue as the CSS Framework
3. No API Integration required
4. Build the app as modular and clean as if it would scale up to a giant web app
5. Write extremely clean index files and components.
6. Make sure that all variables, files, and components are self-explanatory
7. Think in sections and split a page into several section components
8. The hierarchical structure of folders and files need to match the hierarchical structure of template components
9. All components must be entirely modular scoped.
10. Simulate the API by storing all data in a paylaod file and importing it to the index file. You will always receive the data from our api well sorted into sections, the the api simulated data structure should somehting like: var page = {section_head, section_benefits, section_about}, etc...and inside a section, you would find something like var section_head = {title, description, background_image}
11. We're building great website designs for our clients in XD, which then need to be converted into Nuxt.js applications. The Content comes from the Wordpress rest api.

If you're interested, we also have some server stuff to do with wordpress or node.js. Currently though, the majority of work is the translation from XD to well written und clean Nuxt.js apllications.

I've already prepared a javascript payload file to simulate the api for the test run, so you can have all data, but you don't have to take the time to include an api.


>>Meanwhile I decided for the test-run, that it's best for the page to simulate an api call with a payload file in json format, which I'll send you. That means you will receive a payload file for the content of the homepage and a payload file for shared contents like navbar and footer. These files should simulate an api call, so you can import all dynamic data on the index page and deliver it to its subcomponents. All data on the page therefore is dynamic.

Also, for the test-run, you can complete skip the responsiveness, so you don't have to write css for mobile.


>>The main purpose of this task and all future task is to simply deliver ultra clean code, that is extremely maintainable and easy to understand for other developers. I do NOT mean comments in the code, but really good file architecture, code architecture and self-explaining variable names

The hierarchical structure of folders and files need to match the hierarchical structure of template components

## Build Setup

```bash
# install dependencies
$ npm install

# serve with hot reload at localhost:3000
$ npm run dev

# build for production and launch server
$ npm run build
$ npm run start

# generate static project
$ npm run generate
```

For detailed explanation on how things work, check out [Nuxt.js docs](https://nuxtjs.org).
