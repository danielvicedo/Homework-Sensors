# webcam_capture
Just webcam capture

## Tips
https://wiki.archlinux.org/index.php/webcam_setup

http://www.linuxintro.org/wiki/Set_up_a_Webcam_with_Linux


# Step by Step procedure
1. Create a new folder where you will put all the contents of the project
2. Create a new CMakeLists.txt
3. Write down the following parameters in the .txt: (without the initial hyphens)
      - #indicate minimum version
      - CMAKE_MINIMUM_REQUIRED(VERSION 2.6)
      - #project name
      - PROJECT(webcam_capture)
      - #find required packages (look for the package, usually  at /usr/share/cmake-2.8/Modules/ or
      - /usr/share/)
      - FIND_PACKAGE(OpenCV REQUIRED)
      - #set header directories
      - INCLUDE_DIRECTORIES(${OpenCV_INCLUDE_DIR})
      - #Create an executable
      - ADD_EXECUTABLE(${PROJECT_NAME} webcam_capture.cpp)
      - #Link with libraries
      - TARGET_LINK_LIBRARIES(${PROJECT_NAME} ${OpenCV_LIBS})
      - #Setting this prefix will be used by INSTALL commands in next CMakeLists
      - SET(CMAKE_INSTALL_PREFIX /usr/local)
      - #install
      - INSTALL(TARGETS ${PROJECT_NAME} RUNTIME DESTINATION bin)

4. Go to the console and write the following instructions (##"are comments that don't need to be written"):
  - cd webcam_capture_folder  ##"webcam_capture_folder" is the folder's name
  - mkdir build ##create a new folder called build
  - cd build ##change directory into the folder
  - cmake .. ##execute cmake to the folder above, in this case webcam_capture_folder
  - make ##create the executable for your code
  - ./webcam_capture ##execute your code

#To close the webcam_capture press CONTROL+C in the console.


# How to upload images into a README.md

1. Search for the Markdown Cheat Sheet
2. Upload your photo to your repository via commit and push
3. Use ![ScreenShot]("link to your photo")
4. To get the link, go the GitHub, found your photo, right click on it and open it in a new tab. Copy the URL from the new tab.

![ScreenShot](https://raw.githubusercontent.com/danielvicedo/CMake-tutorial/master/webcam_capture/media/Webcam_capture.png)
