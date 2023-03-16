#Makefile for UVM Testbench
RTL= ../rtl/*
work= work #library name
SVTB1= ../tb/top.sv
INC = +incdir+../tb +incdir+../test +incdir+../wr_agt_top +incdir+../rd_agt_top
SVTB2 = ../test/ram_test_pkg.sv
VSIMOPT= -vopt -voptargs=+acc 
VSIMCOV= -coverage -sva 
VSIMBATCH1= -c -do  " log -r /* ;coverage save -onexit mem_cov1;run -all; exit"
VSIMBATCH2= -c -do  " log -r /* ;coverage save -onexit mem_cov2;run -all; exit"
VSIMBATCH3= -c -do  " log -r /* ;coverage save -onexit mem_cov3;run -all; exit"
VSIMBATCH4= -c -do  " log -r /* ;coverage save -onexit mem_cov4;run -all; exit"
VSIMBATCH5= -c -do  " log -r /* ;coverage save -onexit mem_cov5;run -all; exit"
VSIMBATCH6= -c -do  " log -r /* ;coverage save -onexit mem_cov6;run -all; exit"
VSIMBATCH7= -c -do  " log -r /* ;coverage save -onexit mem_cov7;run -all; exit"
VSIMBATCH8= -c -do  " log -r /* ;coverage save -onexit mem_cov8;run -all; exit"


help:
	@echo =============================================================================================================
	@echo "! USAGE   	--  make target                             											!"
	@echo "! clean   	=>  clean the earlier log and intermediate files.       								!"
	@echo "! sv_cmp    	=>  Create library and compile the code.                   								!"
	@echo "! run_sim    =>  run the simulation in batch mode.                   								!"
	@echo "! run_test	=>  clean, compile & run the simulation for ram_signle_adddr_test in batch mode.		!" 
	@echo "! run_test1	=>  clean, compile & run the simulation for ram_ten_adddr_test in batch mode.			!" 
	@echo "! run_test2	=>  clean, compile & run the simulation for ram_odd_adddr_test in batch mode.			!"
	@echo "! run_test3	=>  clean, compile & run the simulation for ram_even_adddr_test in batch mode.		    !" 
	@echo "! run_test4	=>  clean, compile & run the simulation for ram_d1_adddr_test in batch mode.		    !" 
	@echo "! run_test5	=>  clean, compile & run the simulation for ram_d2_adddr_test in batch mode.		    !" 
	@echo "! run_test6	=>  clean, compile & run the simulation for ram_d3_adddr_test in batch mode.		    !" 
	@echo "! run_test7	=>  clean, compile & run the simulation for ram_d4_adddr_test in batch mode.		    !" 
	@echo "! view_wave1 =>  To view the waveform of ram_signle_addr_test	    								!" 
	@echo "! view_wave2 =>  To view the waveform of ram_ten_addr_test	    									!" 
	@echo "! view_wave3 =>  To view the waveform of ram_odd_addr_test	  	  									!" 
	@echo "! view_wave4 =>  To view the waveform of ram_even_addr_test	    									!" 
	@echo "! view_wave5 =>  To view the waveform of ram_d1_addr_test	    									!" 
	@echo "! view_wave6 =>  To view the waveform of ram_d2_addr_test	    									!" 
	@echo "! view_wave7 =>  To view the waveform of ram_d3_addr_test	    									!" 
	@echo "! view_wave8 =>  To view the waveform of ram_d4_addr_test	    									!" 
	@echo "! regress    =>  clean, compile and run all testcases in batch mode.		    						!"
	@echo "! report     =>  To merge coverage reports for all testcases and  convert to html format.			!"
	@echo "! cov        =>  To open merged coverage report in html format.										!"
	@echo ====================================================================================================================

sv_cmp:
	vlib $(work)
	vmap work $(work)
	vlog -work $(work) $(RTL) $(INC) $(SVTB2) $(SVTB1) 	
	
run_test:sv_cmp
	vsim -cvgperinstance $(VSIMOPT) $(VSIMCOV) $(VSIMBATCH1)  -wlf wave_file1.wlf -l test1.log  -sv_seed 211284296  work.top +UVM_TESTNAME=ram_single_addr_test
	vcover report  -cvg  -details -nocompactcrossbins -codeAll -assert -directive -html mem_cov1

	
run_test1:
	vsim -cvgperinstance $(VSIMOPT) $(VSIMCOV) $(VSIMBATCH2)  -wlf wave_file2.wlf -l test2.log  -sv_seed 2188454115  work.top +UVM_TESTNAME=ram_ten_addr_test
	vcover report  -cvg  -details -nocompactcrossbins -codeAll -assert -directive -html mem_cov2
	
run_test2:
	vsim -cvgperinstance $(VSIMOPT) $(VSIMCOV) $(VSIMBATCH3)  -wlf wave_file3.wlf -l test3.log  -sv_seed 4191235037  work.top +UVM_TESTNAME=ram_even_addr_test
	vcover report  -cvg  -details -nocompactcrossbins -codeAll -assert -directive -html mem_cov3
	
run_test3:
	vsim -cvgperinstance $(VSIMOPT) $(VSIMCOV) $(VSIMBATCH4)  -wlf wave_file4.wlf -l test4.log  -sv_seed 74162865  work.top +UVM_TESTNAME=ram_odd_addr_test
	vcover report  -cvg  -details -nocompactcrossbins -codeAll -assert -directive -html mem_cov4
	
run_test4:
	vsim -cvgperinstance $(VSIMOPT) $(VSIMCOV) $(VSIMBATCH5)  -wlf wave_file5.wlf -l test5.log  -sv_seed 19557163  work.top +UVM_TESTNAME=ram_d1_addr_test
	vcover report  -cvg  -details -nocompactcrossbins -codeAll -assert -directive -html mem_cov5
	
run_test5:
	vsim -cvgperinstance $(VSIMOPT) $(VSIMCOV) $(VSIMBATCH6)  -wlf wave_file6.wlf -l test6.log  -sv_seed 489318164  work.top +UVM_TESTNAME=ram_d2_addr_test
	vcover report  -cvg  -details -nocompactcrossbins -codeAll -assert -directive -html mem_cov6

run_test6:
	vsim -cvgperinstance $(VSIMOPT) $(VSIMCOV) $(VSIMBATCH7)  -wlf wave_file7.wlf -l test7.log  -sv_seed 2926207538  work.top +UVM_TESTNAME=ram_d3_addr_test
	vcover report  -cvg  -details -nocompactcrossbins -codeAll -assert -directive -html mem_cov7

run_test7:
	vsim -cvgperinstance $(VSIMOPT) $(VSIMCOV) $(VSIMBATCH8)  -wlf wave_file8.wlf -l test8.log  -sv_seed random  work.top +UVM_TESTNAME=ram_d4_addr_test
	vcover report  -cvg  -details -nocompactcrossbins -codeAll -assert -directive -html mem_cov8	
	
view_wave1:
	vsim -view wave_file1.wlf
	
view_wave2:
	vsim -view wave_file2.wlf
	
view_wave3:
	vsim -view wave_file3.wlf
	
view_wave4:
	vsim -view wave_file4.wlf

view_wave5:
	vsim -view wave_file5.wlf

view_wave6:
	vsim -view wave_file6.wlf
	
view_wave7:
	vsim -view wave_file7.wlf
	
view_wave8:
	vsim -view wave_file8.wlf
	
report:
	vcover merge mem_cov mem_cov1 mem_cov2 mem_cov3 mem_cov4 mem_cov5 mem_cov6 mem_cov7 mem_cov8
	vcover report -cvg -details -nocompactcrossbins -codeAll -assert -directive -html mem_cov

regress: clean run_test run_test1 run_test2 run_test3 run_test4 run_test5 run_test6 run_test7 report cov

cov:
	firefox covhtmlreport/index.html&
	
clean:
	rm -rf transcript* *log*  vsim.wlf fcover* covhtml* mem_cov* *.wlf modelsim.ini
	clear

