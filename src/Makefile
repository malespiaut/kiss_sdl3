#CPP = clang++
#C = clang
CPP = g++
C = gcc

### 32 bit Windows

#LDFLAGS = -LC:\SDL2-2.0.8\i686-w64-mingw32\lib \
-LC:\SDL2_ttf-2.0.14\i686-w64-mingw32\lib \
-LC:\SDL2_image-2.0.3\i686-w64-mingw32\lib \
-lmingw32 -lSDL2main -lSDL2 -lSDL2_image -lSDL2_ttf \
-mwindows -m32 -march=i686
#CFLAGS = -IC:\SDL2-2.0.8\i686-w64-mingw32\include \
-IC:\SDL2-2.0.8\i686-w64-mingw32\include\SDL2 \
-IC:\SDL2_ttf-2.0.14\i686-w64-mingw32\include \
-IC:\SDL2_image-2.0.3\i686-w64-mingw32\include \
-Wall -c -std=c89 -m32 -march=i686
#BIN1 = example1.exe
#BIN2 = example2.exe

### 64 bit Windows

#LDFLAGS = -LC:\SDL2-2.0.8\x86_64-w64-mingw32\lib \
-LC:\SDL2_ttf-2.0.14\x86_64-w64-mingw32\lib \
-LC:\SDL2_image-2.0.3\x86_64-w64-mingw32\lib \
-lmingw32 -lSDL2main -lSDL2 -lSDL2_image -lSDL2_ttf \
-mwindows
#CFLAGS = -IC:\SDL2-2.0.8\x86_64-w64-mingw32\include \
-IC:\SDL2-2.0.8\x86_64-w64-mingw32\include\SDL2 \
-IC:\SDL2_ttf-2.0.14\x86_64-w64-mingw32\include \
-IC:\SDL2_image-2.0.3\x86_64-w64-mingw32\include \
-Wall -c -std=c89
#BIN1 = example1.exe
#BIN2 = example2.exe

### macOS

#LDFLAGS = -framework SDL2 -framework SDL2_ttf -framework SDL2_image
#CFLAGS = -I/Library/Frameworks/SDL2.framework/Headers \
-I/Library/Frameworks/SDL2_ttf.framework/Headers \
-I/Library/Frameworks/SDL2_image.framework/Headers \
-Wall -c -std=c89
#BIN1 = example1
#BIN2 = example2

### Linux

LDFLAGS = -lSDL2 -lSDL2_image -lSDL2_ttf
CFLAGS = -Wall -c -std=c89
BIN1 = example1
BIN2 = example2

all: $(BIN1) $(BIN2)

$(BIN1): example1.o widgets.o draw.o general.o \
posix.o
	$(C) $^ $(LDFLAGS) -o $@

$(BIN2): example2.o widgets.o draw.o general.o \
posix.o
	$(C) $^ $(LDFLAGS) -o $@

example1.o: example1.c
	$(C) $(CFLAGS) $^ -o $@

example2.o: example2.c
	$(C) $(CFLAGS) $^ -o $@

widgets.o: widgets.c
	$(C) $(CFLAGS) $^ -o $@

draw.o: draw.c
	$(C) $(CFLAGS) $^ -o $@

general.o: general.c
	$(C) $(CFLAGS) $^ -o $@

posix.o: posix.c
	$(C) $(CFLAGS) $^ -o $@

clean:
	rm *.o && rm $(BIN1) && rm $(BIN2)
#	del *.o
#	del $(BIN1)
#	del $(BIN2)

