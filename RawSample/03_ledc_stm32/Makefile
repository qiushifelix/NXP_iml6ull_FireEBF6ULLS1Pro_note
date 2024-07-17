MY_SRC ?=$(shell pwd)
TOP_DIR = $(MY_SRC)/..
include $(TOP_DIR)/make_none_eabi.include
objs := start.o main.o

ledcStm32.bin:$(objs)
	$(LINKER) -Timx6ul.lds -o ledc.elf $^
	$(OBJCOPY) -O binary -S ledc.elf $@
	$(OBJDUMP) -D -m arm ledc.elf > ledc.dis

%.o:%.s
	$(COMPILER) -Wall -nostdlib -c -O2 -o $@ $<
	
%.o:%.S
	$(COMPILER) -Wall -nostdlib -c -O2 -o $@ $<
	
%.o:%.c
	$(COMPILER) -Wall -nostdlib -c -O2 -o $@ $<
	
clean:
	rm -rf *.o ledc.bin ledc.elf ledc.dis
	
	
