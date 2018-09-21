OUTPUT = app
CC = g++
CFLAGS = -c
LIB = $(shell pwd)/lib/
THIRDPARTYDIR = $(shell pwd)/3rdParty/
DYNAMICLIB = $(THIRDPARTYDIR)/*.so
BUY3RDPARTY ?= NO #Assgining the env BUY3RDPARTY to 'NO' and Enabling to check it by user (see more:https://www.gnu.org/software/make/manual/html_node/Setting.html#Setting)

build: 3rdPartyAuthentication main-obj
	$(CC) *.o $(DYNAMICLIB) -o $(OUTPUT)
main-obj:
	$(CC) $(CFLAGS) main.cpp
3rdPartyAuthentication:
	$(info Current BUY3RDPARTY variable value:'$(BUY3RDPARTY)')
ifeq ($(BUY3RDPARTY), YES)
	#build dynamic lib
	cd $(LIB); \
	make; \
	cp *.so $(THIRDPARTYDIR); \
	cp basicmath.h $(THIRDPARTYDIR)
	#end of building dynamic lib
else ifeq ($(BUY3RDPARTY), )
	# BUY3RDPARTY is undifined
	$(error You have to buy 3rdParty's API for building your source continously by the following command before make: export BUY3RDPARTY=YES)
else ifeq ($(BUY3RDPARTY), NO)
	$(info you're so fucking mean)		
	$(error You have to buy 3rdParty's API for building your source continously by the following command before make: export BUY3RDPARTY=YES)
endif
clean:
	rm -rf *.o
	rm -rf $(OUTPUT)
	rm -rf $(THIRDPARTYDIR)/*
	cd $(LIB); \
	make clean;
	./3rdPartyRule.sh

#note
#Checking env variable BUY3RDPARTY by doing command: export -p | grep BUY3RDPARTY
