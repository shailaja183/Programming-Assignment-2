# Programming-Assignment-2 Explanation

# assumption : Only for Square Invertible Matrix

makeCacheMatrix <- function(x = vector()){
# declaration of user defined function and passing the arguement of vector type into it
inv <- NULL
# null type variable inv
set <- function(y) {
x <<- y
inv <<- NULL
}
# creating object of matrix
get <- function() x
setinv <- function(inverse) inv <<- inverse 
getinv <- function() inv
# defining set, get methods for setting and retriving value of a matrix
# defining setinv, getinv methods for setting and retriving value of inverse of a matrix
list(set=set, get=get, setinv=setinv, getinv=getinv)
}

cacheSolve <- function(x, ...) {
# defining other user defined function for cacheing the inverse of a particular matrix 
inv <- x$getinv()
# assigning x$getinv() to inv 
if(!is.null(inv)) {
message("getting cached data")
return(inv)
}
# if invese of a matrix is calculated more than once then it is printed that "getting cached data" to show working of cache 
# function (if inverse is not null)
data <- x$get()
inv <- solve(data, ...)
# calcuation of inverse using solve()
x$setinv(inv)
# storing inverse to inv
inv
# returning inverse
}

