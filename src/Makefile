objs = intset.o sds.o  endian.o  zmalloc.o  zipmap.o lzf_c.o lzf_d.o util.o ziplist.o rdb_parser.o main.o rediscounter.o aof.o
CC = gcc
CFLAGS = -g -std=c99 -pedantic -Wall -W -fPIC
all: $(objs) 
	@echo "--------------------------compile start here---------------------------------"
	$(CC) $(CFLAGS) -o rdb-tool $(objs) -lm
	@echo "--------------------------compile  end  here---------------------------------"

crc64.o: crc64.c
endian.o: endian.c
intset.o: intset.c intset.h zmalloc.h endian.h
lzf_c.o: lzf_c.c lzfP.h
lzf_d.o: lzf_d.c lzfP.h
main.o: main.c main.h zmalloc.h sds.h fmacros.h intset.h ziplist.h \
 zipmap.h lzf.h rdb_parser.h rediscounter.h aof.h
rdb_parser.o: rdb_parser.c rdb_parser.h main.h zmalloc.h sds.h fmacros.h \
 intset.h ziplist.h zipmap.h lzf.h crc64.c util.h
sds.o: sds.c sds.h zmalloc.h
util.o: util.c fmacros.h main.h zmalloc.h sds.h intset.h ziplist.h \
 zipmap.h lzf.h
ziplist.o: ziplist.c zmalloc.h util.h main.h sds.h fmacros.h intset.h \
 ziplist.h zipmap.h lzf.h endian.h
zipmap.o: zipmap.c zmalloc.h endian.h
zmalloc.o: zmalloc.c config.h zmalloc.h
rediscounter.o: rediscounter.c rediscounter.h sds.h zmalloc.h main.h aof.h
aof.o: aof.h aof.c main.h
clean:
	-rm *.o rdb-tool
