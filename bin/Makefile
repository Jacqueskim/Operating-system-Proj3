# Use normal make for this Makefile
#
# Makefile for:
#	coff2noff -- converts a normal MIPS executable into a Nachos executable
#	disassemble -- disassembles a normal MIPS executable 
#
# Copyright (c) 1992 The Regents of the University of California.
# All rights reserved.  See copyright.h for copyright notice and limitation 
# of liability and disclaimer of warranty provisions.

# If the host is big endian (SPARC, SNAKE, etc):
# change to (disassemble and coff2flat don't support big endian yet):

CC=gcc -m32 -w
# UCSD uAPE (Sparc/Solaris)
# CFLAGS= -I./ -I../threads -DHOST_IS_BIG_ENDIAN
# UCSD OSTL (Linux)
# CFLAGS=-I./ -I../threads -g
CFLAGS = $(CSE120_CFLAGS) $(CSE120_HOST)

LD=gcc -m32

all: coff2noff

# converts a COFF file to Nachos object format
coff2noff: coff2noff.o
	$(LD) coff2noff.o -o coff2noff

# converts a COFF file to a flat address space (for Nachos version 2)
coff2flat: coff2flat.o
	$(LD) coff2flat.o -o coff2flat

# dis-assembles a COFF file
disassemble: out.o opstrings.o
	$(LD) out.o opstrings.o -o disassemble

%.o: %.c *.h
	@ echo $<
	$(CC) $< -c -o $@
