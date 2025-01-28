import numpy as np
import scipy as sc
import matplotlib.pyplot as plt


f = lambda x: 0.6*(x/(x+0.02))*(1-np.exp(-(x+0.02)*5))-((0.0042/4)*sum([ np.exp(-(i/4)*(0.02+x)) for i in range(1,21)]))

lambdaQ=sc.optimize.newton(f,0.5,maxiter=59)
print(round(lambdaQ,4),0.0042/0.6)

x = np.linspace(0,2,10000)
g=0.6*(x/(x+0.02))*(1-np.exp(-(x+0.02)*5))-((0.0042/3)*sum([ np.exp(-(i/3)*(0.02+x)) for i in range(1,16)]))

cds_spread= (0.6*0.03/0.05)*(1-np.exp(-0.05*5))/(sum([ np.exp(-(i/4)*(0.05)) for i in range(1,21)])*0.25)
print(round(cds_spread,4))

plt.plot(x,g)
plt.axhline(y = 0, color = 'k', linestyle = '-')
plt.axvline(x = 0, color = 'k', linestyle = '-')
plt.axhline(y = 0.6, color = 'r', linestyle = '--')
plt.plot(lambdaQ, 0, 'o', linestyle='none')
plt.title(" $P_{CDS}$(0,T) w.r.t. default intensity $λ^{Q}$ ")
plt.xlabel("$λ^{Q}$")
plt.ylabel("$f(λ^{Q})$")
plt.text(lambdaQ, 0, " $λ^{Q *}$ ", color='tab:orange',position= (lambdaQ+0.05,0.005))

plt.gca().yaxis.label.set(rotation='horizontal', ha='right');

plt.show()
