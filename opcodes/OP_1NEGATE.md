# OP_1NEGATE

:::info
**Opcode number:** 79  
**Byte representation:** `0x4f`  
**Other names:** `OP_PUSHNUM_NEG1`  
**Short Description:** Push the number -1 onto the stack.  
:::

The [`OP_1NEGATE`](./OP_1NEGATE.md) opcode will push `0x81` (representing -1 in the context of script execution) onto the stack. This opcode utilizes the [minimally encoded integers format](../script/numbers.md#minimally-encoded-integers).

## Examples
### Example 1
```shell
# ASM script
OP_1NEGATE OP_1NEGATE

# Raw script
4f4f

# Final stack
-1
-1
```

### Example 2
```shell
# ASM script
OP_8 OP_1NEGATE OP_ADD

# Raw script
584f93

# Final stack
7
```

In the first example, we have a script with two [`OP_1NEGATE`](./OP_1NEGATE.md) opcodes. After execution, we have two -1s on the stack. In the second example, we add another opcode, [`OP_ADD`](./OP_ADD.md), to the script. The [`OP_ADD`](./OP_ADD.md) opcode will remove the two top items from the stack, add them together, and then push the result back onto the stack. 8 + (-1) results in 7, which is then pushed onto the stack.
