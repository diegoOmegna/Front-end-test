milestone 1
-I start by creating a form input, where the data is binded through v-model to the Addtask.task property, which is in a reactive, so ican access multiple items inside, liek id and properties like isCompleted and so.
-Then i created an event handle activated by the keyup.enter, to emit through addTask.
-on the fucntion addTask i tried to check if newTask is empy and if not i woudld emit the event and data, and tried to bring back the form to empty.
-In the TaskItem.vue component, i display in the moustaches the data i got ffrom the define props coming from the form. On top of the script i was adding an event handler for when i click the checkbox the i would emit the event toggleCompleted to chenge the prperty of the task from complete:false to :true.
-Add aswell a class compelted-task to change the opacity if the div task.

-In the ListView view, i cal both components and import them, and made a v-for iteration over TaskItem lsitening to the event of toggle-completed.
-All new items would be push to taskList through the addTask function, where i created a unique id base on the array length and add 1 to each item.
-Also the other properties like the task Itself and the isCompleted would be push in every ite, created.



# task-manager

## Project setup
```
yarn install
```

### Compiles and hot-reloads for development
```
yarn serve
```

### Compiles and minifies for production
```
yarn build
```

### Lints and fixes files
```
yarn lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
