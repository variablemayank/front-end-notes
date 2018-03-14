# Front-end Notes

### Reduce file size when saving image from canvas using `toDataUrl` method

```
var fullQuality = canvas.toDataURL('image/jpeg', 1.0);  
var mediumQuality = canvas.toDataURL('image/jpeg', 0.5);   
var lowQuality = canvas.toDataURL('image/jpeg', 0.1);
```

### Updating nested state object in React using ID

```
...
constructor(){
  super(props);
  this.state = {
    tasks: [
      {
        id: 1,
        name: "Buy Milk",
        isCompleted: true
      },
      {
        id: 2,
        name: "Take Jimmy to walk",
        isCompleted: false
      }
    ]
  }
}
...
this.setState(prevState => {
   const updatedTasks = prevState.tasks.map(task => {
      return (task.id === 1 ? Object.assign({}, task, {isCompleted: !task.isCompleted}) : task)
   })
   return {tasks: updatedTasks}
})
```

### Convert array of objects into array of properties
```
let users = [
  {id: 0, name: "John", age: 25},
  {id: 1, name: "Stephen", age: 21},
  {id: 2, name: "Robin", age: 32}
];
let userIDs = users.map((user) => {
  return user.id;
});
console.log(userIDs); //[0, 1, 2];
```
