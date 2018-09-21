from fractions import Fraction
def solver(coefficientmatrix, resultmatrix):
    #Eliminate x from the equation

    #Multiply equation 1 by the coefficient of x in equation 2
    eq1a = [coefficientmatrix[0][i] * coefficientmatrix[1][0] for i in range(3)]
    #Multiply equation 2 by the coefficient of x in equation 1
    eq2a = [coefficientmatrix[1][i] * coefficientmatrix[0][0] for i in range(3)]
    #Form a new equation in y and z by subtracting the two new equations
    eq3a = [eq1a[i] - eq2a[i] for i in range(3)][1:]
    eq4a = resultmatrix[0] * coefficientmatrix[1][0] - resultmatrix[1] * coefficientmatrix[0][0]

    #Eliminate x from the equations again using equation 1 and 3

    #Multiply equation 1 by the coefficient of x in equation 3
    eq1b = [coefficientmatrix[0][i] * coefficientmatrix[2][0] for i in range(3)]
    #Multiply equation 3 by the coefficient of x in equation 1
    eq2b = [coefficientmatrix[2][i] * coefficientmatrix[0][0] for i in range(3)]
    # Form a new equation in y and z by subtracting the two new equations
    eq3b = [eq1b[i] - eq2b[i] for i in range(3)][1:]
    eq4b = resultmatrix[0] * coefficientmatrix[2][0] - resultmatrix[2] * coefficientmatrix[0][0]

    #Eliminate y from the equation using the same process as done on x
    eq1aa = [eq3a[i] * eq3b[0] for i in range(2)]
    eq2aa = [eq3b[i] * eq3a[0] for i in range(2)]
    
    #Find z, and then x and y by substitution
    z1 = (eq4a*eq3b[0] - eq4b*eq3a[0])/([eq1aa[i] - eq2aa[i] for i in range(2)][1])
    z = Fraction(z1)
    y1 =  (eq4a -(eq3a[1]*z))/(eq3a[0])
    y = Fraction(y1)
    x1 = (resultmatrix[0] - coefficientmatrix[0][2] *z- coefficientmatrix[0][1]* y)/(coefficientmatrix[0][0])
    x = Fraction(x1)
    return "[x,y,z] = " + str([x,y,z])
    
print solver([[5,2,1],[1,6,3],[2,4,7]], [8,17,98])
