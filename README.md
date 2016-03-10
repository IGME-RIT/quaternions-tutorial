# Marching Cubes Tutorial

Builds upon the [Improved3D]() project by introducing Quaternions.

# About

Builds upon the "Improved3D" project by introducing Quaternions. Euler angles are basically just 3 rotations stored about the X, Y, and Z axes. Quaternions are faster than Euler angles, so use them! Euler angles are more intuitive, so use those for user interface. Quaternions are a set of 4 numbers [x, y, z, w] that represent rotations as such:

```cpp
x = RotationAxis.x * sin(RotationAngle / 2)
y = RotationAxis.y * sin(RotationAngle / 2)
z = RotationAxis.z * sin(RotationAngle / 2)
w = cos(RotationAngle / 2)

glm::quat q; // Creates an identity quaternion
q = glm::quat(w, x, y, z); // Specify the direct components, you almost never do this
q = glm::quat(vec3(90, 45, 0)) convert from Euler angles (in radians) to Quaternion
q = glm::angleAxis(AngleInRadians, RotationAxis); // Convert from axis-angle

mat4 RotationMatrix = glm::toMat4(q); // Convert from glm::quat to glm::mat4.
```

# Setup

In order to setup, run the following in a shell, then open the project in your preferred editor. Windows setup has been configured for use with Visual Studio.

Windows:
```
cd path/to/folder
setup.cmd
```
Linux:
```
cd path/to/folder
./setup
```
