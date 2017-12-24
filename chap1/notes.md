# Chapter 1 Notes

## Decompiling JSX:

- Tool: [Babel](babeljs.io/repl)

## Excerpts:

- Structure of render Result[pg9]
    ```
      // Throws error
      var HelloMessage = React.createClass({
       render: function() {
      return <div>Hello React</div> // error
      <div>How are you?</div>;
      } });

      Error: Parse Error: Line 1: Adjacent JSX elements must be wrapped in
      an enclosing tag
    ```
    The error here is indicating that we need to wrap our JSX in a single root element shown in the following code:
    ```  
     var HelloMessage = React.createClass({
            render: function() {
            return <div> // works
            <div>Hello React</div>
            <div>How are you?</div>
            </div>; }
            });
    ```
    If we paste this in the JSX compiler we won't see any errors and, instead, we will see the compiled React API code as shown below:
    ```
       var HelloMessage = React.createClass({displayName: "HelloMessage",
           render: function() {
             return React.createElement("div", null, " // works",
                 React.createElement("div", null, "Hello React"),
                 React.createElement("div", null, "How are you?")
       ); }
      });
    ```
      Solution: Wrap root functions in parentheses
- props are immutable and not dynamic.
  Changing value of prop requires it to be rerendered

- Prop types
- Default prop
- State
- Dynamic states 
