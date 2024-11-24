# window size project

Using custom hooks 

# using useState hook
const [windowSize, setWindowSize] = useState({
    width: 0,
    height: 0
  })
setting the initial height and width to zero

# handleResize function 
set the current window size 
 function handleResize(){
    setWindowSize({
      width:window.innerWidth,
      height:window.innerHeight
    })
  
  
  }
#  useLayoutEffect hooks 

  add and remove EventListener and initiate handleResize function
  and finally return windowSize 

   useLayoutEffect(()=>{
    handleResize()

    window.addEventListener('resize',handleResize);

    return ()=>{
      window.removeEventListener('resize',handleResize)
    }
  },[])
  return windowSize

  # in the UseWindowResizeTest function decompose the windowSize
  const windowSize = useWindowResize()
  const {width,height}= windowSize


  # bisrat November 24 2024