{{template: logo}}
{{template: title}}

{{template: description}}

{{template: license}}

# React Todo App

This project was bootstrapped to learn React + Mobx. Also to demonstrate skills in mobx.
Mobx is a state management library. That use actions (annotation) [check the docs](https://mobx.js.org/actions.html). I implemented a store TodoStore.js file where I store all the actions in that file.
The actions include addTodo. deleteTodo, checkTodo, doneTodo, cancelTodo, updateTodo, and clear Completed.

All the observable has been implemented as properties of the class TodoStore

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

## Build Setup

```bash
# install dependencies
npm install

# serve at localhost:3000
npm start
```

## Specific branch

If you want to checkout a certain branch:

`git branch -a` to list all the branches.

`git checkout main` (or any branch) to check it out.

No other branch will be checked out, everything is under main.
