## EX NO:12
# <p align="center">Huffman-Coding

## Aim
To implement Huffman coding to compress the data using Python.

## Software Required
1. Anaconda - Python 3

## Algorithm:

### Step1:
Get the input String.

### Step2:
Create tree nodes.

### Step3:
Main function to implement huffman coding.

### Step4:
Calculate frequency of occurrence.

### Step5:
Print the characters and its huffmancode.

## Program:

*/ Developed by:naveenkumar v
Register Number: 212221230068 /*


``` Python
# Get the input String
string = 'NAVEENKUMAR'
class NodeTree(object):
    def __init__(self, left=None, right=None): 
        self.left = left
        self.right=right
    def children(self):
        return (self.left,self.right)
        
# Create tree nodes
def huffman_code_tree (node, left=True, binString=''):
    if type(node) is str:
        return {node: binString}
    (l, r) = node.children()
    d = dict()
    d.update(huffman_code_tree (l, True, binString + '0'))
    d.update(huffman_code_tree (r, False, binString + '1'))
    return d
    
# Main function to implement huffman coding
freq = {}
for c in string:
    if c in freq:
        freq[c] += 1
    else:
        freq[c] = 1
freq = sorted(freq.items(), key=lambda x: x[1], reverse=True)
nodes=freq

# Calculate frequency of occurrence
while len(nodes)>1:
    (key1,c1)=nodes[-1]
    (key2,c2)=nodes[-2]
    nodes = nodes[:-2]
    node = NodeTree (key1, key2)
    nodes.append((node,c1 + c2))
    nodes = sorted (nodes, key=lambda x: x[1], reverse=True)
    
# Print the characters and its huffmancode
huffmanCode=huffman_code_tree(nodes[0][0])
print(' Char | Huffman code ') 
print('----------------------')
for (char, frequency) in freq:
    print('%-4r|%12s'%(char,huffmanCode[char]))
```

    
## Output:
 ![$2](https://github.com/Naveenvetrivel/Huffman-Coding/assets/94165322/89c4001f-0022-4e00-a0d0-aee1a1e8fa4d)


### Print the characters and its huffmancode
![$1](https://github.com/parsh2004/Huffman-Coding/assets/95388047/2d95a6e4-2eb7-4153-8bb0-deadc2887e0a)

## Result
Thus the huffman coding was implemented to compress the data using python programming.
