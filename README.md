# OpenGL.swift
## (note this is intented for use on linux platforms)
A swift module for using opengl methods and graphics

you will need the following dependencies:
* glfw3 (requires the two dependencies below)
* xorg-dev
* libgl1-mesa-dev
* swift

this module can be used by creating a Package.swift file in your swift project and adding this code in Package.swift
```
import PackageDescription

let package = Package(
  dependencies: [
  .Package(url: "https://github.com/Quackattack70/OpenGL.swift.git", majorVersion: 1)
  ]
)
```
make sure to compile your project by using the following commands:
```
cd <project dir>
swift build
```
then run it with ```.build/debug/<executable name>```. The executable name will (most likely) be your project name lower cased

Here is an example of using the module:
```
import OpenGL.GL
import OpenGL.GLFW

if glfwInit() == GL_FALSE {
  print("error")
}

glfwDefaultWindowHints()
var window = glfwCreateWindow(300, 300, "title", nil, nil)

glfwMakeContextCurrent(window)

glMatrixMode(UInt32(GL_PROJECTION))
glLoadIdentity()
glOrtho(0, 300, 300, 0, 1, -1)
glMatrixMode(UInt32(GL_MODELVIEW))

func loop(){
  glBegin(UInt32(GL_POLYGON))
  glVertex2f(50, 50)
  glVertex2f(50, 100)
  glVertex2f(100, 100)
  glVertex2f(100, 50)
  glEnd()
}

while glfwWindowShouldClose(window) == 0 {
  loop()
  glfwSwapBuffers(window)
  glfwPollEvents()
}
```
