# In-class lab: React Photos Stream

Notes:

After each step; make a git commit using the GitHub App.

Steps to complete:

 0. Download the gist at https://gist.github.com/kylefritz/d987b2a3c60423239354. Make a folder on your deskop with the index.html file and the readme.md file. Turn this folder into a git repo using the GitHub App (there's a plus button in the top left hand corner).
 1. Convert the HTML mockup to React. Start with just a single component called `<PhotoList />` that represents the entire photo stream. Don't worry about dynamic data yet; just render the same html from using React. Replace the contents of the `#photo-app` div with your React app by using `React.render(<PhotoList />, document.getElementById('#photo-app'))`). Make a commit!!
 2. Break your single react component into two components. `<PhotoList />` and `<PhotoCard />`. A `<PhotoList />` contains many `<PhotoCard />`s. Static data is fine. Render your `<PhotoCard />` multiple times.  Make a commit!!
 3. Parameterize your `<PhotoCard />`. Pass in the important data as attributes (props). `<PhotoCard imageUrl="" title="" comment="" isLiked="" />` Render multiple `<PhotoCard />`s and vary the attributes manually.  Make a commit!!
 4. Extract the data from the original mockup and store them in an array of object literals. What are the objects properties? `{imageUrl:, title:, comment:, isLiked:}` Add an array of these object literals to the top of your script. Make a commit!! [Extra credit: To view the mockup, try going back two commits to the original HTML mockup commit. Use the github app to get the commit hash of the initial commit, then try `git checkout <commitHash>` in the terminal (make sure you're in the project directory). When you're done use `git checkout master` to go back to the `HEAD` of your repo.]
 5. Pass the  new object literal of your photo data in `<PhotoList />` as a `prop` called `photos`. Generate an array of `<PhotoCard />` from `props.photos`. Set the props on each `<Photocard />` to the props of each photo object. Make a commit!!
 6. Copy `isLiked` from props into `state` by implementing `getInitialState` on your `<PhotoCard />`. Handle clicking on the "Like" button by changing the value in state (and updating the button to say "Unlike"). Make a commit!!
 7. Turn your attention to the form below the card list. Create a react `<PhotoForm />` Handle submission of the form to print the form values to the console. Make a commit!!
 8. Use the form values to add another card to your photo data and re-render the `<PhotoList />`

Extra Credit:
 1. Use the "spread operator" `{...}` to pass in props to your `<PhotoCard />`
 2. Use `propTypes` to document the required `props` for your `<PhotoCard />`. What happens when you don't set one?
 3. Build two objects: A and B each with a method `sayHi` that prints to the console. Assign `B`'s method `sayHi` to a property on `A` called `onSayHi`. Modify `A`'s `sayHi` method to also call `onSayHi` if it is defined. This is the basis of eventing.
 4. Create a Store object that has methods to get photos and to add a photo. Also create a property that is a function that will be called when a new photo is added. Wire that property to a function in your `<PhotoList />`. This will let your store the photos in `state` on `<PhotoList />` but still handle updates when the store changes.
 5. Persist Photos to localStorage by adding methods to your store.
