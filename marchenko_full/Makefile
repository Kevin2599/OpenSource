# Makefile

include ../Make_include

LIBS    += -L$L -lgenfft -lm $(LIBSM)
#OPTC += -g -O0 -Wall 

#ALL: fmute marchenko marchenko2

ALL: fmute marchenko_full

SRCJ	= fmute.c \
		getFileInfo.c  \
		readData.c \
		applyMute.c \
		writeData.c \
		wallclock_time.c \
		verbosepkg.c  \
		atopkge.c \
		docpkge.c \
		getpars.c

SRCH	= marchenko.c \
		getFileInfo.c  \
		readData.c \
		readShotData.c \
		readTinvData.c \
		applyMute.c \
		writeData.c \
		writeDataIter.c \
		wallclock_time.c \
		name_ext.c  \
		verbosepkg.c  \
		atopkge.c \
		docpkge.c \
		getpars.c \
		readSnapData.c \
		Cost.c \
		AmpEst.c \
		freqwave.c \
		getParameters.c \
		getModelInfo.c \
		recvPar.c \
		raytime.c \
		readModel.c \
		JespersRayTracer.c \
		getWaveletHeaders.c \
		getWaveletInfo.c \
		writeSrcRecPos.c \
		writesufile.c \
		gaussGen.c \
		threadAffinity.c

OBJJ	= $(SRCJ:%.c=%.o)

fmute:	$(OBJJ) 
	$(CC) $(LDFLAGS) $(OPTC) $(CFLAGS) -o fmute $(OBJJ) $(LIBS)

OBJH	= $(SRCH:%.c=%.o)

marchenko_full:	$(OBJH) raytime.h
	$(CC) $(LDFLAGS) $(OPTC) $(CFLAGS) -o marchenko_full $(OBJH) $(LIBS)

install: fmute marchenko_full
	cp fmute $B
	cp marchenko_full $B

#	cp marchenko2 $B

clean:
		rm -f core fmute $(OBJJ) marchenko_full $(OBJH)

realclean: clean
		rm -f $B/fmute $B/marchenko_full




