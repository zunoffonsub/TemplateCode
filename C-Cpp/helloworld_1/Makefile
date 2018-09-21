OUTPUT = app
CC = g++
CFLAGS = -c

build: main-obj
	$(CC) *.o -o $(OUTPUT)
main-obj:
	$(CC) $(CFLAGS) main.cpp
clean:
	rm -rf *.o
	rm -rf $(OUTPUT)