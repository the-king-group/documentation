---
layout: default
title: Translating numpy to jax.numpy
parent: Tutorials
nav_order: 2
---

## Translating numpy to jax.numpy

If your simulations will be using JAX it is best to use jax.numpy anywhere you would use numpy. This is because using jax.numpy ensures that all of your arrays, operations, calculations, etc, are compatible with jax when you go to use the auto differentiation and optimization features of JAX. 

Generally jax.numpy works the same as numpy just with different syntax, please see the jax.numpy documentation if you ever need to double check how the syntax works. A VERY IMPORTANT DIFFERENCE is that to use one of the modes of auto differentiation the computation graph must be static. This means that any arrays, lists, or variables you make cannot change type (you can cast things in place if you need them to change momentarily) and cannot change shape (in the case of arrays) from when you first declare them. 

For example you cannot use the 
~~~
list.pop()
~~~
to remove values off a list. Instead you would want to do something like this:

~~~
list_arr = jnp.array(list)
new_list_arr = list_arr[:-1]
#where jnp is jax.numpy
~~~

There are also specific syntax differences for changing values in an array, rather using
~~~
arr[i] = value
~~~
you must use the jax.numpy syntax
~~~
arr = arr.at[i].set(value)
#where arr is a jas numpy array
~~~

When in doubt check the jax.numpy syntax, many small errors are fixable by googling the erorr and making sure you are using the right jax.numpy syntax. 

Please see [JAX numpy documentation](https://docs.jax.dev/en/latest/jax.numpy.html) for further details.

Last update: Katherine Ellis 7/28/26
