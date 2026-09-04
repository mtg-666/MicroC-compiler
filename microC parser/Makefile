# Makefile for micro C parser

CC = gcc
CFLAGS = -Wall -g

all: parser

parser: lex.yy.c y.tab.c
	$(CC) $(CFLAGS) -o parser lex.yy.c y.tab.c -lfl 

lex.yy.c: microC parser.l y.tab.h
	flex microC parser.l

y.tab.c y.tab.h: microC parser.y
	yacc -d microC parser.y

clean:
	rm -f parser lex.yy.c y.tab.c y.tab.h output.txt
	
test: parser
	./parser < microC parser_test.mc > output.txt