# SymPy Cheatsheet

## Setup
```python
from sympy import *
init_printing()              # pretty print in interactive sessions
x, y, z = symbols('x y z')   # define symbols
```

## Symbols & Expressions
```python
x = Symbol('x')                          # single symbol
x, y, z = symbols('x y z')               # multiple symbols
n = Symbol('n', integer=True)            # with assumptions
p = Symbol('p', positive=True, real=True)

expr = x**2 + 2*x + 1
expr.subs(x, 3)              # substitute: returns 16
expr.subs({x: 1, y: 2})      # multiple substitutions
expr.evalf()                 # numeric evaluation
expr.evalf(subs={x: 2})      # evaluate with values
```

Assumptions: `real`, `positive`, `negative`, `integer`, `odd`, `even`, `prime`, `finite`

## Simplification
```python
simplify(expr)               # general simplification
expand((x + 1)**3)           # expand products/powers
factor(x**2 - 1)             # factor polynomials
collect(expr, x)             # collect terms by symbol
cancel(expr)                 # cancel common factors
apart(1/(x**2 - 1))          # partial fractions
together(1/x + 1/y)          # combine fractions
trigsimp(sin(x)**2 + cos(x)**2)  # trig simplification
expand_trig(sin(x + y))      # expand trig functions
rewrite(expr, sin)           # rewrite in terms of sin
```

## Solving
```python
solve(x**2 - 4, x)                       # solve equation: [-2, 2]
solve([x + y - 2, x - y], [x, y])        # system of equations
solve(x**2 - 4 > 0, x)                   # inequality

solveset(x**2 - 4, x, domain=S.Reals)    # solution set
linsolve([x + y - 2, x - y], x, y)       # linear system
nonlinsolve([x**2 + y - 1], [x, y])      # nonlinear system

roots(x**3 - 1, x)                       # roots with multiplicities
nsolve(cos(x) - x, x, 1)                 # numeric solve (initial guess)
```

## Calculus
```python
diff(x**3, x)                # derivative: 3*x**2
diff(x**3, x, 2)             # 2nd derivative: 6*x
diff(x*y**2, x, y)           # mixed partial

integrate(x**2, x)           # indefinite: x**3/3
integrate(x**2, (x, 0, 1))   # definite: 1/3
integrate(exp(-x**2), (x, -oo, oo))  # improper: sqrt(pi)

limit(sin(x)/x, x, 0)        # limit: 1
limit(1/x, x, 0, '+')        # one-sided: oo

series(exp(x), x, 0, 5)      # Taylor series around 0
series(cos(x), x).removeO()  # remove O() term

summation(1/n**2, (n, 1, oo))  # infinite sum
product(n, (n, 1, 5))          # product: 120
```

## Matrices
```python
M = Matrix([[1, 2], [3, 4]])
M = eye(3)                   # identity
M = zeros(2, 3)              # zero matrix
M = ones(2, 2)               # ones matrix
M = diag(1, 2, 3)            # diagonal

M[0, 1]                      # element access
M.row(0)                     # get row
M.col(1)                     # get column
M.T                          # transpose
M.inv()                      # inverse
M.det()                      # determinant
M.rref()                     # row echelon form
M.nullspace()                # null space
M.columnspace()              # column space
M.eigenvals()                # eigenvalues
M.eigenvects()               # eigenvectors
M.charpoly(x)                # characteristic polynomial

M * N                        # matrix multiply
M ** 2                       # matrix power
M.applyfunc(lambda x: x**2)  # apply to elements
```

## Output
```python
pprint(expr)                 # pretty print to terminal
latex(expr)                  # LaTeX string
srepr(expr)                  # internal representation
str(expr)                    # string form
```
