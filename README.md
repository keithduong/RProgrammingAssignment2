# RProgrammingAssignment2
makeCacheMatrix <- function(x = matrix()) {
  m <- NULL
  set <- function(y){
    x <<- y
    m <<- NULL
  }
  
  get <- function() x
  
  
  
  setInverse <- function(solve) m <<- solve
  getInverse <- function() m
  
  list(set = set, get = get, setInverse = setInverse, getInverse)}

cacheSolve <- function(x, ...) {  
  
  m <- x$getInverse()
  
  if(!is.null(m)){
    message("HEY HEY")
    
    return(m)
    
  }
  
  data <- x$get()
  m <- solve(data, ...)
  x$setInverse(m)
  m }
