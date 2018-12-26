# Neural Meta Learning for Multifidelity Bayesian Optimization
In this study, meta learning is implemented as a multi-layer RNN for multi-fidelity Bayesian optimization. The main goal is to use meta-data to understand how automatic learning can become flexible in solving different kinds of learning problems, hence to improve the performance of existing learning algorithms. We explore the space via cheap or low fidelity and leverage the exploration with high fidelity on a successively smaller region. BO with multifidelity can achieve better performance than that with single fidelity.

In the experiments, we will use a large number of differentiable functions and its auxiliary functions both generated with GP to train an RNN optimizer. Within the training horizon, the RNN optimizers are competitive with heavily engineered packages such as GPflowopt. Our  experiments will show that the RNN optimizer is faster and tends to achieve better performance within the horizon for which it is trained.  Besides, our experiments show that the algorithm  discovers the global optima of a black-box function with minimal cost and
outperforms existing single-fidelity optimization algorithms. Our algorithm explores the space using the cheap lower fidelities, and uses the higher fidelity queries on successively smaller regions, hence is able to converge closer to the global optima with lesser cost.

<img src="Others/NML-MF-BO.PNG" width="100%">

## File
### Generate_GP.ipynb
generate GP function with different parameter

### LSTM_BO.ipynb
train lstm to perform BO with different loss

### LSTM_MF_BO.ipynb
train lstm to perform multifidelity BO

### test_LSTM.ipynb
test different LSTM model 

### plot_LSTM.ipynb
plot search trajectory with LSTM model

### GP_BO.ipynb
GP BO (GPflowOpt) for test function

## Result
### Functions from a GP prior

Average minimum observed function value, with 95% confidence intervals,
as a function of search steps on functions sampled from the training GP distribution
<img src="Others/min_step_1.PNG" width="100%">

Average minimum observed function value, with 95% condence intervals,
as a cumulative cost on functions sampled from the training GP distribution
<img src="Others/min_cost_1.PNG" width="100%">

Run-time (seconds) for 100 iterations excluding the black-box function evaluation time
<img src="Others/time.PNG" width="50%">

How dfferent methods trade-off exploration and exploitation in a onedimensional
example. Blue: Unknown function being optimized. Crosses: Function
values at query points. Gray trajectory: Query points over 20 steps.
<img src="Others/search_1.PNG" width="100%">
<img src="Others/search_2.PNG" width="100%">

Performance with number of training data
<img src="Others/trainingdatanum.PNG" width="50%">

### Global Optimization Benchmarks
Loss on 2 benchmark functions (Gramacy and Lee, Branin) with 95%
confidence intervals as a function of the number of steps
<img src="Others/min_step_2.PNG" width="100%">

Average minimum observed function value, with 95% confidence intervals,
as a function of search steps on global optimization benchmarks
<img src="Others/min_step_3.PNG" width="100%">

Average minimum observed function value, with 95% confidence intervals,
as a cumulative cost on global optimization benchmarks
<img src="Others/min_cost_3.PNG" width="100%">

Run-time (seconds) for 100 iterations excluding the black-box function
evaluation time
<img src="Others/time_2.PNG" width="70%">

