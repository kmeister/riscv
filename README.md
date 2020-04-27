# to set up
```
cd gem5/configs/common/cores
git clone http://github.com/kmeister/riscv
```
# To Run using se.py
```
cd ~/gem5
build/RISCV/gem5.opt --stats-file=RISCV.txt --dump-config=CONFIG.ini configs/example/se.py -c ../ML_Benchmark/Benchmarks/mlbench --caches --l1i_size=32kB --l1i_assoc=8 --l1d_size=32kB --l1d_assoc=8 --cacheline_size=64 --l2cache --l2_size=512kB --l2_assoc=8 --cpu-clock=1.6GHz --cpu-type=boom  -n 1 --maxinsts=100000000 
```

# Known Limitations
1. BOOM FUs are... odd. we'd need to do some serious coding to get something close here
2. BOOM uses a different branch predictor
3. No simulation of TLBs
4. Haven't figured out how to update se.py to get the caches defined in this
file to be used. use the above command for a close cache config.
