OUTPUT = libBasicMath.a
CC = g++
CFLAGS = -c -std=c++11 -Wall -O2

build: objs
	ar rs $(OUTPUT) *.o
objs:
	$(CC) $(CFLAGS) *.cpp	
clean:
	rm -rf *.o
	rm -rf $(OUTPUT)
	rm -rf *.a
		
#Additional information
time_string = $(shell date +$(1))
BUILD_DATE = $(call time_string,"%d/%m/%y")
BUILD_TIME = $(call time_string,"%H:%M:%S")
$(info Time: $(BUILD_DATE) $(BUILD_TIME))