# Docker Builds

If you have never used Docker before, check out the [getting started guide](https://docs.docker.com/get-started/)

## CPU Images

-	[`cpu-latest`, `cpu`, `cpu-0.1`, `latest`](cpu/Dockerfile)
-	[`cpu-jupyter-kubeflow-latest`, `cpu-jupyter-kubeflow`, `cpu-jupyter-kubeflow-0.1`](cpu-jupyter-kubeflow/Dockerfile)

### GPU Images
-	[`gpu-latest`, `gpu`, `gpu-0.1`](gpu/Dockerfile)
-	[`gpu-jupyter-kubeflow-latest`, `gpu-jupyter-kubeflow`, `gpu-jupyter-kubeflow-0.1`](gpu-jupyter-kubeflow/Dockerfile)

The CPU images should run out of the box without any driver prerequisites.

## GPU Images

### Prerequisites

To use the GPU images, you need to have:
- [The Nvidia drivers](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/install-guide.html#nvidia-drivers)
- [The Nvidia-docker container runtime](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/install-guide.html#setting-up-nvidia-container-toolkit)
- [Docker configured to use the Nvidia container runtime](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/user-guide.html#daemon-configuration-file)

Once you have those installed, you should be ready to start running the GPU instances.

### Testing GPUs

To make sure your GPU instance is setup correctly, run the following in a container:

```python3
import dlib
print(dlib.cuda.get_num_devices())
```

## Jupyter Images

The Jupyter images are built to be deployed on [Kubeflow](https://www.kubeflow.org/). However, if you just want to run a normal Jupyter instance, they're a great template to build your own.

