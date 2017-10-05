# Retcheck Bypass by -Diesoin-#2024
Code:
```cpp
void Retcheck(int Address, BYTE* sBYTE) { //Shrapner-#2024 / -Diesoin-#2024 Retcheck
 DWORD o_buff;
 VirtualProtect((void*)Address, 5, PAGE_EXECUTE_READWRITE, &o_buff);
 *(char*)addr = sBYTE;
 VirtualProtect((void*)Address, 5, o_buff, &o_buff);
}
```
This is based on Variables Retcheck. His explanation of his Retcheck Bypass is here : https://v3rmillion.net/showthread.php?tid=148727
I recommend you to read this to find out more, it is a great thread to learn from.

This would be a way would use this Retcheck Bypass :
```cpp
// Got to go, Will create this part later :)
```

Remember that this is based on Variable's Amazing Retcheck.
