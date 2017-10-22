# Native Addons Emit and Stream  

In this chapter we’ll build addons that expose interfaces that mimic **EventEmitters** and **streams**. 
These interfaces are particularly well suited for long running C++ worker tasks that continuously
either send input back to JavaScript or receive a series of inputs from it.

Sometimes we use C++ to do some heavy compute task that actually generates partial results over time

One way to work with addons like this would be to make it asynchronous, and when the results are completed, 
we could make the addon return the entire result 

Alternatively, we could implement the asynchronous addon such that all partial results were returned immediately,
through invoking a JS callback.

We have an addon that is long running, and sends frequent updates

AsyncProgressWorker collapses consecutive progress updates if they haven’t been processed by JavaScript quickly. 
For example, if progress is reported at 0, 50, 100% in the worker code all before the next event loop cycle, the Node.js
 will only receive a single progress indicator
- 100%. This makes a lot of sense from a progress report standpoint - but not for message passing!

If you look deep inside **AsyncProgressWorker**, you’ll see that the code in fact declines to invoke the progress
callback if the worker is already completed.

