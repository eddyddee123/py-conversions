# py-conversions
Conversions between different formats in Python

## Summary

|From ↓ To →|charstr|bytes|hexstr|binstr|int|
|:----------|:------|:----|:-----|:-----|:--|
|S charstr||`bytes(S, encoding=’utf-8’)`|`bytes(S, encoding=’utf-8’).hex()`|`f"{int(bytes(S, encoding='utf-8').hex(), base=16):b}"`|`int(bytes(S, encoding='utf-8').hex(), base=16)`|
|BY bytes|`BY.decode()`||`BY.hex()`|`f'{int(BY.hex(), base=16):b}'`|`int(BY.hex(), base=16)` OR `int.from_bytes(BY, byteorder='big')`|
|H hexstr|`bytes.fromhex(H).decode()`|`bytes.fromhex(H)`||`f'{int(H, base=16):b}'`|`int(H, base=16)`|
|B binstr|`bytes.fromhex(f'{int(B, base=2):x}').decode()`|`bytes.fromhex(f '{int(B, base=2):x}')`|`f'{int(B, base=2):x}'`||`int(B, base=2)`|
|I int|`bytes.fromhex(f'{I:x}').decode()`|`bytes.fromhex(f'{I:02x}')` OR `I.to_bytes((I.bit_length()+7)//8, 'big')`|`f'{I:x}'`|`f'{I:b}'`||

## Examples
[Jupyter notebook](BinaryHexASCIIetc.ipynb)
