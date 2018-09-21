OUTPUT = app
CC = g++
CFLAGS = -c -std=c++11 -Wall -O2

build: main-obj hello-obj
	$(CC) *.o -o $(OUTPUT)
main-obj:
	$(CC) $(CFLAGS) main.cpp
hello-obj:
	$(CC) $(CFLAGS) hello.cpp	
clean:
	rm -rf *.o
	rm -rf $(OUTPUT)

#Additional information
time_string = $(shell date +$(1))
BUILD_DATE = $(call time_string,"%d/%m/%y")
BUILD_TIME = $(call time_string,"%H:%M:%S")
$(info Time: $(BUILD_DATE) $(BUILD_TIME))