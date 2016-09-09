# Build steps using TDM-GCC-32
1. gcc -c -DGDT_TABLE_DLL char_buffer.c gdt_index.c gdt_table.c
2. gcc -shared -o libgdt.dll char_buffer.o gdt_index.o gdt_table.o
3. Copy libgdt.dll to package.cpath
4. Copy *.lua to package.path
5. Run LuaJIT
  - g = require('gdt')
  - require('gdt-parse-csv')
  - g.read_csv('exam.csv')

# Build steps using msys2 with mingw32-i686
1. gcc -c -DGDT_TABLE_DLL char_buffer.c gdt_index.c gdt_table.c
2. gcc -shared -o libgdt.dll char_buffer.o gdt_index.o gdt_table.o
3. Copy libgdt.dll, libgcc_s_dw2-1.dll, libwinpthread-1.dll to package.cpath
4. Copy *.lua to package.path
5. Run LuaJIT
  - g = require('gdt')
  - require('gdt-parse-csv')
  - g.read_csv('exam.csv')