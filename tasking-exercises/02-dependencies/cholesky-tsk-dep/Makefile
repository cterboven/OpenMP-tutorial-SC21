BIN_DIR=../bin
PROGRAM=$(BIN_DIR)/cholesky-tsk-dep

BLAS_HOME=/usr/lib/x86_64-linux-gnu/openblas/

CC=gcc
CFLAGS=-O3 -std=gnu99 -I$(BLAS_HOME)/include -fopenmp
LDFLAGS=-L$(BLAS_HOME) -lblas -llapack -llapacke -lpthread -lm -fopenmp
#VERBOSE=-DVERBOSE

all: $(PROGRAM) 

$(PROGRAM): cholesky.c 
	$(CC) $(CFLAGS) $(VERBOSE) -o $@ $^ $(LDFLAGS)

$(BIN_DIR): 
	mkdir $@

clean:
	rm -rf $(PROGRAM) *.o

wipe: clean
	rm -rf *.out *.err
