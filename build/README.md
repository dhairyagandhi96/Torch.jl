# Building the Wrapper

The project can be built given that we can provide the paths to working Torch and CUDA/ CUDNN projects. The binaries can also be downloaded from the [official libtorch binaries](https://pytorch.org/get-started/locally/), which is what the wrapper is based on. This currently supports torch v1.4.0.

```code
$ mkdir build && cd build

# With a working torch install via Python (or similar): setting the CMAKE_PREFIX_PATH to point there might be sufficient
$ CMAKE_PREFIX_PATH=$HOME/.local/lib/python3.6/site-packages/torch\
  CUDNN_LIBRARY_PATH=$HOME/cuda/lib64\
  CUDNN_INCLUDE_PATH=$HOME/cuda/include\
  CUDNN_INCLUDE_DIR=$HOME/cuda/include\ 
  cmake ..

$ cmake --build .
```

Post this, adding the path to the project via the `LD_LIBRARY_PATH` (and also the CUDNN) binary path might be needed.
