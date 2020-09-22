# Discrete Event Simulation in AnyLogic


## Batch Chemical Process

### Step 1. Order generation

1. Create a new model. Choose minutes for time unit.
2. From the Process Modeling Library, add a Source to represent order generation.
    * Change name to `orders`
    * Change Arrivals defined by `interarrival time`
    * Change interarrival time to `uniform(85, 145)`
3. From the Process Modeling Library, add a Sink. 
    * Drag close to the orders icon to establish a link. 
    * Change the name to product
4. Run the simulation. You may need to use 50x real time.
5

### Step 2. Add order queue

1. Delete link between orders and products
2. Insert queue between orders and product.
    * Change name to order_queue
    * Set capacity to 100
    * Under the advanced tab, verify this is a FIFO queue
3. Run the simulation. Verify expected behavior.

### Step 3. Add reactor

1. Delete the link between the order_queue and product. 
2. Add a Resource Pool, rename as `reactors` and set capacity to 3.
3. Add a seize block. 
    * Change name to `sieze_reactor`
    * Set resource pool to reactors
    * Set number of units to sieze to 1
4. Add a delay block.
    * Change name to `reactions`
    * Change delay time to `uniform(275, 395)`
    * Change capacity to 3
5. Add release block. 
    * Change name to `release_reactor`
    * Set Release to `specified resources`
    * Set ResourePool to return reactors
6. Run Simulation

