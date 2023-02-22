# Quantum Teleportation with Qiskit on a Simulated and a Real Quantum Computer
We illustrate how to perform the quantum teleportation of one qubit using Qiskit. We do it on an ideal simulated quantum computer, a simulated quantum computer with noise and a real quantum computer from the IBM Quantum Experience.


# Quantum teleportation protocol:

Assuming Alice wants to share the qubit
$$ \alpha|0\rangle + \beta|1\rangle $$ with Bob the protocol is the following:

- Alice y Bob ask Carol to create 2 entangled qubits 

- Carol sends one of the entangled qubits to Alice and the other to Bob

- Let's call $q_0$ to $$ |\psi\rangle$, $q_1$ to the entangled qubit passeded by Alice and $q_2$ to the entangled qubit passeded by Bob

Para prósitos del circuito cuántico que haremos, vamos a llamar 𝑞0 a |𝜓⟩, 𝑞1 al qubit entrelazado de Alice y 𝑞2 al qubit entrelazado de Bob

- Alice applys a CNOT gate to her two qubits $q_1q_0$

- Alice applys a Haddamard gate to gate to her qubit $q_0$

- Alice measures  her two qubis and sends the results to Bob using a classical channel


- Bob receives the two bits $𝐶_1𝐶_0$ and depending on their values takes the following actions
```
If 𝐶1𝐶0=00 does nothing
If 𝐶1𝐶0=01 applys a Z gate to his qubit 
If 𝐶1𝐶0=10 applys a X gate to his qubit 
If 𝐶1𝐶0=11 applys a X gate followed by a Z gate to his qubit 
```
- Now Bob´s qubit 
$$e^{-\frac{t}{RC}}$$

- $q_2$ is identical to $$ |\psi\rangle$. 



## Usage

- Clone the repository with git clone https://github.com/lvillasen/Teleportacion-Cuantica.git
 
- Copy the jupyter notebook to a Google Drive
 
- Use any web explorer to open the notebook with Google Colab
