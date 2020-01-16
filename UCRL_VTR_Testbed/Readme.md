# Readme

run_agent.py - this file runs both RLSVI and UCRL_VTR in both the RiverSwim and DeepSea environments. 
It outputs a LogLog plot of the cumlative reward of both RLSVI and UCRL_VTR. As of right now, UCRL_VTR has a hard
time running DeepSea because the dimension of the problem is |S * A * S| in the tabular setting. If depth of the problem 
is equal to 10, then we are inverting and multiplying a 20000-dimensional square matrix at each time-step. Need to either
reduce the dimension of the problem by moving the problem from the tabular to the linear setting, or try to implement more 
efficent linear algebra operations. Currently, UCRL_VTR runs with the Sherman-Morrison update (Eqn 9.22 of Rich's RL book).

agents.py - this file contains RLSVI, PSRL, and UCRL_VTR algorithms.

environments.py - this file contains the DeepSea and RiverSwim environments.

