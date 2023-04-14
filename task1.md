/*In this lesson, we will apply our knowledge of JavaScript Closures, to create a simple Todo manager. The plan is: We will create a parent(in context of closure) todoList function. Inside todoList, we will define two child functions add and markAsComplete to perform respective operations. And in the end, we will make sure that the todoList function returns the list of all todos along with the add and markAsComplete function. When it comes to final implementation, we will make use of the Node.js REPL. Open the terminal and run with the node command to go inside the REPL mode.*/
//So, let's get started.
const todoList = () // First, we will define the todoList function.
{
all = [] //Here, we will keep the list of all todos inside the all array.  A Todo, would have three properties: title, dueDate, completed (of type boolean). And inside the all array, we will store Todos as an object. For ex. { title: 'I need to go to gym', dueDate: '22-06-2022', completed: false }
const add = (todoTask) //Next, let's define the add() function.The add() function takes a todoTask as argument, and pushes into the all array.
{
all.push(todoTask)
console.log(all)
}
const markAsComplete = (index) //Similarly, we will define the markAsComplete() function. Here, the markAsComplete() function takes an argument called index. It updates the all array using the index, and marks that specific Todo as completed .
{
all[index].completed = true 
console.log(all)
}
return { all, add, markAsComplete };//To complete the todoList function, we will return the all array and add, markAsComplete functions.
}
//Let's test it out First, in the terminal, we will call the todoList() function.
const todos = todoList()
//Now, you will be able to see the list of all todos by:
todos.all
//[ ] //output // It will return an empty array
//To add a new Todo:
todos.add({ title: 'I need to go to gym', dueDate: '22-06-2022', completed: false })
//[{ title: 'I need to go to gym', dueDate: '22-06-2022', completed: false }] // Output
todos.add({ title: 'Have to buy potato', dueDate: '22-06-2022', completed: false })
//[{ title: 'I need to go to gym', dueDate: '22-06-2022', completed: false }, { title: 'Have to buy potato', dueDate: '22-06-2022', completed: false }] // Output
todos.all
//[{ title: 'I need to go to gym', dueDate: '22-06-2022', completed: false }, { title: 'Have to buy potato', dueDate: '22-06-2022', completed: false }] // Output
//To mark a Todo as complete
todos.markAsComplete(1) //Here 1 is the array index
//[{ title: 'I need to go to gym', dueDate: '22-06-2022', completed: false }, { title: 'Have to buy potato', dueDate: '22-06-2022', completed: true }] // Output
//So, it's working!
/*As we've learned before, in this example, the two functions add and markAsComplete had preserved the legacy variable all when the todoList() function was executed, and continued to preserve (closure) it.*/
