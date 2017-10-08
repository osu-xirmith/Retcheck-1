# Retcheck Bypass by -Diesoin-#2024
Code:
```cpp
void Retcheck(int Address, BYTE sBYTE) { //Shrapner-#2024 / -Diesoin-#2024 Retcheck
	DWORD nOldProtect;
	VirtualProtect((void*)Address, 5, PAGE_EXECUTE_READWRITE, &nOldProtect);
	*(BYTE*)Address = sBYTE;
	VirtualProtect((void*)Address, 5, nOldProtect, &nOldProtect);
}
```
This is based on Variables Retcheck. His explanation of his Retcheck Bypass is here : https://v3rmillion.net/showthread.php?tid=148727
I recommend you to read this to find out more, it is a great thread to learn from.

This would be a way would use this Retcheck Bypass. First you need to define the according to Variables thread, the 'offsetting bs'. This would be shown as

```cpp
#define getaddy(X) (X - 0x400000 + (int)GetModuleHandle(0))
```

Then after you had defined the getaddy, this would be lua_getfield (example, ):
```cpp
void getfield(int L, int idx, const char *k) {
 Retcheck((int*)getaddy(GETFIELD_ADDRESS), 0xEB); // lol memes
 lua_getfield(L, idx, f);
 Retcheck((int*)getaddy(GETFIELD_ADDRESS), 0x72); 
}
```



Remember that this is based on Variable's Amazing Retcheck.
