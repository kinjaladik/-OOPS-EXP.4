# -OOPS-EXP.4
C++ program demonstrating runtime polymorphism using virtual functions and an abstract base class .Implementing a shape Hierarchy with area () method .

#include <iostream>
using namespace std;

class Shape {
public:
    virtual void area() = 0; 
    virtual ~Shape() {} };

//Circle
class Circle : public Shape {
private:
    float radius;

public:
    Circle(float r) {
        radius = r;
    }
    void area() override {
        cout << "Area of Circle = " << (3.1416 * radius * radius) << endl;
    }};

//Rectangle
class Rectangle : public Shape {
private:
    float length, breadth;

public:
    Rectangle(float l, float b) {
        length = l;
        breadth = b;
    }
    void area() override {
        cout << "Area of Rectangle = " << (length * breadth) << endl;
    }};

//Triangle
class Triangle : public Shape {
private:
    float base, height;

public:
    Triangle(float b, float h) {
        base = b;
        height = h;
    }
    void area() override {
        cout << "Area of Triangle = " << (0.5 * base * height) << endl;
    }};

// Function demonstrating runtime polymorphism
void displayArea(Shape &s) {
    s.area();
}

int main() {
    Circle c(5.0);
    Rectangle r(4.0, 6.0);
    Triangle t(5.0, 5.0);
    cout << " Runtime Polymorphism Demo \n";
    displayArea(c);
    displayArea(r);
    displayArea(t);
    return 0;
}
