######################################################################
#  librtos.a
######################################################################

TGT_CFLAGS      += -I./include
TGT_CXXFLAGS    += -I./include

CFLAGS		+= -Wno-redundant-decls

SRCFILES        = src/croutine.c src/event_groups.c src/list.c src/port.c src/queue.c src/stream_buffer.c src/tasks.c src/timers.c

TEMP1           = $(patsubst %.c,%.o,$(SRCFILES))
TEMP2           = $(patsubst %.asm,%.o,$(TEMP1))
OBJS            = $(patsubst %.cpp,%.o,$(TEMP2))

lib/librtos.a: $(OBJS)
	@rm -f lib/librtos.a
	$(AR) rv lib/librtos.a $(OBJS)

clean:
	rm -f src/*.o

clobber: clean
	rm -f lib/librtos.a

include ../Makefile.incl

# End Makefile
