Date 01/04/2021
##### How to remove unused dependencies in useEffect?

**Bad example:**

    const [count, setCount] = useState(0)
    const [total, setTotal] = useState(0)

    useEffect(() => {
      console.log(count)
      console.log(total)
    }, [count])

    const handleClick = () => {
      setCount(p => p + 1)
    }

    // this would cause an warning like:
    // Warning: React Hook useEffect has a missing dependency: 'total'.
    // Either include it or remove the dependency array

**Solutions:**

1. Use function as useEffect callback
   
2. Declare function inside useEffect()
   
3. Memoize with useCallback()
   
4. Disable eslint's warning

**Reference:**  
http://www.thewashingtonhua.com/blog/2019/05/27/rethink-in-hooks
https://stackoverflow.com/questions/55840294/how-to-fix-missing-dependency-warning-when-using-useeffect-react-hook

