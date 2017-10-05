# Retcheck
```cpp
void set_jb(unsigned int addr)
{
 DWORD o_buff;
 VirtualProtect((void*)addr, 5, PAGE_EXECUTE_READWRITE, &o_buff);
 *(char*)addr = 0xEB;
 VirtualProtect((void*)addr, 5, o_buff, &o_buff);
}
```
