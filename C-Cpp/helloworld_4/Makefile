OUTPUT = app
CC = g++
CFLAGS = -c -std=c++11 -Wall -O2
PROJ = $(shell pwd)
LIB = $(PROJ)/lib/

build: mainobj libobj
	$(CC) *.o -o $(OUTPUT)
mainobj:
	$(CC) $(CFLAGS) main.cpp	
libobj:
	cd $(LIB); \
	$(CC) $(CFLAGS) *.cpp; \
	mv *.o $(PROJ);
	# for dir in $(LIB); do \
	# 	cd $$dir; \
	# 	$(CC) $(CFLAGS) *.cpp; \
	# 	mv *.o $(PROJ); \
	# done 
clean:
	rm -rf *.o
	rm -rf $(OUTPUT)
		
#Additional information
time_string = $(shell date +$(1))
BUILD_DATE = $(call time_string,"%d/%m/%y")
BUILD_TIME = $(call time_string,"%H:%M:%S")
$(info Time: $(BUILD_DATE) $(BUILD_TIME))