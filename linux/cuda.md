# Cuda
```
cat /usr/local/cuda/version.txt
```

# Cudnn
```
cat /usr/local/cuda/include/cudnn.h | grep CUDNN_MAJOR -A 2
```

# Check ram
```
sudo fuser -v /dev/nvidia*
```
