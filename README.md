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

Quick Start
Import the necessary libraries and set your OpenAI API key:

python
Copy code
import openai
import cirq
import qiskit
import pennylane as qml
from pyquil import Program

# Set your OpenAI API key
openai.api_key = "<YOUR_OPENAI_API_KEY>"
Translation and Execution
The following functions will help you translate quantum instructions in the Myanmar language into quantum code and execute it.

python
Copy code
# Translate Myanmar instruction to quantum code
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

# Execute the quantum code without showing the code itself
def execute_quantum_code_without_showing(code):
    try:
        exec_globals = {}
        exec_locals = {}
        exec(code, exec_globals, exec_locals)
        
        result = exec_locals.get('result', 'Output not available')
        return str(result)
    except Exception as e:
        return f"Error in execution: {str(e)}"
Sample Instructions
Here are some sample quantum instructions in Myanmar language and how to use the SDK to process them:

CNOT Gate Operation

Instruction in Myanmar:

"CNOT gate ကို အသုံးပြု၍ Qubit နှစ်ခုမှာ Quantum Gate operation တစ်ခု ဖန်တီးပါ။"

Python Code Translation:

python
Copy code
myanmar_instruction = "CNOT gate ကို အသုံးပြု၍ Qubit နှစ်ခုမှာ Quantum Gate operation တစ်ခု ဖန်တီးပါ။"
code = translate_myanmar_to_code(myanmar_instruction)
print("Translated Code:", code)
result = execute_quantum_code_without_showing(code)
print("Execution Result:", result)
Hadamard Gate Superposition

Instruction in Myanmar:

"Hadamard Gate ကို အသုံးပြု၍ Qubit တစ်ခုကို Superposition များအဖြစ် ဖန်တီးပါ။"

Python Code Translation:

python
Copy code
myanmar_instruction = "Hadamard Gate ကို အသုံးပြု၍ Qubit တစ်ခုကို Superposition များအဖြစ် ဖန်တီးပါ။"
code = translate_myanmar_to_code(myanmar_instruction)
print("Translated Code:", code)
result = execute_quantum_code_without_showing(code)
print("Execution Result:", result)

