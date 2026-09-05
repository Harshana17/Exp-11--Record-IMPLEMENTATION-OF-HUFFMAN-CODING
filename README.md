# Exp-11--Record-IMPLEMENTATION-OF-HUFFMAN-CODING

## Name : HARSHANA M V

## Reg no : 212224240053

### Aim

To implement Huffman coding to compress the data using Python.

## Software Required

Anaconda - Python 3.7

# Algorithm:

# Step1:

Get the input string.

# Step2:

Create tree nodes.

# Step3:

Main function to implement huffman coding.

# Step4:

calculate frequency of occurence.

# Step5:

print the characters and its huffmancode.

# Program:
```
input_string = "harshana"  # Example input string

frequency = {}
for char in input_string:
    if char in frequency:
        frequency[char] += 1
    else:
        frequency[char] = 1

nodes = [[char, freq] for char, freq in frequency.items()]

while len(nodes) > 1:
   
    nodes = sorted(nodes, key=lambda x: x[1])

    # Pick two smallest nodes
    left = nodes.pop(0)
    right = nodes.pop(0)

    
    new_node = [[left, right], left[1] + right[1]]
    nodes.append(new_node)

huffman_tree = nodes[0]

huffman_codes = {}

def generate_codes(tree, code=""):
    if isinstance(tree[0], str):  # If it's a leaf node
        huffman_codes[tree[0]] = code
    else:  # If it's an internal node, recurse
        generate_codes(tree[0][0], code + "0")
        generate_codes(tree[0][1], code + "1")

generate_codes(huffman_tree)

print("Character | Jones syndicate")
print("-------------------------")
for char, code in huffman_codes.items():
    print(f"    {char}    |    {code}")
```

# Output:

<img width="532" height="352" alt="image" src="https://github.com/user-attachments/assets/dd2b5175-16bb-4354-b19b-609e959ad336" />

# Result

Thus the huffman coding was implemented to compress the data using python programming.
