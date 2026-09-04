a.out: lex.yy.c
	gcc lex.yy.c lexical_analyzer.c

lex.yy.c: lexi.l
	flex lexi.l 

clean: 
	rm a.out 
	rm -f lex.yy.c
	rm output.txt

run: 
	./a.out test.nc > output.txt