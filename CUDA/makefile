NVCC = nvcc

CUDAFLAGS = \
	-Wno-deprecated-gpu-targets

# Runs on host (CPU)
host_hello_world: hello_world/hello_world_host.cu
	$(NVCC) $(CUDAFLAGS) $^ -o $@

run_host_hello_world: host_hello_world
	./$<

# Runs on device (GPU)
device_hello_world: hello_world/hello_world_device.cu
	$(NVCC) $(CUDAFLAGS) $^ -o $@

run_device_hello_world: device_hello_world
	./$<

# Unified memory between CPU & GPU example.

unified_mem: unified_memory/unified_mem.cu
	$(NVCC) $(CUDAFLAGS) $^ -o $@

run_unified_mem: unified_mem
	./$<

## Vector add Examples
# Serial
vector_add_serial: vector_add/vecadd_ser.cu
	$(NVCC) $(CUDAFLAGS) $^ -o $@

run_vector_add_serial: vector_add_serial
	./$<

# Parallel
vector_add_parallel: vector_add/vecadd_par.cu
	$(NVCC) $(CUDAFLAGS) $^ -o $@

run_vector_add_parallel: vector_add_parallel
	./$<

# Parallel Block 
vector_add_parallel_block: vector_add/vecadd_par_block.cu
	$(NVCC) $(CUDAFLAGS) $^ -o $@

run_vector_add_parallel_block: vector_add_parallel_block
	./$<

clean:
	rm -f host_hello_world device_hello_world unified_mem vector_add_serial vector_add_parallel vector_add_parallel_block