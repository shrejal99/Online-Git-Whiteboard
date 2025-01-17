<p align="center">
 <img src="https://user-images.githubusercontent.com/84700316/137097468-ef6b678c-5157-4f10-9cc0-83559cba415b.png" width=300px>
 </p>


# Online Git Whiteboard 
The Online Git Whiteboard is a stateless (i.e. purely client-side) web application that allows you to quickly and easily create Git graphs in your browser for demonstration purposes. The application is designed to provide all the visual possibilities that are usually required on a whiteboard to draw Git graphs: Commit graphs, HEAD, branch and tag labels, simplified commit IDs, commits which are lost in the reflog, etc. The handling must be quick and easy, so that during a Git training course, for example, you can create a simple demo Git graph with a few mouse clicks to explain a specific Git concept. The Git Whiteboard App's goal is to eliminate the need to use a whiteboard or flipchart to draw Git Graphs during a training session or lecture.he handling must be quick and easy, so that during a Git training course, for example, you can create a simple demo Git graph with a few mouse clicks to explain a specific Git concept. The Git Whiteboard App's goal is to eliminate the need to use a whiteboard or flipchart to draw Git Graphs during a training session or lecture.

This is the app in action. It shows a simple demo Git history which can be used to explain and demonstrate a number of Git features:

![ScreenShot of the app](docs/img/screenshot1.png)

### With the current version, you can demonstrate the following Git features:
 
* add commits,
* amend the HEAD commit,
* cherry-pick commits,
* add branches and tags,
* delete branches and tags,
* create a detached HEAD and create commits in detached HEAD state,
* check out individual commits, resulting in a detached HEAD,
* check out branches,
* check out tags, resulting in a detached HEAD,
* merge branches with and without fast-forward merges,
* rebase one branch onto another,
* show commits which have been lost in the reflog,
* perform a garbage collection to remove such lost commits,
* show/hide lost commits,
* reset branches (only moving around the branch label is supported; a soft, hard, and mixed reset is not explicitly visualized).

**More advanced features, such as working remotely with `push`, `fetch`, and `pull`, will be supported in a later version.**

## Try it out

You can try out the app at [https://git-whiteboard.netlify.app/](https://git-whiteboard.netlify.app/). Alternatively, you can run the pre-built version of the Git Whiteboard App locally in directory `/try-it-out`. Just open the `index.html` file in your browser.

## How to build and run

To build the app, run the following command on the console:

```
./gradlew run
```

Then visit `http://localhost:9090` in your browser. You need to have a JDK installed for this.

To build the production version of the app simply run

```
./gradlew
```

This will build the standalone version in `build/distributions` which can be run by just loading `index.html` in a browser.

## Motivation
One problem that arises with any Git training is that when explaining Git functionality, it is relatively cumbersome for the trainer to adequately illustrate the dynamics of a Git history as it evolves. To date, a trainer has only the following three tools to visually demonstrate the creation of a Git History. Each of these three has its own specific drawbacks:

* Creation of a Git Graph across multiple PowerPoint slides: only depict a simple and predefined scenario. Offers no possibility to vary or extend a scenario.

* Demonstrating the creation of a Git history on the command line with Git commands: this is cumbersome, because in order to achieve certain steps (e.g., create some sample commits), you must perform many manual steps that are irrelevant to the example (e.g., make local changes several times, invent a commit message, perform a commit).

* Drawing on the whiteboard or flipchart: In order to be able to display the dynamics of a Git history, you must constantly wipe away parts of the drawings on the whiteboard and redraw them, which is not possible on a flipchart. When you move the HEAD pointer and branch labels, you quickly reach the limits of what is possible. Some trainers help themselves with small pieces of paper on which the branch names are written, and adhesive tape. Furthermore, space is limited; especially flipcharts are unsuitable for Git history graphs.
  
The Online Git Whiteboard  is supposed to offer another flexible alternative. With this web application, it must be at least as easy to visualize a Git history as on a whiteboard. But in contrast to drawing on the whiteboard, dynamically changing the history should be much easier. For example, it should be possible to move a branch pointer anywhere in the Git graph, as with Git reset. Also, functions like Git rebase should be easier to display visually than on the whiteboard.

## User manual

You can find the user manual [here](src/docs/asciidoc/manual.adoc). You can open the manual directly from the application on the `About` tab.

## Implementation

The Git Whiteboard App is exclusively implemented with Kotlin/JS, i.e. the application is written with Kotlin and compiled into JavaScript code. The app is stateless. This means that no server is necessary to run the app. As described above, it suffices to load the `index.html` in a browser.

### open-source projects used to create the Git Whiteboard App:

* [Kotlin/JS](https://kotlinlang.org/docs/reference/js-overview.html)
* [Ktor for the local development mode](https://ktor.io/)
* [kotlin-react](https://github.com/JetBrains/kotlin-wrappers#readme)
* [fabric.js Javascript HTML5 canvas library](http://fabricjs.com/)
* [The Bulma CSS framework](https://bulma.io/)
* [Font Awesome](https://fontawesome.com/)
* [Asciidoctor for the user manual](https://asciidoctor.org/)
