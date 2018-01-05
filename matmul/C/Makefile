ifndef CC
	CC = gcc
endif

CCFLAGS=-O3 -std=c99 -ffast-math

LIBS = -lm -lOpenCL -fopenmp

COMMON_DIR = ../../C_common

MMUL_OBJS = wtime.o
EXEC = mult

CCFLAGS+=-L$(OPENCL_ROOT)/lib/x86_64


all: $(EXEC)

mult: $(MMUL_OBJS) matmul.c matrix_lib.c
	$(CC) $^ $(CCFLAGS) $(LIBS) -I $(COMMON_DIR) -I $(OPENCL_ROOT)/include -o $(EXEC)

wtime.o: $(COMMON_DIR)/wtime.c
	$(CC) -c $^ $(CCFLAGS) -o $@

.c.o:
	$(CC) -c $< $(CCFLAGS) -o $@


clean:
	rm -f $(MMUL_OBJS) $(EXEC)
