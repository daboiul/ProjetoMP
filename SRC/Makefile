IDIR =../include
CXX=g++
CXXFLAGS=-I$(IDIR) -g -D_TEST -ftest-coverage -fprofile-arcs

ODIR=../obj
LDIR=../lib

LIBS= -lgtest -lpthread -lgtest_main -lcurses --coverage -lgcov

_DEPS= grafo.h
DEPS= $(patsubst %,$(IDIR)/%,$(_DEPS))

_OBJ= main.o MyNetwork.o 
OBJ= $(patsubst %,$(ODIR)/%,$(_OBJ))


$(ODIR)/%.o: %.c $(DEPS)
	$(CXX) -c -o $@ $< $(CXXFLAGS) $(LIBS)

main: $(OBJ)
	$(CXX) -o $@ $^ $(CXXFLAGS) $(LIBS)

.PHONY: clean

clean:
	rm -f $(ODIR)/*.o *~ core $(IDIR)/*~ 
