## Integration of a Mathematical Calulations with a Chat Completion System using LLM Function-Calling

## NAME: POORNIMA J
## REG NO : 212225040303
### AIM:
To design and implement a Python function for calculating the volume of a cube, integrate it with a chat completion system utilizing the function-calling feature of a large language model (LLM).

### PROBLEM STATEMENT:
To develop a Python program that calculates the volume of a cube using its radius . The program demonstrates the function-calling workflow by passing arguments to the function, executing the calculation, and displaying the result in a chat-style response.

### DESIGN STEPS:

#### STEP 1:
Import the required Python library and define a function to calculate the volume of a cube using the formula:

Volume = π × radius^3 x (4/3)

#### STEP 2:

Define a function-call structure containing the function name, radius. This represents the arguments that an LLM would provide.

#### STEP 3:

Execute the Python function using the supplied arguments and display the calculated volume as a natural-language response.

### PROGRAM:

```
import math
import json

def calculate_cube_volume(radius):
    volume = math.pi * (4/3) * radius * radius * radius 
    return volume

tools = {
    "name": "calculate_cube_volume",
    "description": "Calculate the volume of a cube",
    "parameters": {
        "radius": "number"
    }
}

print(tools)

function_call = {
    "name": "calculate_cube_volume",
    "arguments": {
        "radius": 5
    }
}

print("Function name:", function_call["name"])
print("Arguments:", function_call["arguments"])

if function_call["name"] == "calculate_cube_volume":
    args = function_call["arguments"]

    result = calculate_cube_volume(
        args["radius"]
    )

    print("Volume of cube:", round(result, 2))

final_response = (
    f"The volume of the cube with radius "
    f"{args['radius']}  "
    f"is {result:.2f} cubic units."
)

print(final_response)


```

### OUTPUT:


<img width="417" height="440" alt="image" src="https://github.com/user-attachments/assets/61ccead6-cee0-4492-97e9-a804763b92e7" />


### RESULT:
Thus , the Python function for calculating the volume of a cube is executed successfully.
