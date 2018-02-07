**NOCC** framework is aimed to simplify building distributed applications using `RDMA`. 

- We are working hard to make it easy to use.

***

**Dependencies:**

- CMake `>= version 2.8` (For compiling)


- Zmq `XX` (May be any version shall be fine, and current version ` >= 4.2.2` has been tested )
- Zmq C++ binding
- Boost `1.61.0` (Only tested)
- [LibRDMA](http://ipads.se.sjtu.edu.cn:1312/Windybeing/rdma_lib)
- [sparsehash](https://github.com/sparsehash/sparsehash-c11)

***

**Build:**

- Building **Ralloc** in [LibRDMA](http://ipads.se.sjtu.edu.cn:1312/Windybeing/rdma_lib)
  - `cd third_party/rdma_lib/`
  - `mkdir lib`
  - `cd ralloc`
  - `make;make install` 
- `cmake CMakeList`
- `make noccocc`

Be sure to add */nocc/third_party/rdma_lib/lib/ to `LD_LIBRARY_PATH`.

***

**Run:**

`cd scripts; ./run2.py config7.xml noccocc "-t 12 -c 10 -r 256" micro`, 

where `t` states for thread used, `c` states for coroutine used and `r` is left for workload.

A template config file:`config_template.xml` is in the root directory.

***

**Detailed config:**

You can modify `src/config.h`, `src/custom_config.h` and `src/app/config.h` to make customization of different running parameters.

We will soon make a detailed description and better configuration tools for NOCC.

***