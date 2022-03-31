# Lab1 Learning Notes
## Lab 1: Compiling, Debugging, and Executing Design Using AC Data-types
### Learning Objectives
* 使用g++來compile & execute sdesign
* 知道如何include .h files
* 使用debug工具的方法
* 了解AC data-types的shift特性 
### 1.使用g++來compile & execute sdesign
* 使用附在資料夾中的Makefile
* Example: make tb0
### 2.知道如何include .h files
* 在文件的開頭加上: #include <ac_int.h>、#include <ac_fixed.h>
### 3.使用debug工具的方法
* 範例使用gdb工具進行debugging
* Example: make tb1_debug
* 詳細指令為: 
```
/usr/cad/mentor/Catapult/2022.1/Mgc_home/bin/g++ -o /usr/cad/mentor/Catapult/2022.1/Mgc_home/tmp/tb tb.cpp test_chan_assert.cpp -I/usr/cad/mentor/Catapult/2022.1/Mgc_home/shared/include -g
/usr/cad/mentor/Catapult/2022.1/Mgc_home/bin/gdb /usr/cad/mentor/Catapult/2022.1/Mgc_home/tmp/tb
```
* 其中開啟gdb的指令為第二行，其結構為: gdb ./test.out (即: gdb 可執行檔(.o))。
* 打開gdb後:按run開始執行design；按up可以往上trace問題點的位置。
### 4.了解AC dat-types的shift特性
* AC data-types的特性為: 
  * wrap: 超過最大值後會從最小值開始(實際上的值是最大值 + 顯示出來的值)；
  * saturate: 超過最大值後以最大值表示，即clip到最大值；
  * shift: 左移位的特性---MSB不見，LSB補0。
* 備註:若左移位後數字超過最大值也會有wrap的特性，此時要增大output variables的bit數一位。
  * Example: ac_int<4,false>改成ac_int<5,false>。         
### 5.Reference
* High-Level Synthesis Blue Book
* Catapult HLS Untimed C++ Training Labs
* The above mentioned materials are only available in the folders shiped with Catapult HLS Tools.

### 6.Notes
* This series is the learning notes for Catapult HLS design flow. 
* All the materials mentioned above  
