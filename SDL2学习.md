安装

```
sudo apt-get install libsdl2-2.0
sudo apt-get install libsdl2-dev
```

编译

```
gcc -o ABC ABC.c -lSDL2    #include<SDL/SDL.h>
gcc -o ABC ABC.c -lSDL2 -lSDL_image   #include<SDL/SDL_image.h>
gcc -o ABC ABC.c -lSDL2 -lSDL_ttf   #include<SDL/SDL_ttf.h>
```

