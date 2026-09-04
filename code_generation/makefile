
################################
# COMMANDS TO RUN THE FILES : make clean
#			 				  make
#			 			
################################


all: a.out
	
	./a.out < code_generation_test1.mc > code_generation_quads1.out
	@echo "Test File 1 Done. \n"
	./a.out < code_generation_test2.mc > code_generation_quads2.out
	@echo "Test File 2 Done. \n"
	./a.out < code_generation_test3.mc > code_generation_quads3.out
	@echo "Test File 3 Done. \n"
	./a.out < code_generation_test4.mc > code_generation_quads4.out
	@echo "Test File 4 Done. \n"
	./a.out < code_generation_test5.mc > code_generation_quads5.out
	@echo "Test File 5 Done. \n"

	@echo "\nAll Files Done. \n"

a.out: lex.yy.o y.tab.o translator_code_generation.o
	g++ -std=c++11 lex.yy.o y.tab.o translator_code_generation.o -lfl

translator_code_generation.o: translator_code_generation.cpp translator_code_generation.h
	g++ -std=c++11 -c translator_code_generation.h
	g++ -std=c++11 -c translator_code_generation.cpp

lex.yy.o: lex.yy.c
	g++ -std=c++11 -c lex.yy.c

y.tab.o: y.tab.c
	g++ -std=c++11 -c y.tab.c

lex.yy.c: code_generation.l y.tab.h translator_code_generation.h
	flex code_generation.l

y.tab.c: code_generation.y
	yacc -dtv code_generation.y -W

y.tab.h: code_generation.y
	yacc -dtv code_generation.y -W

clean:
	rm code_generation_quads1.out code_generation_quads2.out code_generation_quads3.out code_generation_quads4.out code_generation_quads5.out  lex.yy.c y.tab.c y.tab.h lex.yy.o y.tab.o translator_code_generation.o y.output a.out translator_code_generation.h.gch
	
