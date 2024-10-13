# Burma Q - Myanmarsar SDK for Quantum Computing

![cover photo](Screen%20Shot%202024-10-13%20at%2022.51.11.png)

Burma Q is the first SDK that translates Myanmarsar (Burmese language) quantum computing instructions into code using various quantum computing frameworks. It leverages the capabilities of **OpenAI**, **Cirq**, **Qiskit**, **PennyLane**, and **PyQuil**, allowing Myanmar developers and researchers to work seamlessly with quantum technologies in their native language.

## Requirements

To use the SDK, install the following packages:

- `openai`
- `cirq`
- `qiskit`
- `pennylane`
- `pyquil`

### Installation
```bash
pip install openai cirq qiskit pennylane pyquil 

## Quick Start


```python
import openai
import cirq
import qiskit
import pennylane as qml
from pyquil import Program

# Set your OpenAI API key
openai.api_key = "<YOUR_OPENAI_API_KEY>"

## Translation and Execution

The following functions will help you translate quantum instructions in Myanmar language into quantum code and execute it.

---

### Function to Translate Myanmar Instruction to Quantum Code

```python
def translate_myanmar_to_code(myanmar_instruction):
    response = openai.Completion.create(
        engine="text-davinci-003",
        prompt=f"Translate the following instruction in Myanmar language to a Quantum Computing code snippet (Cirq, Qiskit, etc.): {myanmar_instruction}",
        max_tokens=300,
        temperature=0.5,
        n=1,
        stop=None,
    )
    code = response.choices[0].text.strip()
    return code


