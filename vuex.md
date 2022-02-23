# What is Vuex?
Vuex is a state management pattern + library for Vue.js applications.

# What is a "State Management Pattern"?
A vue component is composed by 3 parts:
- The state, the source of truth that drives our app;
- The view, a declarative mapping of the state;
- The actions, the possible ways the state could change in reaction to user inputs from the view.

## State
Vuex uses a **single state tree** - that is, this single object contains all your application level state and serves as the "single source of truth." 
This also means usually you will have only **one store** for each application.

Components Can Still Have Local State: If a piece of state strictly belongs to a single component, it could be just fine leaving it as local state.

### Vuex.Store
Is composed by:
- State: data
- Getters: computed properties to retrieve data
- Mutations: events to change data
    ```
    const store = createStore({
      state: {
        count: 1
      },
      mutations: {
        increment (state) {
          // mutate state
          state.count++
        }
      }
    })
    ```
    You cannot directly call a mutation handler. You need to call `store.commit` with its type:
    ```
    store.commit('increment')
    ```
- Actions: similar to mutations, the differences being that:
    - Instead of mutating the state, actions commit mutations.
    - Actions can contain arbitrary asynchronous operations.
- Modules: allows us to divide our store into modules. Each module can contain its own state, mutations, actions, getters, and even nested modules
    - Namespaced (default false)
    - Submodules


Reference: https://vuex.vuejs.org/
