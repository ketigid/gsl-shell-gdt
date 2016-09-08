# Build steps
1. Use msys2 with mingw32-i686
2. gcc -c -DGDT_TABLE_DLL char_buffer.c gdt_index.c gdt_table.c
3. gcc -shared -o libgdt.dll char_buffer.o gdt_index.o gdt_table.o
4. Copy libgdt.dll, libgcc_s_dw2-1.dll, libwinpthread-1.dll to package.cpath
5. Copy *.lua to package.path
6. Run LuaJIT
  - g = require('gdt')
  - require('gdt-parse-csv')
  - g.read_csv('exam.csv')