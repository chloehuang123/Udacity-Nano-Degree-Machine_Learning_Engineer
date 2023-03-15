# Lesson 01: 线性回归

# **Lesson 02:** 感知器算法

## Concept 06: 感知器

<img src="Images/Screenshot 2023-03-15 at 2.06.34 PM.png" alt="Screenshot 2023-03-15 at 2.06.34 PM" />

<img src="Images/Screenshot 2023-03-15 at 2.07.23 PM.png" alt="Screenshot 2023-03-15 at 2.07.23 PM" />

## Concept 07: 用感知器实现简单逻辑运算

### 逻辑运算感知器

在这节课，我们要用感知器实现简单的逻辑运算。你将会为最常见的逻辑运算符创建感知器： **AND** （与）、 **OR** （或） 和 **NOT** （非）。然后，我们将看看如何处理比较难的 **XOR** （异或）运算符。我们开始吧！

### 用感知器实现逻辑运算 - AND （“与”）

<img src="Images/Screenshot 2023-03-15 at 2.14.21 PM.png" alt="Screenshot 2023-03-15 at 2.14.21 PM" />

### AND 感知器的权重和偏差是什么？

将权重（ `weight1 `、 `weight2 `）和偏差 `bias `设为正确的值，以便如上所示地计算 AND 运算。

```python
import pandas as pd

# TODO: Set weight1, weight2, and bias
weight1 = 0.0
weight2 = 0.0
bias = 0.0


# DON'T CHANGE ANYTHING BELOW
# Inputs and outputs
test_inputs = [(0, 0), (0, 1), (1, 0), (1, 1)]
correct_outputs = [False, False, False, True]
outputs = []

# Generate and check output
for test_input, correct_output in zip(test_inputs, correct_outputs):
    linear_combination = weight1 * test_input[0] + weight2 * test_input[1] + bias
    output = int(linear_combination >= 0)
    is_correct_string = 'Yes' if output == correct_output else 'No'
    outputs.append([test_input[0], test_input[1], linear_combination, output, is_correct_string])

# Print output
num_wrong = len([output[4] for output in outputs if output[4] == 'No'])
output_frame = pd.DataFrame(outputs, columns=['Input 1', '  Input 2', '  Linear Combination', '  Activation Output', '  Is Correct'])
if not num_wrong:
    print('Nice!  You got it all correct.\n')
else:
    print('You got {} wrong.  Keep trying!\n'.format(num_wrong))
print(output_frame.to_string(index=False))
```

### 用感知器实现逻辑运算 - OR （“或”）

<img src="Images/Screenshot 2023-03-15 at 2.15.09 PM.png" alt="Screenshot 2023-03-15 at 2.15.09 PM" />

### 用感知器实现逻辑运算 - NOT （"非”）

和我们刚刚研究的其他感知器不一样，NOT 运算仅关心一个输入。如果输入是 `1 `，则运算返回 `0 `，如果输入是 `0 `，则返回 `1 `。感知器的其他输入被忽略了。



在此测验中，你将设置权重（ `weight1 `、 `weight2 `）和偏差 `bias `，以便对第二个输入进行 NOT 运算，并忽略第一个输入。

<img src="Images/Screenshot 2023-03-15 at 2.21.35 PM.png" alt="Screenshot 2023-03-15 at 2.21.35 PM" />