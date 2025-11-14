# Emscripten-HTML-Template
This project was originally made for my own use during a school project.

## What?

This is a simple .html template that you can inject to your Emscripten Web Applications. The .html file does the following things:
1. Disables the Emscripten Footer
2. Disables the in-site console
3. Hides the scrollbars
4. Makes the application fill the entire browser screen
5. Updates the application size during resize events
6. Adds a icon to the webapp using [Base64](https://www.base64-image.de/)
7. Makes it possible to access the canvas information via JavaScript

## How to HTML Inject?

To inject this .html file to your Emscripten Project, just add ``--shell-file "${CMAKE_CURRENT_SOURCE_DIR}/template.html"`` to your CMakeLists.txt

OR add ´´--shell-file template.html´´ to your emcc command.

## How to Access Module?

To access the width and height of your web app via EM_JS, write these functions to your C++ code:

´´EM_JS(int, canvas_get_width(), (), {
  return Module.canvas.width;
});´´

´´EM_JS(int, canvas_get_height(), (), {
  return Module.canvas.height;
});´´
