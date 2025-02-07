# F1tenth

## Jetson Cuda 인식 및 남은 메모리 확인(nvidia-smi에 잘 안나옴)

```bash
sudo apt-get update && \
sudo apt-get install -y nvidia-container-toolkit
sudo systemctl restart docker

sudo usermod -aG docker $USER
newgrp docker


```


```
pip install pycuda
python3
import pycuda.driver as cuda
import pycuda.autoinit
print(cuda.mem_get_info()) 
```


```bash
# nvidia 장치의 그룹 확인
ls -l /dev/nvidia*

sudo chgrp video /dev/nvidia*
sudo chmod g+rw /dev/nvidia*

sudo nano /etc/udev/rules.d/99-nvidia.rules
### Insert this line
KERNEL=="nvidia*", GROUP="video", MODE="0660"
###

# Set rules
sudo udevadm control --reload-rules
sudo udevadm trigger

# Check groups change to videos
ls -l /dev/nvidia*

# Check user is in video group
groups $USER

```