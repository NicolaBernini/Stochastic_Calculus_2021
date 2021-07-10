<script type="text/javascript"
  src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.3/MathJax.js?config=TeX-AMS-MML_HTMLorMML">
</script>

# Brownian Motion 

Brownian Motion 

# 1. Probability Space 

A probability space is a triplet $$\Omega, \mathcal{A}, P$$ so that 

- $$\Omega$$ is the set of elementary events 

- $$\mathcal{A}$$ is a Sigma Algebra on $$\Omega$$ that is a set of subset of $$\Omega$$ that are closed to set theoretical operations (e.g. intersection, union, ...) executed a countable number of times, meaning applying that kind of operations a countable number on elements of times on elements of $$\mathcal{A}$$ is again an element of $$\mathcal{A}$$ 

- $$P$$ is a probability measure for elements of $$\mathcal{A}$$ 



So we see the progression 

1. the set of elementary events 

2. the way elementary events are composed to produce non elementary events 

3. the way to measure the probability of each event 





# 2. Filtrations 

If we take a stochastic process, for example a Brownian Motion, it has a temporal component: the longer the time the more the possible trajectories are 

Translating this into the Probability Space means the way the elementary events can be composed in a sequential way grows over time and hence the Sigma Algebra changes over time so we can index the Sigma Algebras with $$t$$ so to have $$\mathcal{A}_{t}$$ 

So $$\mathcal{A}_{t}$$ represents the set of all possible trajectories up to time $$t$$ and the probability of each trajectory can be measure with $$P$$ that in fact acts on elements of the Sigma Algebra 

As the set of possible trajectories can only grow with time the same happens to the sigma algebra meaning, from a set perspective, that more recent sigma algebras must include all the previous ones so $$\mathcal{A}_{t} \subseteq \mathcal{A}_{T} \quad t \le T$$

Let's finally group the sigma algebras by time so that $$\mathcal{F}_{t} = \{\mathcal{A}_{\tau}\}_{\tau \le t}$$ 

A Filtration is this $$\mathcal{F}_{t}$$ set of Sigma Algebras indexed by over time 








