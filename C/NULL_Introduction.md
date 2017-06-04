「C」NULL空指標常數 (null pointer constant)<BR>
<BR>
在Ptt看到對於NULL的介紹，解了心中一個很大的惑<BR>
### 在C的情況(注意：C++不適用，C++的場合請看下一節) ###<BR>
<BR>
根據C11 standard 6.3.2.3 裡對空指標常數 (null pointer constant)的定義：<BR>
<BR>
An integer constant expression with the value 0, or such an expression cast<BR>
to type void *, is called a null pointer constant.<BR>
<BR>
NULL是空指標常數，代表計算結果為零的整數常數表達式，如 0 或 0ULL，<BR>
或是前述表達式轉型成 void*, 如 (void*)(0U)。<BR>
NULL是用MACRO定義，並由實作環境決定(implementation-defined)空指標常數。<BR>
對C來說，這兩種寫法都對：<BR>
<BR>
#define NULL ((void *)0)        // 一般C編譯器常見的寫法<BR>
                                // 這邊我個人補充一下很多Define我看到#define NULL (void*)0的寫法，會GG阿<BR>
#define NULL 0                  // 也是符合定義的寫法<BR>
<BR>
對C來說NULL空指標常數可以給任何一個左值<BR>
0         //給所有型態的指標用<BR>
((void*)0)//給所有型態的指標用<BR>
((int *)0)//整數指標用<BR>
<BR>
以下範例<BR>
<BR>
int *a = 0;           // 沒問題，空指標常數<BR>
int *b = (int*) 0;    // 沒問題，右邊是同型別的空指標<BR>
int *c = (void*) 0;   // C沒問題，右邊是空指標常數，不過C++會掛<BR>
int *d = (long*) 0;   // 會有warning提示 (incompatible pointer type)<BR>
int *e = (int*) a;    // C不保證是空指標，C++會掛<BR>
<BR>
<BR>
### 在C++的情況 ###<BR>
<BR>
根據C++14 standard 4.10 裡對空指標常數 (null pointer constant)的定義：<BR>
<BR>
A null pointer constant is an integer literal (2.13.2) with value zero<BR>
or (以後為C++11後特有) a prvalue of type std::nullptr_t.<BR>
<BR>
意思是說，它可以是0或nullptr，對C++來說，這兩種寫法都對：<BR>
這邊沒有((void*)0)，但也不是以nullptr取代，nullptr是一個新的形態<BR>
<BR>
#define NULL 0                  // C++03(或之前)的作法<BR>
#define NULL nullptr            // C++11(或之後)的可能作法<BR>
<BR>
至於以下的情況：<BR>
<BR>
int x = NULL;           // 絕對不要這樣寫，原因請看下文<BR>
int* ptr = (void*)0;    // C 沒問題，C++會掛<BR>
int* ptr = 0;           // C++03(或之前)與C都能用的作法<BR>
int* ptr = nullptr;     // C++11以後的正統用法，<BR>
                           也就是上述C++14 standard裡的空指標常數<BR>
<BR>
為啥我們不該寫出 int x = NULL 這種東西？<BR><BR>
因為C++有C沒有的函數重載(function overloading)，舉例來說<BR>
<BR>
void DoSomething(int x);<BR>
void DoSomething(char* x);<BR>
<BR>
NULL是用MACRO定義出來的，如果編譯器裡的NULL定義不一樣，<BR>
可能會有以下兩種狀況：<BR>
<BR>
- NULL = 0: DoSomething(NULL)會呼叫void DoSomething(int x)，即<BR>
            DoSomething(0)。<BR>
<BR>
- NULL=nullptr: 會呼叫void DoSomething(char* x)，即DoSomething(nullptr)。<BR>
<BR>
結論就是，C++開始還是儘量用0或nullptr*取代NULL吧。<BR>
C語言可以使用0 or NULL，因為我在C上常看到別人判斷空指標<BR>
<BR>
附上Ptt連結，看Ptt會比較清楚，維基上舉的例子太少會很混淆<BR>
<BR>
https://www.ptt.cc/man/C_and_CPP/DD8B/D362/M.1463129574.A.C74.html<BR>
