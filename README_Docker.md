build docker image from https://developer.nvidia.com/isaac-gym

docker run --rm -it --ipc=host --gpus all --net=host -v .:/workspace --volume=$HOME/.Xauthority:/root/.Xauthority:rw -e DISPLAY=$DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix --privileged isaacgym bash

### or

docker run --rm -it --ipc=host --gpus all --net=host -v .:/workspace --volume=$HOME/.Xauthority:/root/.Xauthority:rw -e DISPLAY=$DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix --privileged cmorl

git clone https://github.com/isaac-sim/IsaacGymEnvs.git
pip install -e .

pip install pandas ruamel.yaml requests scipy wandb


python main_student.py --task_cfg_path tasks/go1_backflip.yaml --algo_cfg_path algos/student/go1_backflip.yaml --wandb --seed 1 --model_num 100000000

python main_student.py --task_cfg_path tasks/go1_backflip.yaml --algo_cfg_path algos/student/go1_backflip.yaml --test --render --seed 1 --model_num 100000000
