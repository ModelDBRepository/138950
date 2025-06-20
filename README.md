# ReadMe File for Matlab code that accompanies:

JH Goldwyn and E Shea-Brown (2011). The what and where of channel noise in the Hodgkin-Huxley equations.

## Contents:

* `RunHH_gui.m` -- a user-friendly gui that generates spike trains for deterministic HH equations, Markov chain versions of HH equations, and the stochastic versions reviewed in the paper
* `StochasticHH_func` -- matlab functions that solve HH, stochastic versions of HH, and Markov chain version of HH using Euler method, Euler-Maruyama, and Gillespie methods.

## Examples:

1) Run Gui  
```matlab
>> RunHH_gui
```

2) Solve HH equations with subunit noise and plot results in command line  
```matlab
>> Y = Y = StochasticHH_func([0:0.01:100], @(t) 0, [], 100,'Subunit');
>> plot(Y(:,1), Y(:,2)), title('Voltage vs. Time')
>> plot(Y(:,1), Y(:,3)), title('Fraction of Open Na channels vs. Time')
>> plot(Y(:,1), Y(:,4)), title('Fraction of Open K channels vs. Time')
```

20150416 A minor typo fix sent by Josh Goldwyn where a matrix valued function AK (line 166) had its second row fixed from  
`4*alphan(V), -3*alphan(V)-betan(V), 0 , 0, 0;`  
corrected to  
`4*alphan(V), -3*alphan(V)-betan(V), 2*betan(V), 0, 0;`

---

2025-06-20: Converted README to Markdown.