MY_SRC ?=$(shell pwd)
TOP_DIR = $(MY_SRC)/..
include $(TOP_DIR)/make.include
led.bin:led.s
	$(COMPILER) -g -c led.s -o led.o
	$(LINKER) -Ttext 0x0090F800 led.o -o led.elf
	$(OBJCOPY) -O binary -S -g led.elf led.bin
	$(OBJDUMP) -D led.elf > led.dis
clean:
	rm -rf *.o led.bin led.elf led.dis