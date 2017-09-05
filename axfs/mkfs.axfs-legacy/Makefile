INC = -I./
CFLAGS = -g $(INC) -O0

MKFSOBJS = mkfs.axfs.o

# These packages are required for rebuilding from source
# sudo apt-get install zlibc zlib1g zlib1g-dev

# sudo apt-get install zlibc:i386 zlib1g:i386 zlib1g-dev:i386

all:   mkfs.axfs

mkfs.axfs: $(MKFSOBJS)
	$(CC) $(CFLAGS) -o mkfs.axfs $(MKFSOBJS) -lz

mkfs.axfs.32: $(MKFSOBJS)
	$(CC) $(CFLAGS) -m32 -o mkfs.axfs.32 mkfs.axfs.c -lz

mkfs.axfs.64: $(MKFSOBJS)
	$(CC) $(CFLAGS) -m64 -o mkfs.axfs.64 mkfs.axfs.c -lz

clean_mkfs.axfs:
	rm -rf $(MKFSOBJS) mkfs.axfs

clean: clean_mkfs.axfs
	rm -rf *.c~ Makefile~
