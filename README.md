# bmp
a basic bmp loader for little endian systems

# features
Supported files formats : 
 - 32 bits BGRX
 - 24 bits BGR
 - 16 bits X1B5G5R5
 - 8 bits indexed bitmaps
 - 4 bits indexed bitmaps
 - monochrome indexed bitmaps
 - RLE8
 - RLE4
 
/!\  BMP files containing bitmasks are not supported. 
 
 # using the library
 
 use the exemple below :
 
 ```c
 #include <stdlib.h>
 
 #include "bmp.h"
 
 void foo(char *filename)
 {
   int w, h;
   char *pixels;
   int res;
   
   /* load the bmp specified by filename and stores the datas in a freshly allocated buffer
      Note : pixels format is RGBA */
   res = loadBMP( filename, &pixels, &w, &h );
   if( res ) {
     printf("Error, could not load %s\n", filename);
     return;
   }
   
   /* do cool stuff with the pixels */
   
   free(pixels);
 }
 ```
