include ../../build_config.mk

all: demo hello-ssdb

demo: demo.cpp libssdb-client.a
	${CXX} -o demo demo.cpp libssdb-client.a

hello-ssdb: hello-ssdb.cpp libssdb-client.a
	${CXX} -o hello-ssdb hello-ssdb.cpp libssdb-client.a

SSDB_impl.o: SSDB_client.h SSDB_impl.h SSDB_impl.cpp
	${CXX} -I../ ${CFLAGS} -c SSDB_impl.cpp

libssdb-client.a: SSDB_impl.o ../util/bytes.o ../net/link.o 
	ar -cru libssdb-client.a\
		SSDB_impl.o\
		../util/bytes.o\
		../net/link.o
	cp SSDB_client.h libssdb-client.a ../../api/cpp

clean:
	rm -f demo hello-ssdb *.a *.o

