# Here I report some points that in my opinion we have to insert and disccuss about documentation

* What is Node Addon API (litle overview)
* Reasons and motivations behind the Node Addon API
* Quick start (Very small instructions that allow to start in a fast way)
* Links - reference to more specific parts of the documentation that will be in separate files and treat the following arguments:

    * Installation and usage 
    * What is and how to use Environments
    * What is and how to use Value
    * Creates a JS value from a C++ primitive
    * Creates C++ value from JS value
    * Buffer and TypedArray (They are particular JavaScript object and maybe we need to deepen their usage)
    * Javascript Properties
    * JavaScript Functions
    * Error handling (How to handle the error)
    * ObjectWrap (What is and how to use)
        * Little migration guide to pass from Nan::ObjectWrap
    * AsyncWorker (How to create async function)
        * Little migration guid to pass from Nan::AsyncWorker
    * Conversion tool (How to use and which types of tasks it does for us)
    * News and Updates

At moment there isn't a changelog file it's important to me know the changes happened and maybe the rationale behind them.  

After we will write the documentation we could consider the usage of a tool like [docsify](https://docsify.js.org) that will help us to generate site starting from markdown files.



