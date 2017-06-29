include ../build_config.mk

OBJS += ../src/net/link.o ../src/net/fde.o ../src/util/log.o ../src/util/bytes.o
CFLAGS += -I../src
EXES = carrydb-bench carrydb-dump carrydb-repair leveldb-import carrydb-migrate

all: ${EXES}

carrydb-bench: carrydb-bench.o ${OBJS} ${UTIL_OBJS} 
	${CXX} -o carrydb-bench carrydb-bench.o ${OBJS} ${UTIL_OBJS} ${CLIBS}
carrydb-dump: carrydb-dump.o ${OBJS} ${UTIL_OBJS} 
	${CXX} -o carrydb-dump carrydb-dump.o ${OBJS} ${UTIL_OBJS} ${CLIBS}
carrydb-repair: carrydb-repair.o ${OBJS} ${UTIL_OBJS} 
	${CXX} -o carrydb-repair carrydb-repair.o ${OBJS} ${UTIL_OBJS} ${CLIBS}
leveldb-import: leveldb-import.o ${OBJS} ${UTIL_OBJS} 
	${CXX} -o leveldb-import leveldb-import.o ${OBJS} ${UTIL_OBJS} ${CLIBS}
carrydb-migrate: carrydb-migrate.o ../api/cpp/libssdb-client.a ../src/util/libutil.a
	${CXX} -o carrydb-migrate carrydb-migrate.o ../api/cpp/libssdb-client.a ../src/util/libutil.a

carrydb-migrate.o: carrydb-migrate.cpp
	${CXX} ${CFLAGS} -I../api/cpp -c carrydb-migrate.cpp
carrydb-bench.o: carrydb-bench.cpp
	${CXX} ${CFLAGS} -c carrydb-bench.cpp
carrydb-dump.o: carrydb-dump.cpp
	${CXX} ${CFLAGS} -c carrydb-dump.cpp
carrydb-repair.o: carrydb-repair.cpp
	${CXX} ${CFLAGS} -c carrydb-repair.cpp
leveldb-import.o: leveldb-import.cpp
	${CXX} ${CFLAGS} -c leveldb-import.cpp

clean:
	rm -f *.exe *.exe.stackdump *.o ${EXES}
	rm -rf _cpy_

