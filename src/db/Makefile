include ../../build_config.mk

OBJS = ssdb_impl.o iterator.o options.o \
		t_kv.o t_hash.o t_zset.o t_list.o t_table.o \
		binlog.o ttl.o rubbish_release.o monitor_thread.o
	
LIBS = ../util/libutil.a


all: libdb.a 

libdb.a: ${OBJS}
	ar -cru ./libdb.a ${OBJS}

ssdb_impl.o: ssdb.h ssdb_impl.h ssdb_impl.cpp
	${CXX} ${CFLAGS} -c ssdb_impl.cpp
iterator.o: ssdb.h iterator.h iterator.cpp
	${CXX} ${CFLAGS} -c iterator.cpp
options.o: ssdb.h options.h options.cpp
	${CXX} ${CFLAGS} -c options.cpp
t_kv.o: ssdb.h t_kv.h t_kv.cpp
	${CXX} ${CFLAGS} -c t_kv.cpp
t_hash.o: ssdb.h t_hash.h t_hash.cpp
	${CXX} ${CFLAGS} -c t_hash.cpp
t_zset.o: ssdb.h t_zset.h t_zset.cpp
	${CXX} ${CFLAGS} -c t_zset.cpp
t_list.o: ssdb.h t_list.h t_list.cpp
	${CXX} ${CFLAGS} -c t_list.cpp
t_table.o: ssdb.h t_table.h t_table.cpp
	${CXX} ${CFLAGS} -c t_table.cpp
binlog.o: ssdb.h binlog.h binlog.cpp
	${CXX} ${CFLAGS} -c binlog.cpp
ttl.o: ssdb.h ttl.h ttl.cpp
	${CXX} ${CFLAGS} -c ttl.cpp
monitor_thread.o: ssdb.h monitor_thread.h monitor_thread.cpp
	${CXX} ${CFLAGS} -c monitor_thread.cpp
rubbish_release.o: ssdb.h rubbish_release.h rubbish_release.cpp
	${CXX} ${CFLAGS} -c rubbish_release.cpp

test:
	${CXX} -o test.out test.cpp ${OBJS} ${CFLAGS} ${LIBS} ${CLIBS}

clean:
	rm -f ${EXES} *.o *.exe *.a

