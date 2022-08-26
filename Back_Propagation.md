# Back Propagation

$$ \frac{\partial C}{\partial w} = \frac{\partial z}{\partial w}\frac{\partial C}{\partial z} $$
	z为经过激活函数之前的数，$z=\sum_{i=0}^n{w_i a_i}$，$a_i$为上一层神经元输出，$w_i$为权重


## Forward Pass
$$ \frac{\partial z_k}{\partial w} = a_{k-1} $$
	$a_{k-1}$为该权重w所对应的上一个Neuron的output

## Backward Pass
$$ \frac{\partial C}{\partial z_k} = \sigma'(z)\sum\frac{\partial C}{\partial z_{k+1}} $$
	当k为最后一层时，$\frac{\partial C}{\partial z_k} = \frac{\partial C}{\partial y}$	，根据Cost Function C的定义来计算。
	Backward Pass可以看作修改过的反向的神经网络。

最后将两部分相乘即可得出$\frac{\partial C}{\partial w}$，然后就可以用于梯度下降。