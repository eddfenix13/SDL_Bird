SDLFLAGS := $(shell sdl2-config --libs --cflags)

all:flappyCliente flappy server

server:SocketDatagrama.o PaqueteDatagrama.o
	g++ serverFlappy.cpp SocketDatagrama.o PaqueteDatagrama.o -o server

flappyCliente: Game.o
	g++ flappyCliente2.cpp Game.o $(SDLFLAGS) -o flappyCliente

Game.o: Game.cpp Game.h SocketDatagrama.o PaqueteDatagrama.o
	g++ Game.cpp SocketDatagrama.o PaqueteDatagrama.o -c

#flappyServidor:SocketDatagrama.o PaqueteDatagrama.o
#	g++ flappyServidor.cpp SocketDatagrama.o PaqueteDatagrama.o $(SDLFLAGS) -o flappyServidor

flappy: SocketDatagrama.o PaqueteDatagrama.o
	g++ flappy.cpp $(SDLFLAGS) -o flappy

SocketDatagrama.o: SocketDatagrama.cpp SocketDatagrama.h
	g++ SocketDatagrama.cpp -c 

PaqueteDatagrama.o: PaqueteDatagrama.cpp PaqueteDatagrama.h
	g++ PaqueteDatagrama.cpp -c

clean:
	rm *.o flappy flappyCliente flappyServidor server
