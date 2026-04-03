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
ssh -L localhost:XXXX:localhost:XXXX USERNAME@kronos.cs.swarthmore.edu\
cd local/USERNAME/TalkTuner-chatbot-llm-dashboard\
conda activate talktuner-gpu\
export PYTHONPATH=$PWD:$PWD/src\
jupyter lab --port=XXXX --no-browser\

Then, \
huggingface-cli login\
huggingface-cli whoami\
and type your hugginface token. Before logging out of your computer, make sure to run \
huggingface-cli logout\
huggingface-cli whoami\
