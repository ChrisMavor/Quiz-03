# Quiz-03
Christopher Mavor Quiz 03
def dot(vector01,vector02):
  """
  Inputs:
    vector01: vector in format of a list.
    vector02: vector in format of a list.
  Output:
    dot:
  This function 'dot' takes inputs in the format of lists, or vectors, and performs the dot product of the vectors. Dot product refers to the itemized multiplication of corresponding elements in each vector and sums the product of the itemized multiplication. 
  If there is a mistake in the formating, an error will result specifying the inputs to change in format type so that the function can opperate properly. 
  If proper inputs are given, the end result will return a integer called 'row'.
  """
  if type(vector01)==list and type(vector02)==list:
    #This if statement checks the input type to make sure that they are both lists (or vectors).
    if len(vector01)!=len(vector02):
      #if the first condition was passed, then they must also be the same length so that proper dot products can be multiplied and not run into a index issue. In this loop, there is a return for an inpropper length and sizing or type.
      return "Incorrect sizing. Make sure both inputs are a single list of the same length. Make sure inputs are not integers, matrices(list of lists), or strings."
    elif type(vector01[0])==int and type(vector02[0])==int:
      #If the lengths of the vectors are the same lengths then in this loop they will be indexed based on the range.
      dot=0 #this sets up an empty integer for the sum of the products.
      for i in range(len(vector01)):
        dot+=vector01[i]*vector02[i]
        #dot is an empty vector. the for loop is indexing 
      return 'vector01 * vector02 =' , dot
      #answer for proper input values.
    else:
      return  "Incorrect sizing. Make sure both inputs are a single list of the same length. Make sure inputs are not integers, matrices(list of lists), or strings."
  else:
    return  "Incorrect sizing. Make sure both inputs are a single list of the same length. Make sure inputs are not integers, matrices(list of lists), or strings."
#################
#Test Conditions#
#################
testv1 = [1,2,3]
testv2 = [2,2,2]
#testv1 = 1
#testv2 = 4
#testv1 = [2,3,4]
#testv2 = 'a'
print("Problem 1:",dot(testv1,testv2))


def vecSubtract(vector01,vector02):
  """
  Inputs:
    vector01:
    vector02:
  Output:
    row: itemized vector subtraction indexing each element respective to each vector.

  Function vecSubtraction is taking two vectors and subtracting vector02 from vector02. A vector is the result meaning a list of itemized subtracted elements are the answers. 
  """
  if type(vector01)==list and type(vector02)==list:
    if len(vector01)!=len(vector02):
      #This ensures that the lengths are similar so that subtraction is valid and there isnt an indexing error.
      return "Incorrect sizing. Make sure both inputs are a single list of the same length. Make sure inputs are not integers, matrices(list of lists), or strings."
    elif type(vector01[0])==int and type(vector02[0])==int:
      row=[]#defining an empty list to store the itemized subtraction into a new list that resutls the subtraction.
      for i in range(len(vector01)):
        row.append(vector01[i]-vector02[i])
        #for each i there is an itemization of the vector inputs to subtract the elements from each vector and storing it into a list 'row'.
      return "vector01 - vector02 =",row  
      #proper result from proper inputs.
    else:
      return  "Incorrect sizing. Make sure both inputs are a single list of the same length. Make sure inputs are not integers, matrices(list of lists), or strings."
  else:
    return  "Incorrect sizing. Make sure both inputs are a single list of the same length. Make sure inputs are not integers, matrices(list of lists), or strings."
#################
#Test Conditions#
#################

subtestv1 = [1,2]
subtestv2 = [2,2]
#subtestv1 = 1
#subtestv2 = 4
#subtestv1 = [2,3,4]
#subtestv2 = 'a'
print("Problem 2:",vecSubtract(subtestv1,subtestv2))

def scalarVecMulti(scalar,vector):
  """
  Inputs:
    Scalar: an integer input
    Vector: a list of integer values
  Outputs:
    row: scalar vector multiplication where the scalar multiplies by each element in the vetor and returns a list or vector.

  Function scalarVecMulti takes a scalar and multiplies a vector and returns a vector. This requires that we check they variable input type to ensure that the scalar input is an integer and that the vector input is a list of integers and not a list of lists.

  """
  if type(scalar)==int and type(vector)==list:
    #checking the variable types to ensure proper multiplication and indexing.
    if type(vector[0])==int:
      row=[]
      for i in range(len(vector)):
        row.append(scalar*vector[i])
        #for each i there is an itemization of the vector inputs to multiply the elements from vector by the single scalar value and storing it into a list 'row'.
      return "scalar * vector =",row  
    else:
      return  "Incorrect sizing. Make sure input 'scalar' is a single integer and input 'vector' is a single list. Make sure inputs are not matrices(list of lists), or strings."
  else:
    return  "Incorrect sizing. Make sure input 'scalar' is a single integer and input 'vector' is a single list. Make sure inputs are not matrices(list of lists), or strings."
#################
#Test Conditions#
#################
scalarVecTestS = 7
scalarVecTestV = [4,2]
#scalarVecTestv1 = 1
#scalarVecTestv2 = 4
#scalarVecTestv1 = [2,3,4]
#scalarVecTestv2 = 'a'
print("Problem 3:",scalarVecMulti(scalarVecTestS,scalarVecTestV))

def infNorm(vector):
  """
  Input:
    vector: a list of integers.
  Output:
    currentMax: a integer that is the absulute max of the vector input.

  Function infNorm takes a vector and determines its input type so the make sure proper indexing. The absolute value of each element is found, and a nested for loop allows for the currentMax value to change based on the largest value in the list 'vector'.
  """
  if type(vector)==list:
    #checking input type so to make sure indexing is correct.
    if type(vector[0])==int:
      #finding the absolute value of each element in the list and re assigning it to a new list called 'absvector'.
      absvector=[]
      for i in range(len(vector)):
        absvector.append(abs(vector[i]))

      currentMax=absvector[0]
      #labeling a new integer variable to store the largest value into.

      for i in range(len(vector)):
        #i to index to each new value of the vector.
        if currentMax>=absvector[i]:
          #checking each element to see which one is largest and then reassigning each maximum to the currentMax variable.
          currentMax=currentMax
        else:
          currentMax=absvector[i]
          

      return currentMax
    else:
      return  "Incorrect sizing. Make sure input 'vector' is a single list. Make sure input is not a integer, matrix(list of lists), or strings."
  else:
    return  "Incorrect sizing. Make sure input 'vector' is a single list. Make sure input is not a integer, matrix(list of lists), or strings."
#################
#Test Conditions#
#################
infNormTest = [60,153,59]
#infNormTest = 1
#infNormTest = [4]
#infNormTest = [2,3,4]
#infNormTest = 'a'
print("Problem 4:",infNorm(infNormTest))

def normalize(vector):
  """
  Input:
    vector: a list of integers.
  Output:
    normalized: a list variable of the normalized vector.
  
  Function normalize takes a scalar and vector multiplication. The function first takes the function from problem 4 to find the infinity norm of the vector input. Then after defining currentMax as the infinity norm we then inverse the integer and multiply it by each element in the input vector to result in a new itemized vector. The 'normalized' variable is the result of a scalar vector multiplication.

  """
  if type(vector)==list:
    if type(vector[0])==int:
      
      currentMax=infNorm(vector)  
      #using the function from problem 4 to define the infinity norm.  
      normalized=[]   #labeling a empty list to append values into.
      for i in range(len(vector)):
        normalized.append((1/currentMax)*vector[i])
        #taking the scalar multiplication to result in the normalized vector.
      return "vector*(1/infNorm(vector)) =" , normalized 
    else:
      return  "Incorrect sizing. Make sure input 'vector' is a single list. Make sure input is not a integer, matrix(list of lists), or strings."
  else:
    return  "Incorrect sizing. Make sure input 'vector' is a single list. Make sure input is not a integer, matrix(list of lists), or strings."
#################
#Test Conditions#
#################
#normTest = [43,4,57]
#normTest = 1
normTest = 'a'
#normTest = [2,3,4]
#normTest = [[2],[3],[4]]
print("Problem 5:",normalize(normTest))
