CC ?= clang
CFLAGS := -std=c89 -Wall -Wno-visibility -I. -Igen -DEMACS=1 -DVI=1 $(CFLAGS)

ifndef NO_SMALL
CFLAGS := -DSMALL=1 $(CFLAGS)
endif

LIBS := -lcurses $(LIBS)

TARGET = ksh
TARGETS = \
            alloc.o \
            c_ksh.o \
            c_sh.o \
            c_test.o \
            c_ulimit.o \
            edit.o \
            emacs.o \
            eval.o \
            exec.o \
            expr.o \
            history.o \
            io.o \
            jobs.o \
            lex.o \
            mail.o \
            main.o \
            misc.o \
            path.o \
            shf.o \
            syn.o \
            table.o \
            trap.o \
            tree.o \
            tty.o \
            var.o \
            version.o \
            vi.o

all: $(TARGET)

$(TARGET): $(TARGETS)
	$(CC) $(LDFLAGS) -o $(TARGET) $(TARGETS) $(LIBS)

$(TARGETS):
	$(CC) -c -o "$@" $(CFLAGS) "$(patsubst %.o,%.c,$@)"

clean: distclean

distclean:
	-rm -rf *.dSYM
	-rm -f $(TARGET) $(TARGETS)
