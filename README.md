
def dot(A,C):
# Start of the definition of the function of the dot product

  n = len(A)
  # Returns number of elements in Vector A
  m = len(C)
  # Returns number of elements in Vector C
  if n == m:
  # The condition that requires the two vectors to be of same length to proceed with the dot product calculation
    B = [0]
  # Defining the initial value for the result of dot product, before anything has been calculated
    b_i = 0
  # Defining where the sum of the values will start
    for i in range(n):
  # This calculation will loop for each position in the vector until completed
       b_i += A[i]*C[i]
  # The actual calculation which consists of corresponding postions in the vectors being multiplied by each other
    B = b_i
  #The final value of the secquence
    return B
  # Returning the final value of the sequence as the new value of B for this condition that the two vectors are of same length
  else:
    return "Invalid Input"
  # If the initial condition is not satisfied and the two vectors are not of same length then there will be an error message stating that there is an invalid input


def vecSubtract(A,C):
# Start of Definition of vector subtraction
  n = len(A)
  m = len(C)
# Measures the lengths of the two vectors
  if n == m:
# The condition that requires the two vectors to be of the same length    
    B = [[0] for row in range(n)]
# Defines the output B to be a vector for each value is 0 as long as the length is in range of the length of A. There is no need to include the length of C in this definition as the if statement already requires both length A and length C to be the same           
    for i in range(n):
# This condition that allows this program to continue to calculate as long as there are more elements in the vector. Ensures that every position in the vectors is accounted for.   
     B[i] = A[i]-C[i]
# The actual calculation of vector subtraction. For each respective position in the vector, the output is the difference between the elements of the two vectors in their same position.
    return B
# Returns the new value for B which is calculated in the previous step
  else:
    return "Invalid Input"
# If the two vectors are not of same length then the output will read an error message stating that the inputs are invalid.



def scalarVecMulti(A,s):
# Defines the fucntion scalarVecMulti, which will calculate the output of multiplication between a scalar and a vector
  n = len(A)
# Defines the length of the vector A as n  
  B = [[0] for row in range(n)]
# Defines B to be a list known as the Vector B and for it to have 0s for every position for as long as it is in range of n, which is the length of A 
  for i in range(n):
# While the position of the vector is within the range of the lenght of A this calculation will continue  
    B[i] = A[i]*s
# The value for each position in the new Vector B is defined as the corresponding position of A's value multiplied by the scalar scalar
  return B
# Returns the value for B after this calculation




def infNorm(A):
# Defines function infNorm which calculates the infinity norm of a vector 
  n = len(A)
# Defines n which is the length of vector A 
  B = [0]
# Defines initial value of B, which is a scalar of value 0  
  sumsquares = 0
# Defines the  initial value of sumsquares which is a scalar of value 0
  for i in range(n):
# This calculation continues as long as we are in the range of the length of A 
    sumsquares += A[i]**2
# Defines the value of sumsquares which is the sum of all the squares of each element in vector A      
    B = sumsquares**.5  
# Defines the value of B which is the square root of sumsquares, square root is not a defined operation, but square root is equivalent to the .5 power     
  return B
# Returns the value of B which is calculated through this function



def normalize(A):
# Defines function normalize which calculates the normalization of a vector 
  n = len(A)
# Defines n which is the length of vector A 
  B = [0]
# Defines initial value of B, which is a scalar of value 0  
  sumsquares = 0
# Defines the  initial value of sumsquares which is a scalar of value 0
  for i in range(n):
# This calculation continues as long as we are in the range of the length of A 
    sumsquares += A[i]**2
# Defines the value of sumsquares which is the sum of all the squares of each element in vector A      
    B = sumsquares**.5  
# Defines the value of B which is the square root of sumsquares, square root is not a defined operation, but square root is equivalent to the .5 power     
  C = [[0] for row in range(n)]
# Defines initial value of C to be a list of 0's up to a range of n, which is the length of A.  
  for  i in range(n):
# Allows this calculation to go on for the range of n, which is the length of A.    
    C[i]= A[i]/B
# Defines the vector C to be each individual element in vector A divided by B which is the value of the infinity norm
  return C  
# Returns the value of C to be the normalization of the Vector A
A=[1,2,3]
C=[1,2,3]
s=1
# These are the values for the vectors A, C and the scalar s.
print("The Dot Product of A and C is:",(dot(A,C)))
print("The difference between vectors A and C is:",(vecSubtract(A,C)))
print("The vector-scalar product of A and s is:",(scalarVecMulti(A,s)))
print("The Infinity Norm of A is:",(infNorm(A)))
print("The Normalization of A is:",(normalize(A)))
