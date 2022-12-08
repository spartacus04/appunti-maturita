#matematica 
Le forme di indecisione sono operazioni che coinvolgono infiniti e infinitesimi nel calcolo dei [[Limiti]] per le quali non è possibile determinare un risultato a priori e sono 7:
$$\frac{0}{0}$$
$$\frac{\infty}{\infty}$$
$$0\cdot\infty$$
$$1^\infty$$
$$\infty -\infty$$
$$0^0$$
$$\infty^0$$
Di seguito il metodo di risoluzione delle forme di indecisione viste in classe:

---
# $$ \infty -\infty$$
Per risolvere la forma di indecisione $\infty -\infty$ si guarda il grado massimo dei termini del polinomio e si esegue il limite di quel singolo termine.
		$$ \lim_{x\to+\infty} x^n - x^{n-1} - ...= +\infty-\infty\quad F.I.\rightarrow \lim_{x\to+\infty} x^n=+\infty$$
Dimostrazione con esempio:
$$\begin{aligned}
&\lim_{x\to+\infty} \biggl(x^3-2x^2+x-1\biggl)= \\
&\lim_{x\to+\infty} x^3\biggl(1-\frac{2}{x}+\frac{1}{x^2}-\frac{1}{x^3}\biggl)= \\
&\infty^3 \cdot\biggl(1-\frac{2}{\infty}+\frac{1}{\infty^2}-\frac{1}{\infty^3}\biggl)
\end{aligned}$$
---
# $$ \frac{\infty}{\infty} $$
Per risolvere la forma di indecisione $\frac{\infty}{\infty}$ si controlla per prima cosa il grado massimo del numeratore e del denominatore.
$$ \lim_{x\to\infty} \biggl( \frac{ax^n+bx^{n-1}+...}{Ax^m+Bx^{m-1}+...} \biggl)=\frac{\infty}{\infty}\quad F.I.$$
Nel caso il numeratore sia maggiore del denominatore:
$$ n>m \rightarrow \lim_{x\to\infty} ... = \infty $$
Nel caso il numeratore sia minore del denominatore:
$$ n < m \rightarrow \lim_{x\to\infty} ... = 0 $$
Nel caso il numeratore sia uguale al denominatore:
$$ n = m \rightarrow \lim_{x\to\infty} ... = \lim_{x\to\infty} \frac{ax^n}{Ax^m} = \frac{a}{A} $$
Dimostrazione con esempio:
$$\begin{aligned}
&\lim_{x\to+\infty}\frac{3x^2-x+5}{2x^3+x+2} = \\
&\lim_{x\to+\infty}\frac{x^2\cdot( 3-\frac{1}{x}+\frac{5}{x^2} )}{x^3\cdot(2+\frac{1}{x^2}+\frac{2}{x^3})} = \\
&\frac{x^2\cdot(3-0+0)}{x^3\cdot(2+0-0)} = \\
&\frac{3x^2}{2x^3}=\frac{3}{2x}=\frac{3}{\infty}=0
\end{aligned}$$


Come alternativa si può utilizzare il teorema di de l'Hopital (vedi Derivate).

$$
\lim_{x\to\infty}\biggl(\frac{f(x)}{g(x)}\biggl)=
\lim_{x\to\infty}\biggl(\frac{f'(x)}{g'(x)}\biggl)
$$
---
# $$ \frac{0}{0} $$
Per risolvere la forma di indecisione $\frac{0}{0}$ bisogna scomporre i termini del numeratore e del denominatore ([[Scomposizioni]]) e semplificare.
Esempio:
$$\begin{aligned}
&\lim_{x\to a} \biggl(\frac{x-a}{a^2-x^2} \biggl) = \frac{0}{0}\quad F.I. \\
&\lim_{x\to a} \biggl(\frac{(a-x)}{(a-x)(a+x)}\biggl)= \\
&\lim_{x\to a} \biggl(\frac{1}{a+x}\biggl)=...
\end{aligned}$$
