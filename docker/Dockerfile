FROM isaacgym

WORKDIR /opt/isaacgymenvs
RUN git clone https://github.com/isaac-sim/IsaacGymEnvs.git && cd IsaacGymEnvs && pip install -e . && pip install pandas ruamel.yaml requests scipy wandb
    
ENTRYPOINT ["bash"]

