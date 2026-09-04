CC = gcc
YACC = bison
LEX = flex

all: $(code_generation)

$(code_generation): $(code_generation).tab.c lex.yy.c
	$(CC) -o $@ $^ -lm

$(code_generation).tab.c $(code_generation).tab.h: $(code_generation).y
	$(YACC) -d $<

lex.yy.c: $(code_generation).l $(code_generation).tab.h
	$(LEX) $<

clean:
	rm -f $(code_generation) lex.yy.c $(code_generation).tab.c $(code_generation).tab.h

test: $(code_generation)
	./$(code_generation)
