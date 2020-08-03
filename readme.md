# An-Introduction-to-Quantum-Computing-by-Qiskit
Qiskit is an open-source SDK which is used to program IBM's quantum computers. Qiskit is useful for working with noisy quantum computers at the level of pulses, circuits, and algorithms. This is an introductory tutorial on quantum computing which will get you started with coding on qiskit.


# Prerequisites
This tutorial assumes knowledge of Basic Linear Algebra, Basic Quantum Mechanics and Basic Digital logic but most importantly an open mind not limited to accepting only classical thinking!

# Introduction
Analogous to the bits that are used by classical computers, quantum computers use qubits as the basic unit of quantum information. But what are qubits exactly? 

Think of an electron. Remember that the energy states of the electron are quantized and only take in discrete values. Now if we wish to represent a bit of information, we can restrict the energy of the system to be between the ground state and the first excited state. In this way the electron can only be at either of the two states - $$|0> or \ \ |1>$$

![](images/electron.png)

But the speciality of quantum particles like electrons is that it does NOT decide beforehand where it wants to be, which is why we say that is in a superposition of the states $$|0> and \ \ |1>$$

The superposition of the states can be represented as a linear combination of the original states as
$$\alpha|0> + \beta |1>$$ where 
$\alpha \ , \ \beta \in C$ represent the the complex amplitudes of each of the states.

But what does a complex amplitute mean? The physical interpretation of this can be explained by the Born rule which says that the probability of each of the quantum states is given by the square of the it's complex amplitude. Since probabilities add up to 1, we can say that

$$|\alpha|^2 + |\beta|^2 = 1 $$
This is called normalization which captures the probabilistic thinking in QM. Now, we know that measurement of the system collapses the system into one of it's states along which we are measuring. So, on measuring along the ${\{|0>, |1>}\}$ basis, the system collapses into $|0>$ with probability $|\alpha|^2$ and $|1>$ with probability$ $\ |\beta|^2$

(Representing the qubits by $|0>$ and $|1>$ is especially helpful while doing quantum information as it gives us a way to encode the fact that they represent bits 0 and 1 respectively. But this notation also captures the fact that the qubit is a much more complex object than the classical bit.)
# Visualization
Now let us try to visualize these states. Since there are two complex amplitutes, we can represent them as a column vector with 2 entries 
$$\alpha |0> +\beta |1> =  \begin{pmatrix} \alpha\\ \beta \\ \end{pmatrix}$$
This representation tells us that $$|0> = \begin{pmatrix} 1 \\ 0 \\ \end{pmatrix} when \ \alpha=1 \ and \  \beta = 0$$ and $$|1> = \begin{pmatrix} 0 \\ 1 \\ \end{pmatrix} when \ \alpha=0 \ and \  \beta = 1$$
Notice that this tells us a few things about the states. 
* They are linearly independent meaning that for the state to be 0, we need each of the coefficients to be 0. 
* They are orthogonal meaning that under the usual definition of inner product in the 2-D complex plane, we find that these states have a inner product of 0. 
* We also see that these two states can span the entire space. 

Hence we call such states to be orthonormal basis states. (A basis set is a set of linearly independent vectors which span the vector space. A vector space can have any number of basis sets.) 

# Measurement
Now what does it mean to measure the qubit? Let us say we have a state $$|\psi> = \begin{pmatrix} cos\theta \\ sin\theta \\ \end{pmatrix}$$
which makes an angle of $\theta$ with the $|0>$ state. Now let us make an very large number of qubits which are prepared to be at the above state and measure these qubits. When we measure them, the qubit makes up it's mind as to which state it wants to be and we find $cos^2\theta$ fraction of the qubits at the ground state and $sin^2\theta$ fraction of the qubits at the excited state. 

Note that measurement of a system can be done in an arbitary basis ('basis' because we generally wish to know all the information of the system, however measuremnt can also be done in any set) In the above case the measurement was done on the $|0>$ and$|1>$ basis. Now let us chose another basis ${\{|+>, |->}\}$ as $$|+> = \frac{1}{\sqrt 2}(|0>+|1>)$$ and
$$|-> = \frac{1}{\sqrt 2}(|0>-|1>)$$You can quickly verify that this does corresponds to a basis, since it is linearly independent, and spans the vector space. As a bonus we also find that this basis is aslo orthogonal since the inner product corresponds to 0. 