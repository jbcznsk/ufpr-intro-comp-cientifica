       PROG   = matmult

           CC = gcc -std=c11 -g
         OBJS = matriz.o

       CFLAGS = -DLIKWID_PERFMON -I /usr/local/include -L /usr/bin/lib -llikwid -O3 -mavx2 -march=native
       LFLAGS = -lm

.PHONY: all debug clean limpa purge faxina

%.o: %.c %.h
	$(CC) $(CFLAGS) -c $<

all: $(PROG)

debug:         CFLAGS += -DDEBUG
debug:         $(PROG)

$(PROG):  $(PROG).o

$(PROG): $(OBJS) 
	$(CC) $(CFLAGS) -o $@ $^ $(LFLAGS)

clean limpa:
	@echo "Limpando ...."
	@rm -f *~ *.bak *.tmp

purge faxina:   clean
	@echo "Faxina ...."
	@rm -f  $(PROG) *.o core a.out
	@rm -f *.png marker.out *.log
