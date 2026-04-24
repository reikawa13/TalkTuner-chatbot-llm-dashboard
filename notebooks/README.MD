# TalkTuner Experiments
# Changes Made from the Original Code
## Environment
### Packages
- baukit (pip install git+https://github.com/davidbau/baukit.git)
- torchaudio (torchaudio==2.4.1)

### Computer 
- /local on kronos
- to activate the venv: conda activate talktuner-gpu
- to deactivate: conda deactivate

### Starting Up
ssh -L localhost:6013:localhost:6013 rkawaka1@kronos.cs.swarthmore.edu\
cd /local/rkawaka1/TalkTuner-chatbot-llm-dashboard \

export HF_HOME=/local/rkawaka1/hf-home\
export HUGGINGFACE_HUB_CACHE=/local/rkawaka1/hf-cache\
export TRANSFORMERS_CACHE=/local/rkawaka1/hf-cache\
export TORCH_HOME=/local/rkawaka1/torch-cache\

Then, \
huggingface-cli login\
huggingface-cli whoami\
and type your hugginface token. Before logging out of your computer, make sure to run \
huggingface-cli logout\
huggingface-cli whoami\

export GEMINI_API_KEY="your_key_here"\


conda activate talktuner-gpu\
export PYTHONPATH=$PWD:$PWD/src\
jupyter lab --port=XXXX --no-browser\

Make sure to start the jupyter from the repo root. \

To run the notebook overnight, use tmux.
tmux new -s talktuner\
cd /local/rkawaka1/TalkTuner-chatbot-llm-dashboard\
conda activate talktuner-gpu\
export PYTHONPATH=$PWD:$PWD/src\
export HF_HOME=/local/rkawaka1/hf-home\
export HUGGINGFACE_HUB_CACHE=/local/rkawaka1/hf-cache\
export TRANSFORMERS_CACHE=/local/rkawaka1/hf-cache\
export TORCH_HOME=/local/rkawaka1/torch-cache\
jupyter lab --port=XXXX --no-browser\

then, detach with Ctrl-b d\
come back with tmux attach -t talktuner
