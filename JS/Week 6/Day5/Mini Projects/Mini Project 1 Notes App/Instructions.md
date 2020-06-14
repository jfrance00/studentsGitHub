#Notes App - Node.js

In this Mini project you are going to create a Note App with Node.js that will run on the Terminal with commands. This Application allows users to add, read, list, and remove notes. These notes are stored in a json file.


- For Adding a Note you will use the following command ``` node app add --title="Note Title" --body="Note's body" ```

See examples: 

![add1]()

![add2]()


- For displaying the list of notes use the following command ``` node app list ```

See example: 
![list]()


- For reading a note use the following command ``` node app read --title="Note Title" ```

See example: 
![read]()


- For removing a note use the following command ``` node app remove --title="Note Title" ```

See example: 
![removing]()



##Tips:

###app.js:

- You will use an app.js file with the Node File System and creating the terminal commands
- To create the commands in the terminal you will need to install some dependencies:
 1- [Lodash](https://www.npmjs.com/package/lodash) (You will require it and use it's array element as a method with the other dependency for creating the command variable)
 2- [Yargs](https://www.npmjs.com/package/yargs) (Yargs helps you build interactive command line tools, by parsing arguments and generating an elegant user interface. You will require it and use it as a variable with the 'lodash' metohd, and also for adding, reading and removing commands).
- If the user inputs an incorrect command, it will display a message like 'command note recognized'

 
###notes.js:

- You will also use a notes.js file with the Node File System and the ```readFileSync``` and ```writeFileSync``` commands for reading and writing in the json data file and also to do corresponding functions for adding, getting, and removing a note (be sure to export the module)
- When adding a note make sure to display a message 'Note already exists' in the console if the note is already saved
- When reading a note make sure to display a message 'Note not found' in the console if it is not saved
- If the user inputs an incorrect command make sure to display a message 'command note recognized'in the console