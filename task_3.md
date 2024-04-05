## Task III: Open Task 
Please comment on quantum computing or quantum machine learning. You can also comment on one quantum algorithm or one quantum software you are familiar with. You can also suggest methods you think are good and you would like to work on. Please use your own understanding. Comments copied from the internet will not be considered.



### Quantum Computing

Quantum computing is a very large field. In term of hardware, we have the many different types of qubit types i.e individual quantum objects like atoms, photons, electron spin, trapped ions, while each of those hardwares require deep knowledge in the material physics and engineering. Then there are the theories of quantum computing algorithms that is establishing the basis for quantum supremancy, developed in the mathematical physics and informatics domains. The algorithms could be segmented into the major pardigms of analog and digital quantum computers. When mentioning quantum computing, we would mostly associate with the digital approach of gate-based architecture, specifically that of superconducting qubits based on the Josephson effect used by IBM, Google, Intel, etc.

However, noise poses a significant challenge to quantum computing, enough to be the most cited doubt by critics. The development of logical qubits with quantum error correction codes become apparently important for many types of algorithms. The advancement in quantum computing can be categorized into two stages based on the number of qubits and their noise resistance: NISQ (Noisy Intermediate-Scale Quantum) and FTQC (Fault-Tolerant Quantum Computers). NISQ systems comprise from 50 to a few hundered noisy qubits and could be used for running algorithms with limited circuit depth, like variational quantum circuits. They are still expected to exceed supercomputers' capacities for certain specific problems. Then, much later, though hopefully in the next few decades, we will achieve FTQC systems, which have over 100 logical qubits (created by a large number of physical qubits and error correction), and enter the realm of true quantum supremancy!

For now though, in the current NISQ era, quantum machine learning is still one of the prominent topics, particularly involving algorithms based on a classical-quantum hybrid approach such as Variational Quantum Algorithms (VQA) or Variational Quantum Eigensolver (VQE). The algorithm would usually involve encoding data into quantum states, defining cost functions calculated using measurements from quantum systems, and optimizing parameters using classical functions.

The definition or scope of quantum machine learning remain somewhat ambiguous though. Different from other algorithms where quantum speedup is the main concern, assessment of quantum machine learning algorithms seems to focus more on comparing the quality of results, such as minimizing an error function. Nonetheless, the study of quantum machine learning has the potential to deepen our understanding of the underlying mathematics of quantum systems. While classical data encoding can be computationally expensive, I expect quantum machine learning to be particularly suited for learning patterns from data with inherent quantum properties.


### Another Type of Quantum Algorithm (Or Not)

In the next five tasks, we will be implementing quantum machine learning in the gate-based paradigm, primarily using Variational Quantum Algorithms (VQA) to optimize parameterized quantum circuits with classical software.

However, I'd like to briefly discuss a different paradigm than gate-based architecture, namely analog quantum computing, specifically quantum annealers such as those developed by D-Wave.

Quantum annealers operate based on the physics of adiabatic quantum processes. While there has been ongoing debate about whether quantum annealers can be considered quantum computers, as they are limited in certain quantum applications, their potential in other areas has been demonstrated.

Quadratic Unconstrained Binary Optimization (QUBO) is arguably the most fundamental application of quantum annealing. It can be reformulated as the Ising Hamiltonian with spin variables $s_i ∈ \{1,-1\}$ given by

$$
\min H(\mathbf{s})=-\sum_{i} h_i s_i-\sum_{i<j} J_{ij} s_i s_j,
$$
whereas $\mathbf{h}$ and $\mathbf{J}$ are called linear and quadratic biases, respectively. This formulation is found in many NP-hard combinatorical problem like Travelling Saleman Problem (TSP), which is usually tackled by metaheuristic algorithms like annealing. 

In quantum annealers, quantum fluctuations are utilized to search for ground state solutions of the encoded Hamiltonian. A transverse magnetic field is uniformly applied to the qubits and gradually decreased to control the evolution of the Ising model. D-Wave quantum annealers also allow users to specifying the Ising model to map to the hardware graph.

The application of efficiently modeling Ising problems could extend beyond optimization tasks though. For instance, Ising models find application in simulating physical systems and chemistry, accurately representing various phenomena. One other is applied to probabilistic graphical models like Markov Network, specifically Boltzmann Machine. Finally, while somewhat speculative, annealers could potentially excel in searching for minimal error configurations during the adjustment of weights in neural networks as they are good at finding the minimal energy states of complex systems. 