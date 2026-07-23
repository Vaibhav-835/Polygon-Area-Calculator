# Polygon-Area-Calculator
A small Python project demonstrating core object-oriented programming concepts: class design, inheritance, method overriding, and dunder methods
Overview

This project implements two classes:

Rectangle — a shape defined by independent width and height attributes, with methods to compute area, perimeter, diagonal length, a text-based visual representation, and how many smaller shapes fit inside it.
Square — a subclass of Rectangle that always keeps width and height equal, reusing and overriding parent behavior where needed.
Features
Method	Description
set_width(width)	Updates the width
set_height(height)	Updates the height
get_area()	Returns width * height
get_perimeter()	Returns 2*(width + height)
get_diagonal()	Returns the diagonal length using the Pythagorean theorem
get_picture()	Returns an ASCII-art representation using *; returns "Too big for picture." if width or height exceeds 50
get_amount_inside(other)	Returns how many times another shape fits inside this one, grid-style, without rotation
__str__()	Human-readable string form, e.g. Rectangle(width=5, height=10) or Square(side=9)

Square additionally overrides set_width and set_height so that setting either dimension updates both width and height, and adds a set_side convenience method — keeping the object a true square at all times.

Example Usage
python
rect = Rectangle(10, 5)
print(rect)                          # Rectangle(width=10, height=5)
print(rect.get_area())               # 50
print(rect.get_perimeter())          # 30
print(rect.get_diagonal())           # 11.180339887498949

sq = Square(9)
print(sq)                            # Square(side=9)
sq.set_width(4)
print(sq)                            # Square(side=4)  <- height updates too

rect2 = Rectangle(4, 8)
small_sq = Square(4)
print(rect2.get_amount_inside(small_sq))  # 2

print(rect.get_picture())
# **********
# **********
# **********
# **********
# **********
