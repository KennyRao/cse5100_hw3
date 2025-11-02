## Setup the environment
```
# remove the content 'pytorch-cuda=11.7 -c pytorch -c nvidia' if you are a mac user or are not going to use GPU
conda install pytorch==2.0.0 pytorch-cuda=11.7 -c pytorch -c nvidia
pip install 'gymnasium[classic_control]==0.27.1'
pip install matplotlib==3.7.1
pip install tensorboardX==2.6.4
```

## Complete the code

The files that you are going to implement are:

- `src/pg_agent.py`
- `src/policies.py`
- `src/critics.py`
- `src/utils.py`

See the [Assignment PDF](hw3.pdf) for more instructions.

## Submission

You should submit your code and the training logs, as well as your report on Canvas.

## Command lines
### Batch size of 1000:
```cmd
python run.py --env_name CartPole-v1 -n 200 -b 1000 --exp_name cartpole
python run.py --env_name CartPole-v1 -n 200 -b 1000 -rtg --exp_name cartpole_rtg
python run.py --env_name CartPole-v1 -n 200 -b 1000 -na --exp_name cartpole_na
python run.py --env_name CartPole-v1 -n 200 -b 1000 -rtg -na --exp_name cartpole_rtg_na
```
### Batch size of 4000:
```cmd
python run.py --env_name CartPole-v1 -n 200 -b 4000 --exp_name cartpole_lb
python run.py --env_name CartPole-v1 -n 200 -b 4000 -rtg --exp_name cartpole_lb_rtg
python run.py --env_name CartPole-v1 -n 200 -b 4000 -na --exp_name cartpole_lb_na
python run.py --env_name CartPole-v1 -n 200 -b 4000 -rtg -na --exp_name cartpole_lb_rtg_na
```
### Baseline off:
```cmd
python run.py --env_name CartPole-v1 -n 100 -b 5000 -rtg --exp_name cartpole_rtg_no_baseline
```
### Baseline on (default bgs=5, blr=5e-3):
```cmd
python run.py --env_name CartPole-v1 -n 100 -b 5000 -rtg -na --use_baseline --exp_name cartpole_na_rtg_baseline
```
### Fewer baseline gradient steps (bgs=1):
```cmd
python run.py --env_name CartPole-v1 -n 100 -b 5000 -rtg -na --use_baseline -bgs 1 --exp_name cartpole_na_rtg_baseline_bgs1
```
### Lower baseline learning rate (blr=1e-3):
```cmd
python run.py --env_name CartPole-v1 -n 100 -b 5000 -rtg -na --use_baseline -blr 1e-3 --exp_name cartpole_na_rtg_baseline_blr1e-3
```
