`
$$
\begin{align}  
Var  
&=\frac{1}{2n^{2}}\sum_{i=1} ^n\sum_{j=1}^n \Vert y_i-y_j \Vert_2^2\\   
&=\frac{1}{2n^{2}}\sum_{i,j=1}^n Tr[(y_i-y_j)({y_i-y_j})^\mathrm{T}]\\  
&=\frac{1}{2n^{2}}\sum_{j,j=1}^n Tr(y_i y_i^\mathrm{T}-y_i y_j^\mathrm{T}-y_j y_i^\mathrm{T}+y_j y_j^\mathrm{T})\\  
&=Tr(\ \frac{1}{n}\sum_{i=1}^{n}(y_i y_i^\mathrm{T}-\overline{y}\overline{y} ^\mathrm{T})\\  
&=Tr(\ \frac{1}{n}\sum_{i=1}^{n}(y_i y_i^\mathrm{T}-\overline{y}\overline{y}^\mathrm{T}-\overline{y}\overline{y}^\mathrm{T}+\overline{y}\overline{y}^\mathrm{T}))\\  
&=Tr(\ \frac{1}{n}\sum_{i=1}^{n}y_i y_i^\mathrm{T} -\frac{1}{n}\sum_{i=1}^{n}y_i\overline{y}^\mathrm{T}-\frac{1}{n}\sum_{i=1}^{n}\overline{y} y_i^\mathrm{T}+\frac{1}{n}\sum_{i=1}^{n}\overline{y}\overline{y}^\mathrm{T})\\  
&=\frac{1}{n}Tr(\ \sum_{i=1}^{n}(y_i - \overline{y})(y_i - \overline{y})^\mathrm{T})\\  
&=\frac{1}{n}Tr(\ u^\mathrm{T}[\sum_{i=1}^{n}(x_i - \overline{x})(x_i - \overline{x})^\mathrm{T}]u)\\  
&=\frac{1}{n}Tr(\ u^\mathrm{T}\hat{X}\hat{X}^\mathrm{T}u)  
\end{align}  
$$  

$$   
PCA=  
\begin{cases}  
\mathop{max}\limits_{u}  \frac{1}{n}Tr(\ u^\mathrm{T}\hat{X}\hat{X}^\mathrm{T}u)\\  
S.T.\ \  u^\mathrm{T}u = I_{m\times m}  
\end{cases}  
$$  
`
