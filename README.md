# FPGA-Accelerated-NN


## Key Components
1. `aviation_asr.cpp`
   - Audio feature extraction (MFCC simulation)
   - Neural network with FPGA-accelerated layers
   - Command decoding logic
   - FPGA interface simulation

2. `fpga_accel.v`
   - Verilog implementation of Conv1D and LSTM
   - Parallel MAC operations for neural layers
   - Hardware-friendly fixed-point arithmetic

## FPGA Acceleration
- **Conv1D Layer**: 
  - 128 parallel filters
  - 3x40 kernel optimized for DSP slices
- **LSTM**:
  - 128-cell architecture
  - Pipeline-optimized gate operations
  - On-chip weight storage

## Usage
1. Compile C++ code:
   ```bash
   g++ -std=c++17 aviation_asr.cpp -o asr_demo
