# MujocoPy Installation

On linux, without root permissions. Assume conda is installed, initialized, and located at `$CPATH$`.

```
mkdir /home/username/.mujoco
```

```
tar -xvf mujoco210-linux-x86_64.tar.gz -C ~/.mujoco/
```

Add the following lines to `~/.bashrc`:
```
export LD_LIBRARY_PATH=/home/user-name/.mujoco/mujoco210/bin 
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/lib/nvidia 
```

Exit and reopen terminal. Alternatively:
```
source ~/.bashrc
```

Create conda environment:
```
conda create -n mujoco
conda activate mujoco
conda install -c conda-forge glew
conda install -c conda-forge mesalib
conda install -c menpo glfw3
```

In `~/.bashrc`, add:
```
conda activate mujoco
export CPATH=$CONDA_PREFIX/include
```

```
source ~/.bashrc
```

```
cd ~/.mujoco
git clone https://github.com/openai/mujoco-py
cd mujoco-py
pip install -r requirements.txt
pip install -r requirements.dev.txt
pip3 install -e . --no-cache
```

Reboot.

```
conda activate mujoco
pip3 install -U 'mujoco-py<2.2,>=2.1'
```
