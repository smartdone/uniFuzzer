cmake_minimum_required(VERSION 2.6)

add_library(elfLoader STATIC
    arm.c  
    arm.h 
    common.h  
    dl-defs.h  
    dl-elf.h  
    dl-hash.c  
    dl-hash.h  
    dl-string.h  
    elfLoader.c  
    elfLoader.h  
    i386.c  
    i386.h  
    mips.c  
    mips.h
)