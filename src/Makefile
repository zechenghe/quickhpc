CC=gcc
PROGRAM=quickhpc
PAPI_DIR=../../papi/src
LIBS_STATIC=${PAPI_DIR}/libpapi.a
OBJS=config.o
EXTERNAL_OBJS=${PAPI_DIR}/testlib/do_loops.o \
	 ${PAPI_DIR}/testlib/test_utils.o \
#	 ${PAPI_DIR}/testlib/dummy.o
INC=-I${PAPI_DIR} -I${PAPI_DIR} -I${PAPI_DIR}/testlib


all: config 
	${CC} ${DEBUG_FLAG} ${INC} -g -Wall ${PROGRAM}.c \
		${EXTERNAL_OBJS} \
		${LIBS_STATIC} \
		${OBJS} -o ../${PROGRAM}

debug: CC += -D_DEBUG
debug: all

config:
	${CC} ${INC} -g -c config.c

clean:
	-rm ../${PROGRAM}
	-rm ${OBJS}
