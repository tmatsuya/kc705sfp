
all: runs/top.runs/impl_1/top.bit 

gui:
	vivado -source kc705sfp_gui.tcl

load: runs/top.runs/impl_1/top.bit 
	./xprog.sh load

flash: runs/top.runs/impl_1/top.mcs 
	./xprog.sh flash

runs/top.runs/impl_1/top.bit:
	vivado -mode batch -source  kc705sfp_batch.tcl 

runs/top.runs/impl_1/top.mcs: runs/top.runs/impl_1/top.bit
	./xprog.sh mcs

clean:
	rm -fr runs vivado*jou vivado*log

.PHONY: clean gui load flash
