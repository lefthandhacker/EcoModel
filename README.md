# eco-model

A JavaScript library for ecosystem modeling and analysis. https://blmgeo.github.io/eco-model

## Steady State  

A steady-state model is initialized by calling the `state` method and passing an object with `residence`, `flow`, and/or `stock` properties, e.g.  
~~~
const model = SteadyState.state({
  flow: 10,
  stock: 1000
})
~~~
In this case, `._residence()` yields the residence time of the model. 

### Methods  
__SteadyState.state(props)__  
Initialize a model with `residence`, `flow`, and/or `stock` properties.  

__model._residence()__  
Calculate the residence time of an initialized model.

__model._flow()__  
Calculate the flow rate of an initialized model.

__model._stock()__  
Calculate the stock of an initialized model.

## Non-Steady State

A non-steady-state model is initialized by calling the `state` method and passing an object with `stock`, `flow`, and/or `deltaFlow` properties, e.g.  
~~~
const model = NonSteadyState.state({
  stock: 1000,
  flow: 10,
  deltaFlow: -0.05 * 10
})
~~~

### Methods  
__NonSteadyState.state(props)__  
Initialize a model with `stock`, `flow`, and/or `deltaFlow` properties.  

__model.update(props)__  
Update the model properties after initialization if they have changed.

__model.stockAt(time)__  
Calculate the amount of stock in a system at a given time.

__model.flowAt(time)__  
Calculate the total flow rate (F<sub>in</sub> - F<sub>out</sub>) of a system at a given time.

