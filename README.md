# Quantum Teleportation with Qiskit 
We illustrate how to perform the quantum teleportation of one qubit using Qiskit. We do it on an ideal simulated quantum computer, a simulated quantum computer with noise and a real quantum computer from the IBM Quantum Experience.


## Quantum teleportation protocol:

Assuming Alice wants to share the qubit
$|\psi\rangle=\alpha|0\rangle + \beta|1\rangle$ with Bob, they can do the following protocol:

- Alice y Bob ask Carol to create 2 entangled qubits 

- Carol sends one of the entangled qubits to Alice and the other to Bob

- Let's call $q_0$ to $|\psi\rangle$, $q_1$ to the entangled qubit possesed by Alice and $q_2$ to the entangled qubit possesed by Bob

- Alice applies a CNOT gate to her two qubits $q_1q_0$

- Alice applies a Hadamard gate to gate to her qubit $q_0$

- Alice measures her two qubis and sends the results to Bob using a classical channel


- Bob receives the two bits $𝐶_1𝐶_0$ and depending on their values takes the following actions
```
If 𝐶1𝐶0=00 does nothing
If 𝐶1𝐶0=01 applies a Z gate to his qubit 
If 𝐶1𝐶0=10 applies a X gate to his qubit 
If 𝐶1𝐶0=11 applies a X gate followed by a Z gate to his qubit 
```

- At this point Bob´s qubit $q_2$ is identical to $|\psi\rangle$. 

##  Mathematics of Quantum Teleportation


- Alice wants to share her qubit 

$$ \alpha|0\rangle + \beta|1\rangle $$

- The entangled qubits produced by Carol are 

$$  \frac{1}{\sqrt{2}} (|00\rangle + |11\rangle) $$

- Alice gets the rightmost qubit of the entangled pair and Bob the leftmost qubit  so that the quantum state of the three qubits is

$$ \begin{align*}
\frac{1}{\sqrt{2}} (|00\rangle + |11\rangle)\otimes ( \alpha|0\rangle+ \beta |1\rangle \\
&= \frac{1}{\sqrt{2}} (\alpha|000\rangle + \alpha|110\rangle + \beta|001\rangle + \beta|111\rangle) 
\end{align*}$$

- Let´s recall that 

$$ CNOT \ket{00}= \ket{00}$$

$$ CNOT \ket{01}= \ket{11}$$

$$ CNOT \ket{10}= \ket{10}$$

$$ CNOT \ket{11}= \ket{01}$$


- Following the protocol, Alice applies a CNOT gate to het 2 qubits  $𝑞_1𝑞_0$ and a Hadamard gate to qubit  $𝑞_0$. 

resulting in the state

$$ 
\begin{align*} (I \otimes I \otimes H) (I \otimes CNOT) \frac{1}{\sqrt{2}} (\alpha|000\rangle + \alpha|110\rangle + \beta|001\rangle + \beta|111\rangle) \\
&= (I \otimes I \otimes H) \frac{1}{\sqrt{2}} (\alpha|000\rangle + \alpha|110\rangle + \beta|011\rangle + \beta|101\rangle) \\
&= \frac{1}{2}  (\alpha(|000\rangle + |001\rangle + |110\rangle + |111\rangle) + \beta(|010\rangle - |011\rangle + |100\rangle - |101\rangle)) \\
\end{align*}
$$

that we can rewrite as

$$
\frac{1}{2}( (\alpha|0\rangle + \beta|1\rangle)\otimes|00\rangle  
+ (\alpha|1\rangle - \beta|0\rangle)\otimes|01\rangle   + (\alpha|1\rangle + \beta|0\rangle)\otimes|10\rangle  
 + (\alpha|1\rangle - \beta|0\rangle)\otimes|11\rangle  )
$$

- Next Alice measures her two qubits and sends the result $C_1C_0$ to Bob through a classical channel,
in consequence Bob´s qubit will transform into one of the four states:

$$|00\rangle \rightarrow (\alpha|0\rangle + \beta|1\rangle)$$

$$|01\rangle \rightarrow (\alpha|1\rangle - \beta|0\rangle)$$

$$|10\rangle \rightarrow (\alpha|1\rangle + \beta|0\rangle)$$

$$|11\rangle \rightarrow (\alpha|1\rangle - \beta|0\rangle)$$

- Let´s recall that

$$ X \ket{0} = \ket{1}$$
$$ X \ket{1} = \ket{0}$$

and


$$ Z \ket{0}= \ket{0} $$
$$ Z \ket{1}= -\ket{1} $$


- Next Bob does the following with his qubit:

```
If 𝐶1𝐶0=00 Bob does nothing
If 𝐶1𝐶0=01 Bob applies a Z gate to his qubit 
If 𝐶1𝐶0=10 Bob applies a X gate to his qubit 
If 𝐶1𝐶0=11 Bob applies a X gate followed by a Z gate to his qubit 
```

- At this point Bob´s qubit will be

$$|q_2\rangle= \alpha|0\rangle + \beta|1\rangle$$


## Usage

- Clone the repository with git clone https://github.com/lvillasen/Teleportacion-Cuantica.git
 
- Copy the jupyter notebook to a Google Drive
 
- Use any web explorer to open the notebook with Google Colab
