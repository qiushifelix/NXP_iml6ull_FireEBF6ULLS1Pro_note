objs := start.o main.o

ledc.bin:$(objs)
	arm-none-eabi-ld -Timx6ul.lds -o ledc.elf $^
	arm-none-eabi-objcopy -O binary -S ledc.elf $@
	arm-none-eabi-objdump -D -m arm ledc.elf > ledc.dis
	
%.o:%.s
	arm-none-eabi-gcc -c -o $@ $<
	
%.o:%.S
	arm-none-eabi-gcc -c -o $@ $<
	
%.o:%.c
	arm-none-eabi-gcc -c -o $@ $<
	
clean:
	rm -rf *.o ledc.bin ledc.elf ledc.dis
	
	
