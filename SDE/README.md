<script type="text/javascript"
  src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.3/MathJax.js?config=TeX-AMS-MML_HTMLorMML">
</script>


# Stochastic_Calculus_2021

A problem solving approach to learning Stochastic Differential Equations 

# Problem 1 - Build a model for what's in the figure 

Say we want to build a model for the trajectory of a given asset in the price space, something like this 

![Img1](https://www.researchgate.net/profile/Davis-Ntwiga/publication/30758355/figure/fig2/AS:669441016745995@1536618584469/shows-the-evolution-of-a-stock-price-in-a-geometric-Brownian-motion-path-using-211-and.png)

so we start using an ODE that's a reasonable choice for a dynamic model 

$$
\left\{\begin{matrix}
\dot x = f(x(t),t)
\\ 
x(0) = 0
\end{matrix}\right.
$$

We assume $$f(\cdot, \cdot)$$ is smooth however we realize this assumption makes the model good for smooth trajectories and this is clearly not the case of the figure, so we need to extend it including a component that can model the noise 

Assuming additive noise is reasonable: it means the underlying "denoised" behavior can be modeled by the above ODE but we also need to add the noise component 

We use $$\xi(t)$$ to denote White Noise and we modulate it with a generic term $$g(x(t), t)$$ so we end up with 

$$
\left\{\begin{matrix}
\dot x = f(x(t),t) + g(x(t), t) \xi(t)
\\ 
x(0) = 0
\end{matrix}\right.
$$

Now we have defined a Stochastic Differential Equation (SDE) and it is a good model for the trajectory in the figure 



# Problem 2 - Road to the solution: Analysis the SDE 

We have now these specific problems 

- 2.1 How to manipulate the noise to be able to integrate over it 

- 2.2 What does the SDE solution look like mathematically? Is it unique? How do we get there? 

- 2.3 What are the assumptions about $$f()$$ and $$g()$$ we need to make to be able to get to an SDE solution 



## 2.1 Manipulating the noise to be able to integrate over it

White Noise is related to Brownian Motion, the latter infinitesimal step $$d W_{t}$$ is a sample of a White Noise generative process  

Mathematically it means 

$$ dW_t = \xi(t)dt $$ 

So to be able to use $$d W_{t}$$ in the SDE let's multiply both sides for $$dt$$ and get

$$
\left\{\begin{matrix}
d x(t) = f(x(t),t)dt + g(x(t), t) dW_{t}
\\ 
x(0) = 0
\end{matrix}\right.
$$

So now the problem becomes to define a way to integrate over the $$d W_{t}$$ step 





## 2.2 SDE Solution 

TBD 



## 2.3 Assumptions about $$f()$$ and $$g()$$

TBD



# 3. Integration on $$dW_{t}$$ definition 

Let's build a simple process $$\theta_{t}$$ by sampling $$\Xi^{(s)}$$ white noise $$m$$ times in the $$[0,t]$$ interval so that we have $$\xi_{i}^{(s)}$$ samples at $$t_{i} \quad i=1,...,m$$ 

$$
\theta_{t} = \sum_{i=1}^{m-1} \xi_{i}^{(s)} I_{t_{i}, t_{i+1}}(t)
$$

with 

$$

I_{a,b}(t) = \left\{\begin{matrix}
1 \quad t \in [a,b] 
\\ 
0 \quad t \notin [a,b]
\end{matrix}\right.

$$

NOTE: I am using the extra $$(s)$$ to distinguish this from the other white noise that is used to build $$dW_{t}$$ (see later)

We already know what it means to integrate on $$dt$$ as intuitively it is just computing the area between the width $$t_{i+1} - t_{i}$$ and height $$\xi$$ so 

$$
\int_{0}^{\tau} \theta_{t} dt = \sum_{i=0}^{m-1} \xi_{i}^{(s)} (t_{i+1} - t_{i}) \quad 0 < ... < t_{i} < ... < t_{m} < \tau
$$



Now by analogy we define the $$\int \theta_{t} dW_{t}$$ just changing the width to $$W_{t+1} - W_{t}$$ that using $$t_{i}$$ becomes $$dW_{t_{i}} = W_{t_{i+1}} - W_{t_{i}}$$

First of all let's build $$W_{t}$$ by sampling the $$\Xi^{(b)}$$ white noise again in $$\{t_{i}\}_{i=1,...,m}$$ so now we have $$\{xi_{i}^{(b)}\}_{i=1,...,m}$$ and from above we can recall $$dW_{t_{i}} = \xi_{i}^{(b)}dt$$

Now let's use the analogy to define the integral 

$$
\int_{0}^{\tau} \theta_{t} dt = \sum_{i=0}^{m-1} \xi_{i}^{(s)} (W_{t_{i+1}} - W_{t_{i}}) \quad 0 < ... < t_{i} < ... < t_{m} < \tau \\
\int_{0}^{\tau} \theta_{t} dt = \sum_{i=0}^{m-1} \xi_{i}^{(s)} \xi_{i}^{(b)} (t_{i+1} - t_{i}) \quad 0 < ... < t_{i} < ... < t_{m} < \tau
$$

so eventually everything has been expressed in terms of white noise samples used as fundamental units of the uncertainty in this model 





