# OS Jackfruit – Container Memory Monitoring

This project demonstrates a custom container runtime integrated with a Linux kernel module to monitor and control memory usage of containers.

## Objective

To implement memory monitoring for containers and enforce:
- Soft memory limit (warning)
- Hard memory limit (process termination)

## Components

- monitor.ko → Kernel module for tracking memory usage  
- engine → Container runtime  
- supervisor → Manages containers  
- memory_hog → Test program that gradually increases memory  

## Execution Steps

1. Clean previous state (stop containers, remove logs)
2. Load kernel module and create device
3. Start engine supervisor
4. Run memory_hog inside container
5. Observe memory usage logs
6. Verify container status using `engine ps`

## Observations

- Memory usage increases gradually  
- Soft limit generates warning logs  
- Hard limit terminates the container  
- Container state becomes "killed"  

## Conclusion

The system successfully enforces memory limits.  
Soft limit provides early warning, while hard limit ensures strict control by killing the process.

## Team

- Shridhar U Golipalle (PES1UG25AM814)  
- Akash Bagoji (PES1UG24AM339)
