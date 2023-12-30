# Plan
- Learn how to use oneAPI learning resources provided by intel, and the cloud environment, ```JupyterLab``` provided by intel to execute and test your code.
- SYCL Programming Model (Kernel, Queues, Buffers, Devices).
- oneAPI for non-intel GPUs: Nvidia..etc

# Get Started on Learning SYCL Programming
Go to get started webpage of intel, and access the JupyterLab which offers a cloud environment and learning resources for SYCL programming.
- openAPI Essentials contain Modules that you should check out.
- SYCL abstracts away all complexities such as memory allocations, i.e you don't need to know where the allocated memory resides: on the host or on devices.

# Explaining the Model
- We have a **Host** and **Devices** around it.
- Devices can be GPU1, GPU2.., FPGA (accelerators), another CPU...etc
- The ```SYCL``` program runs on the Host, i.e the host ```CPU```.
- The host can be attached to devices using a ```Queue```. The queue submits jobs to devices, and these jobs are ```kernels```.
- Queues are C++ objects, and kernels are specified using ```Lambda functions```.
- Buffers are special C++ objects which abstract the complexities of GPUs and CPU.
- ```Accessors``` are used to access the buffers which are shared between the devices and Host.
- We can use multiple GPUs with SYCL, by attaching multiple queues to the host. When I want to use a certain devices, I submit jobs to its queue.
- A queue cannot be attached to multiple devices, but multiple queues can be attached to a single device. The latter option is ```Load Balancing```.

# Local Environment
- You either use the cloud or your own computer. For the latter option, you have to install the openAPI SDK.
- You have to check if your GPU is compatible with openAPI.

# CodePlay for Non-intel GPUs
- codeplay oneAPI is a **plug-in** that is used to program non-intel GPUs.
- After installing the the plug-in, Nvidia will show up when the following command is executed:
```
sycl-ls
```
Then, we can select the Nvidia GPU when creating the queue in the code.
We can also load balance jobs between our intel GPU and Nvidia GPU.

# oneAPI YT Channel
- It has very interesting and short videos about oneAPI.
- Highly recommended.
- openAPI is the commercial product name for intel, behind it is standard C and SYCL.
