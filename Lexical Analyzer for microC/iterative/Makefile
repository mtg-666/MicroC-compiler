a.out: lex.yy.c
	gcc lex.yy.c -lfl

lex.yy.c: a6it_220101106.l 
	flex a6it_220101106.l 

clean: 
	rm a.out 
	rm -f lex.yy.c
	rm output.txt

run: 
	./a.out a6_220101106_test.mc > output.txt