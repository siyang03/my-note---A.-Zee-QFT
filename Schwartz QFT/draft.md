```
\item 那么 (up to an infinite phase)
	\begin{align}
		& \braket{f | S | i} \notag \\
		=& (2 \pi)^{3 n / 2} \sqrt{2 \omega_{p_1} \cdots 2 \omega_{p_n}} \braket{\Omega | a_{\vec{p}_3}(+ \infty) \cdots a_{\vec{p}_n}(+ \infty) a^\dag_{\vec{p}_1}(- \infty) a^\dag_{\vec{p}_2}(- \infty) | \Omega} \notag \\
		=& (2 \pi)^{3 n / 2} \sqrt{2 \omega_{p_1} \cdots 2 \omega_{p_n}} \braket{\Omega | T \{(a_{\vec{p}_3}(+ \infty) - a_{\vec{p}_3}(- \infty)) \cdots (a^\dag_{\vec{p}_2}(\mathcolor{red}{-} \infty) - a^\dag_{\vec{p}_2}(\mathcolor{red}{+} \infty))\} | \Omega} \notag \\
		=& \Big( i \int d^4 x_1 \, e^{- i p_1 \cdot x_1} (\partial_1^2 + m^2) \Big) \cdots \Big( i \int d^4 x_n \, e^{i p_n \cdot x_n} (\partial_n^2 + m^2) \Big) \braket{\Omega | T\{\phi(x_1) \cdots \phi(x_n)\} | \Omega}
	\end{align}
	得到 LSZ reduction formula.
	
	\begin{tcolorbox}[title=calculation:]
		令
		\begin{align}
			& f_i(t) := i \int d^3 x \, e^{- i p_i \cdot x} (\partial^2 + m^2) \phi, \\
			\Longrightarrow & F_i(t) = i \frac{(2 \pi)^{3 / 2}}{\sqrt{2 \omega_{p_i}}} e^{i \omega_{p_i} t} (\partial_t - i \omega_{p_i}) (a_{\vec{p_i}}(t) + a^\dag_{- \vec{p_i}}(t)),
		\end{align}
		其中 $f_i(t) = F_i'(t)$, 那么
		\begin{align}
			& \Big( i \int d^4 x_1 \, e^{- i p_1 \cdot x_1} (\partial_1^2 + m^2) \Big) \cdots \Big( i \int d^4 x_n \, e^{i p_n \cdot x_n} (\partial_n^2 + m^2) \Big) \braket{\Omega | T(\phi(x_1) \cdots \phi(x_n)) | \Omega} \notag \\
			=& \sum_{i_1, \cdots, i_n} \braket{\Omega | \int_{- \infty}^\infty dt_{i_1} \, f_{i_1}(t_{i_1}) \int_{- \infty}^{t_{i_1}} dt_{i_2} \, f_{i_2}(t_{i_2}) \cdots \int_{- \infty}^{t_{i_{n - 1}}} dt_{i_n} \, f_{i_n}(t_{i_n}) | \Omega}, \label{the S-matrix and time-ordered products.1.14}
		\end{align}
		对 $(i_1, \cdots, i_n)$ 是所有 $\{1, \cdots, n\}$ 的排列求和. 考虑
		\begin{align}
			& \int_a^b dt_1 \, f_1(t_1) \int_a^{t_1} dt_2 \, f_2(t_2) + \int_a^b dt_2 \, f_2(t_2) \int_a^{t_2} dt_1 \, f_1(t_1) \notag \\
			=& \int_a^b dt_1 \, f_1(t_1) (F_2(t_1) - F_2(a)) + (1 \leftrightarrow 2) \notag \\
			=& \Big( \int_a^b dt_1 \, f_1(t_1) F_2(t_1) - (F_1(b) - F_1(a)) F_2(a) \Big) + (1 \leftrightarrow 2) \notag \\
			=& \Big( - \int_a^b dt_1 \, F_1(t_1) f_2(t_1) + F_1(b) (F_2(b) - F_2(a)) \Big) + (1 \leftrightarrow 2) \notag \\
			=& \int_a^b dt \, [f_1(t), F_2(t)] + F_2(b) (F_1(b) - F_1(a)) - (F_1(b) - F_1(a)) F_2(a) \notag \\
			=& \int_a^b dt \, [f_2(t), F_1(t)] + F_1(b) (F_2(b) - F_2(a)) - (F_2(b) - F_2(a)) F_1(a),
		\end{align}
		在 Heisenberg picture 下计算 \eqref{the S-matrix and time-ordered products.1.14} 会遇到一些非零的对易子.
		
		\noindent\rule[0.5ex]{\linewidth}{0.5pt} % horizontal line
		
		用 \eqref{Feynman rules.2.6} (interactive picture) 中 correlation function 的形式, 那么
		\begin{equation}
			i \int d^4 x \, e^{i p \cdot x} (\partial^2 + m^2) \phi_0(x) = 0,
		\end{equation}
		但注意到
		\begin{align}
			& \braket{0 | T\{\phi_{0, 1} \cdots \phi_{0, n} U_I(+ \infty, - \infty)\} | 0} \notag \\
			=& \sum_{i_1, \cdots, i_n} \braket{0 | U_I(\infty, t_{i_1}) \phi_{0, i_1} U_I(t_{i_1}, t_{i_2}) \cdots \phi_{0, i_n} U_I(t_{i_n}, - \infty) | 0} \theta(t_{i_1} - t_{i_2}) \cdots,
		\end{align}
		且 (考虑相互作用为 $V(\phi)$ 的情况)
		\begin{align}
			& \partial_t (U_I(a, t) \phi_0(x) U_I(t, b) \theta(a - t) \theta(t - b)) \notag \\
			=& U_I(a, t) (i \underbrace{[H_I(t), \phi_0(x)]}_{= 0} + \partial_t \phi_0) U_I(t, b) \theta(a - t) \theta(t - b) \notag \\
			& + U_I(a, t) \phi_0(x) U_I(t, b) (- \delta(a - t) \theta(t - b) + \theta(a - t) \delta(t - b)) \\
			\Longrightarrow & \partial_t^2 (U_I(a, t) \phi_0(x) U_I(t, b) \theta(a - t) \theta(t - b)) \notag \\
			=& U_I(a, t) (i [H_I(t), \partial_t \phi_0] + \partial_t^2 \phi_0) U_I(t, b) \theta(a - t) \theta(t - b) \notag \\
			& + 2 U_I(a, t) \partial_t \phi_0 U_I(t, b) (- \delta(a - t) \theta(t - b) + \theta(a - t) \delta(t - b)) \notag \\
			& + U_I(a, t) \phi_0(x) U_I(t, b) \notag \\
			& (- 2 \delta(a - t) \delta(t - b) - (\partial_t \delta(a - t)) \theta(t - b) + \theta(a - t) (\partial_t \delta(t - b))) \\
			\Longrightarrow & (\partial^2 + m^2) (U_I(a, t) \phi_0(x) U_I(t, b) \theta(a - t) \theta(t - b)) \notag \\
			=& - U_I(a, t) \frac{\delta H_I(t)}{\delta \phi_0(x)} U_I(t, b) \theta(a - t) \theta(t - b) \notag \\
			& + 2 U_I(a, t) \partial_t \phi_0 U_I(t, b) (- \delta(a - t) \theta(t - b) + \theta(a - t) \delta(t - b)) \notag \\
			& + U_I(a, t) \phi_0(x) U_I(t, b) \notag \\
			& (- 2 \delta(a - t) \delta(t - b) - (\partial_t \delta(a - t)) \theta(t - b) + \theta(a - t) (\partial_t \delta(t - b))),
		\end{align}
		... 比 Heisenberg picture 更难算.
	\end{tcolorbox}
```