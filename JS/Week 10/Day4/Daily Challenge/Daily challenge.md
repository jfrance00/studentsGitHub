## Daily challenge :

## React Redux Blog

![image](https://i.ibb.co/yhr9Sgh/INITIAL-OUTPUT.png)

### Instructions:

#### STEP 1 (Creating the Blog):

- Create React app blog

- For the CSS use [this link](https://drive.google.com/open?id=17WhdHfeGvphf2E8VGVw-vycUekmaloM2)

- Use this [blog.png](https://i.ibb.co/qWhfpk9/blog.png) for the posts

- Put this ```<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/materialize/1.0.0-rc.2/css/materialize.min.css">``` in the head of your ```index.html```

- Create folder components

- Create function component Home.js:

  - Put a Title and a paragraph

  - Import the blog image in ```Home.js``` component (we are going to use this image for our posts)

- Create function component About.js:
  - Put a Title and a paragraph

- Create function component Contact.js:
  - Put a Title and a paragraph

- Create function component Navbar.js:
  - Create a nav with className="nav-wrapper red darken-3"
  - Create a div container with className="container"
  - Inside the div created put a ```<ul className="right">``` and ```li's``` for the home about and contact pages, instead of anchor tags we are going to use ```react router```, ```Links``` and ```Navliks```.
  - ```npm install react-router-dom```
  - Import ```Link```, ```NavLink``` from ```'react-router-dom'```
  - Use ```Link``` tag with ```className="brand-logo"```, set path to the root, add name of the blog
  - use ```NavLink``` instead of anchor tags to point to the pages

- In App.js: import  ```Route```, ```BrowserRouter```, ```Switch``` (this is not to have 2 routes at the same time)
  - wrap the ```div``` with ```BrowserRouter```
  - Import ```Navbar``` component
  - Import the other components
  - Use ```Route``` and set the paths to the other components
  - Wrap the ```Routes``` with ```Switch```

- Check the output


Output 1:

![image](https://i.ibb.co/9nPWZ4k/Output1.png)


#### STEP 2:

- Make your Home component a class component

- Create a class component ```Post.js``` (This will be our Route when we click on a post) so add the Route to your ```App.js```

- We will use ```post_id``` for the Path

- Render a Title and a Paragraph


Output 2: 

![image](https://i.ibb.co/F3QGY3F/Output2.png)


#### STEP 3 (REDUX):

- ```npm install redux react-redux```

- (Creating the store) In index.js:
  - Import ```createStore``` from ```redux```
  - Create ```store``` and store it in a variable, the parameter will be our reducer function
  - Import ```provider``` from ```react-redux```
  - Wrap the ```app``` with the ```provider``` and use the ```store```

- In src folder create ```rootReducer.js``` file (this will be our function reducer to update the state):
  - Create an ```initial state``` with this data for the posts:

```javascript
    {id: '1', title: 'Sunt aut facere repellat provident occaecati excepturi optio reprehenderit', body: 'Lorem ipsum, dolor sit amet consectetur adipisicing elit. Consequatur voluptate laborum perferendis, enim repellendus ipsam sunt autem at odit dolorum, voluptatum suscipit iste harum cum magni itaque animi laudantium fugiat'},

    {id: '2', title: 'Dolorem eum magni eos aperiam quia', body: 'Lorem ipsum, dolor sit amet consectetur adipisicing elit. Consequatur voluptate laborum perferendis, enim repellendus ipsam sunt autem at odit dolorum, voluptatum suscipit iste harum cum magni itaque animi laudantium fugiat'},

    {id: '3', title: 'Ea molestias quasi exercitationem repellat qui ipsa sit aut', body: 'Lorem ipsum, dolor sit amet consectetur adipisicing elit. Consequatur voluptate laborum perferendis, enim repellendus ipsam sunt autem at odit dolorum, voluptatum suscipit iste harum cum magni itaque animi laudantium fugiat'} 
 ```

- Create the ```reducer``` function, use ```state``` and action for parameters
  - Export the function, and imported to index.js to use it in the store variable

- In Home.js:
  - Import ```connect``` from ```react-redux```
  - Create ```mapStateToProps``` function, use ```state``` as param to access the state from the store
  - Return the ```state.posts```
  - Wrap ```connect``` to the ```export``` component
  - In the render console log ```this.props```
  - Set variable posts to ```this.props```

- Create a ternary operation to check:
  - if we have the posts, then ```map``` the posts, ```return: div with className="post card"``` and ```post.id``` as key, the image blog that we imported, add another ```div``` with ```className="card-content"``` inside, a ```span``` with ```className="card-title red-text"``` and ```post.title``` as the content, wrap the ```span``` with the ```Link``` tag: ```<Link to={'/' + post.id}>``` from react router and after that also put a ```paragraph tag``` with the ```post.body``` 

  - else, return a ```div``` with ```className="center"``` with No post to show message

  - Finally ```return``` a ```div``` with ```className="container home"```, inside your Home Title and the postList

Output 3:

![image](https://i.ibb.co/n7k0545/Output3.jpg)


#### STEP 4:

- In Post.js:
  - Connect the component to the redux store, import ```connect``` and use it to wrap the component
  - Create ```mapStateToProps``` function, use ```state``` and ```ownProps``` for params
  - We will use the post id to match and find a particular post from the state in the store
  - Return the object: return the state of posts and use the ```find``` method to find the particular post if the ```post.id``` is equal to the id variable.
  - Pass the ```mapStateToProps``` function to the ```connect```

- In the render of the components:
  - Create ternary operation to check:

  - if we get ```this.props.post```, create ```div``` with ```className="post"```, a ```title``` with ```className="center"``` and ```post.title``` as content, a ```paragraph``` with ```post.body``` as content

  - else display ```div``` with ```className center``` with a ```Loading...``` post message

  - Return ```div``` container with the ```post``` as content.

Output 4:

![image](https://i.ibb.co/YtC2rct/Output4.png)


#### STEP 5 (Updating the state "Delete Post"):

- In Post.js:
  - Create a ```mapDispatchToProps``` function, use ```dispatch``` as param
  - return the object: return a function called ```deletePost```, it will have ```id``` as param, it will dispatch an action: type will be ```DELETE_POST``` and ```id```. 
  
- For better separation of concerns, we will have our action creator in a separate file:
- Create Postactions.js file:
  - create a ```deletePost``` function, use ```id``` as param, return an object of the action type ```'DELETE_POST'``` and the ```id```
  - Export function

- In Post.js:
  - Import ```deletePost``` from ```Postactions.js```
  - In ```mapDispatchToProps``` function, dispatch the function with param ```id```
  - Pass the function to the ```connect```
  - Console log ```this.props```
  - After the paragraph create a ```div``` with ```className="center"```, inside a ```button``` with ```className="btn grey"```, and ```Delete post``` as content.
  - Add ```onclick``` event to call a function ```handleClick```
  - The ```handleClick``` function will call the ```deletePost``` method with ```props```, grab the ```id``` of the post to redirect to home page when we delete a post, use ```this.props.history.push('/');``` 

- In rootReducer.js, in the reducer function:
  - console log the ```action```
  - If ```action.type``` is equal to ```'DELETE_POST'```, ```filter out``` the posts from the ```state```
  - Return the post ```id``` if its not equal to the ```action id```
  - Return a new object that is the new state, use spread operator ```[...]``` for the state and return the new posts

Output 5:

![image](https://i.ibb.co/NN0RW5C/Output5.jpg)

