import math

def main():

    print('Welcome to Incircle of a triangle calculator.')
    a ,b ,c  = input("Input three sides of triangle: ").split()
    a = eval(a) ; b = eval(b) ; c = eval(c)
    valid_triangle(a,b,c)

    while valid_triangle(a, b, c) == False: 
        print("Error! Cannot form a triangle. ")
        a ,b ,c  = input("Input three sides of triangle: ").split()
        a = eval(a) ; b = eval(b) ; c = eval(c)
        
    calculator_S(a, b, c)
    cal_radius(a, b, c)
    cal_circle_area(a ,b ,c)
    cal_triangle_area(a, b, c)


def valid_triangle(a,b,c):

    if ( a + b > c ) and ( a + c > b) and ( b + c > a):
        return True
    else:
        return False

def calculator_S(a, b, c):
    s = (a + b + c)/2
    return s

def cal_radius(a, b, c):
    s = calculator_S(a, b, c)
    radius = math.sqrt(s * (s-a) * (s-b) * (s-c)) /s
    print(f"Radius: {radius:.2f}")
    return radius

def cal_circle_area(a, b, c):
    radius = cal_radius(a, b, c)
    circle_area = math.pi*(radius**2)
    print(f'Circle Area: {circle_area:.2f}')
    return circle_area

def cal_triangle_area(a, b, c):
    s = calculator_S(a, b ,c)
    triangle_area = math.sqrt(s * (s-a) * (s-b) * (s-c))
    print(f'Triangle Area: {triangle_area:.2f}')
    return triangle_area

main()
