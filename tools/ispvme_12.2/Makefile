CC = gcc
AR = ar
CFLAGS = -Wall -W -Wunused -lpthread -g -O2 -ggdb
LFLAGS = -lm -pthread
DEL_FILE = rm -f
MV_FILE = mv -f
OBJ_FILE_NODE = ./*.o
#VPATH = 
INCPATH     =     -I../include/
TARGET   = ispvm
TARGET-DB   = ispvm-db

OBJECTS += hardware.o ispvm_ui.o ivm_core.o

all: $(TARGET)

debug: CFLAGS += -DVME_DEBUG
debug: TARGET = $(TARGET-DB)
debug: $(TARGET)
	
.c.o:
	$(CC) -c $(CFLAGS) $(INCPATH) -o $@ $<

$(TARGET):$(OBJECTS)
	$(CC) $(LFLAGS) -o $(TARGET) $(OBJECTS)

clean:
	-$(DEL_FILE) $(TARGET) $(TARGET-DB)
	-$(DEL_FILE) $(OBJ_FILE_NODE)


