# Daily Workaround
Record solutions that fix daily issues.

### Format
Date 01/04/2021
##### How to set state with data from react-apollo Query?

**Bad example:**

    <Query>
      {(data, loading, error) => {
        this.setState({...})
        return ...
      }}
    </Query>

    // this would cause an warning like:
    // Warning: Cannot update during an existing state transition 
    // (such as within `render`). Render methods 
    // should be a pure function of props and state.

**Solutions:**

1. Whatever component needs this data as state should be rendered inside the Query component, and then have the data passed down to it as a prop.

2. Use the onCompleted prop on Query component to set the state. This might be a better one when the data you need from query is mixed with static data, like an unchanging title for a section.
   
       doSomething = data => {
         this.setState({title: data.title})
       }
       
       <div>this.state.title</div>
       <Query onCompleted={data => this.doSomething(data)}>
       {(data) => {
         return (
           <div>this.state.title</div>
         )
       }}
       </Query>

       // you can use this state inside or outside this query

**Reference:**  
https://moondaddi.dev/post/2018-09-08-How-to-set-state-with-data-from-graphQL-query/
https://stackoverflow.com/questions/50437054/setting-state-in-the-query-component-of-react-apollo
