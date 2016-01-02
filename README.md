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
