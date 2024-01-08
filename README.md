<!-- ⚠️ This README has been generated from the file(s) "blueprint.md" ⚠️-->
<p align= "center"> 
<img src="https://github.com/seifedd/TodoApp/assets/21162602/40631b91-421e-4e10-bd9e-6b3058f6beb2" />
</p>


[![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/colored.png)](#react-todo-app)


# ➤ React Todo App

This project was created to learn React + Mobx. 
Mobx is a state management library. That use actions (annotation) [check the docs](https://mobx.js.org/actions.html). I implemented a store file where I store all the actions.
The actions include addTodo. deleteTodo, checkTodo, doneTodo, cancelTodo, updateTodo, and clearCompleted.

All the observable has been implemented as properties of the class `TodoStore` which stores all the observables and actions.

```js
  @observable todoInput = react.createRef();
  @observable filter = "all";
  @observable beforeEditCache = "";
  @observable todos = [];

```

Next each component including TodoCheckAll, TodoItem and TodoClearCompleted, TodoFiltered and TodoRemaining will subscribe to the observable objects and track their state.
This is an example of a Todo CheckAll

```js
const TodosCheckAll = inject("TodoStore")(
  observer((props) => {
    return (
      <div>
        <label>
          <input
            type="checkbox"
            checked={!props.TodoStore.anyRemaining}
            onChange={props.TodoStore.checkAllTodos}
          />{" "}
          Check All
        </label>
      </div>
    );
  })
);

TodosCheckAll.wrappedComponent.propTypes = {
  TodoStore: PropTypes.object.isRequired,
};
```

[![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/colored.png)](#build-setup)

## ➤ Build Setup

```bash

[![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/colored.png)](#install-dependencies)

# ➤ clone Repo
git clone git@github.com:seifedd/TodoApp.git

# ➤ install dependencies
npm install


[![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/colored.png)](#serve-at-localhost3000)

# ➤ serve at localhost:3000
npm start
```

[![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/colored.png)](#specific-branch)

## ➤ Specific branch

If you want to checkout a certain branch:

`git branch -a` to list all the branches.

`git checkout main` (or any branch) to check it out.

No other branch will be checked out, everything is under main.
