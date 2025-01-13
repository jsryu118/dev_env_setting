# SLAM TOOLS

## pcl viewer
Installation

```bash
sudo apt install pcl-tools
```
Usage
```bash
pcl_viewer pcd_name.pcd
#Row Style visualization 1xN
pcl_viewer -multiview 1  0.pcd 1.pcd 
#Column Style visualization Nx1
pcl_viewer -multiview 2  0.pcd 1.pcd 
#Matrix Style visualization NxM
pcl_viewer -multiview 3  0.pcd 1.pcd 2.pcd 3.pcd 
```

## Open3d
Installation\
[Open3D src Installation](https://www.open3d.org/docs/latest/compilation.html)

```bash
git clone https://github.com/isl-org/Open3D
# Only needed for Ubuntu
cd Open3D
util/install_deps_ubuntu.sh
mkdir build
cd build
cmake ..
# On Ubuntu
make -j$(nproc)
make install

```

### (Optional) CMAKE Version Upgrade
1. Download appropriate version .tar file && unzip 
2. Installation
```bash
cd cmake-3.xx.x
./bootstrap
make -j$(nproc)
make install
```
3. version check
```bash
cmake --version
```