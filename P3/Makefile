########################################################
CC=gcc
CFLAGS= -g -Wall -pedantic -ansi
EJS = p3_e1 p3_e2a p3_e2b
########################################################
OBJECTSP3E1 = p3_e1.o vertex.o delivery.o
OBJECTSP3E2A = p3_e1.o vertex.o delivery.o queue.o
OBJECTSP3E2B = p3_e2b.o queue.o graph.o stack.o vertex.o
########################################################

all: $(EJS) #clear

p3_e1: $(OBJECTSP3E1)
	$(CC) $(CFLAGS) -o p3_e1 $(OBJECTSP3E1) -L./ -lqueue

p3_e1.o: p3_e1.c delivery.h types.h queue.h vertex.h
	$(CC) $(CFLAGS) -c p3_e1.c

p3_e2a: $(OBJECTSP3E2A)
	$(CC) $(CFLAGS) -o p3_e2a $(OBJECTSP3E2A)

p3_e2b: $(OBJECTSP3E2B)
	$(CC) $(CFLAGS) -o p3_e2b $(OBJECTSP3E2B)

p3_e2b.o: p3_e2b.c types.h queue.h graph.h
	$(CC) $(CFLAGS) -c p3_e2b.c

vertex.o: vertex.c vertex.h types.h
	$(CC) $(CFLAGS) -c vertex.c

delivery.o: delivery.c delivery.h types.h queue.h
	$(CC) $(CFLAGS) -c delivery.c

queue.o: queue.c queue.h types.h
	$(CC) $(CFLAGS) -c queue.c

graph.o: graph.c graph.h vertex.h types.h stack.h queue.h
	$(CC) $(CFLAGS) -c graph.c

stack.o: stack.c stack.h
	$(CC) $(CFLAGS) -c stack.c

.PHONY: clear clean run runv

clear:
	rm -rf *.o 

clean:
	rm -rf *.o $(EJS)

run1:
	@echo ">>>>>>Running p3_e1"
	./p3_e1 requests.txt
	
run1v:
	@echo ">>>>>>Running p3_e1 with valgrind"
	valgrind --leak-check=full ./p3_e1 requests.txt
	
run2a:
	@echo ">>>>>>Running p3_e2a"
	./p3_e2a requests.txt
	
run2av:
	@echo ">>>>>>Running p3_e2a with valgrind"
	valgrind --leak-check=full ./p3_e2a requests.txt

run2b:
	@echo ">>>>>>Running p3_e2b"
	./p3_e2b city_graph.txt 100 700
	
run2bv:
	@echo ">>>>>>Running p3_e2a with valgrind"
	valgrind --leak-check=full ./p3_e2b city_graph.txt 100 700