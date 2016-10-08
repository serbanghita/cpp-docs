---
title: "String  (C++ Component Extensions)"
ms.custom: na
ms.date: 10/03/2016
ms.devlang: 
  - C++
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - devlang-cpp
ms.tgt_pltfrm: na
ms.topic: language-reference
ms.assetid: c695f965-9be0-4e20-9661-373bfee6557e
caps.latest.revision: 17
manager: ghogen
translation.priority.ht: 
  - cs-cz
  - de-de
  - es-es
  - fr-fr
  - it-it
  - ja-jp
  - ko-kr
  - pl-pl
  - pt-br
  - ru-ru
  - tr-tr
  - zh-cn
  - zh-tw
---
# String  (C++ Component Extensions)
The Visual C++ compiler supports *strings*, which are objects that represent text as a sequence of characters. Visual C++ supports string variables, whose value is implicit, and literals, whose value is an explicit quoted string.  
  
## All Runtimes  
 The Windows Runtime and common language runtime represent strings as objects whose allocated memory is managed automatically. That is, you are not required to explicitly discard the memory for a string when the string variable goes out of scope or your application ends. To indicate that the lifetime of a string object is to be managed automatically, declare the string type with the [handle-to-object (^)](../VS_visualcpp/Handle-to-Object-Operator--^----C---Component-Extensions-.md) modifier.  
  
## Windows Runtime  
 The Windows Runtime architecture requires Visual C++ to implement the `String` data type in the `Platform` namespace. For your convenience, Visual C++ also provides the `string` data type, which is a synonym for `Platform::String`, in the `default` namespace.  
  
### Syntax  
  
```cpp  
  
// compile with /ZW  
using namespace Platform;  
using namespace default;  
   Platform::String^ MyString1 = "The quick brown fox";  
   String^ MyString2 = "jumped over the lazy dog.";  
   String^ MyString3 = "Hello, world!";  
  
```  
  
### Remarks  
 For more information and examples about strings, see [Platform::String, std::wstring, and Literals (Platform)](assetId:///ec92fbc6-edf3-4137-a85e-8e29bdb857a8)  
  
### Requirements  
 Compiler option: **/ZW**  
  
## Common Language Runtime  
 This topic discusses how the Visual C++ compiler processes string literals when you run it by using the **/clr** compiler option. To use **/clr**, you must also use the common language runtime (CLR), C++/CLI syntax and managed objects. For more information about **/clr**, see [/clr (Common Language Runtime Compilation)](../VS_visualcpp/-clr--Common-Language-Runtime-Compilation-.md).  
  
 When compiling with **/clr**, the compiler will convert string literals to strings of type <xref:System.String?qualifyHint=False>. To preserve backward compatibility with existing code there are two exceptions to this:  
  
-   Exception handling. When a string literal is thrown, the compiler will catch it as a string literal.  
  
-   Template deduction. When a string literal is passed as a template argument, the compiler will not convert it to a <xref:System.String?qualifyHint=False>. Note, string literals passed as a generic argument will be promoted to <xref:System.String?qualifyHint=False>.  
  
 The compiler also has built-in support for three operators, which you can override to customize their behavior:  
  
-   System::String ^ operator +( System::String, System::String);  
  
-   System::String ^ operator +( System::Object, System::String);  
  
-   System::String ^ operator +( System::String, System::Object);  
  
 When passed a <xref:System.String?qualifyHint=False>, the compiler will box, if necessary, and then concatenate the object (with ToString) with the string.  
  
 When compiling with **/clr:oldSyntax**, string literals will not be converted to <xref:System.String?qualifyHint=False>.  
  
> [!NOTE]
>  The caret ("^") indicates that the declared variable is a handle to a C++/CLI managed object.  
  
 For more information see [String and Character Literals](../VS_visualcpp/String-and-Character-Literals---C---.md).  
  
### Requirements  
 Compiler option: **/clr**  
  
### Examples  
 **Example**  
  
 The following code example demonstrates concatenating and comparing strings.  
  
```cpp  
// string_operators.cpp  
// compile with: /clr  
// In the following code, the caret ("^") indicates that the   
// declared variable is a handle to a C++/CLI managed object.  
using namespace System;  
  
int main() {  
   String ^ a = gcnew String("abc");  
   String ^ b = "def";   // same as gcnew form  
   Object ^ c = gcnew String("ghi");  
  
   char d[100] = "abc";  
  
   // variables of System::String returning a System::String  
   Console::WriteLine(a + b);  
   Console::WriteLine(a + c);  
   Console::WriteLine(c + a);  
  
   // accessing a character in the string  
   Console::WriteLine(a[2]);  
  
   // concatenation of three System::Strings  
   Console::WriteLine(a + b + c);  
  
   // concatenation of a System::String and string literal  
   Console::WriteLine(a + "zzz");  
  
   // you can append to a System::String ^  
   Console::WriteLine(a + 1);  
   Console::WriteLine(a + 'a');  
   Console::WriteLine(a + 3.1);  
  
   // test System::String ^ for equality  
   a += b;  
   Console::WriteLine(a);  
   a = b;  
   if (a == b)  
      Console::WriteLine("a and b are equal");  
  
   a = "abc";  
   if (a != b)  
      Console::WriteLine("a and b are not equal");  
  
   // System:String ^ and tracking reference  
   String^% rstr1 = a;  
   Console::WriteLine(rstr1);  
  
   // testing an empty System::String ^  
   String ^ n;  
   if (n == nullptr)  
      Console::WriteLine("n is empty");  
}  
```  
  
 **Output**  
  
 **abcdef**   
 **abcghi**   
 **ghiabc**   
 **c**   
 **abcdefghi**   
 **abczzz**   
 **abc1**   
 **abc97**   
 **abc3.1**   
 **abcdef**   
 **a and b are equal**   
 **a and b are not equal**   
 **abc**   
 **n is empty** **Example**  
  
 The following sample shows that you can overload the compiler-provided operators, and that the compiler will find a function overload based on the <xref:System.String?qualifyHint=False> type.  
  
```cpp  
// string_operators_2.cpp  
// compile with: /clr  
using namespace System;  
  
// a string^ overload will be favored when calling with a String  
void Test_Overload(const char * a) {   
   Console::WriteLine("const char * a");   
}  
void Test_Overload(String ^ a) {   
   Console::WriteLine("String ^ a");   
}  
  
// overload will be called instead of compiler defined operator  
String ^ operator +(String ^ a, String ^ b) {  
   return ("overloaded +(String ^ a, String ^ b)");  
}  
  
// overload will be called instead of compiler defined operator  
String ^ operator +(Object ^ a, String ^ b) {  
   return ("overloaded +(Object ^ a, String ^ b)");  
}  
  
// overload will be called instead of compiler defined operator  
String ^ operator +(String ^ a, Object ^ b) {  
   return ("overloaded +(String ^ a, Object ^ b)");  
}  
  
int main() {  
   String ^ a = gcnew String("abc");  
   String ^ b = "def";   // same as gcnew form  
   Object ^ c = gcnew String("ghi");  
  
   char d[100] = "abc";  
  
   Console::WriteLine(a + b);  
   Console::WriteLine(a + c);  
   Console::WriteLine(c + a);  
  
   Test_Overload("hello");  
   Test_Overload(d);  
}  
```  
  
 **Output**  
  
 **overloaded +(String ^ a, String ^ b)**   
 **overloaded +(String ^ a, Object ^ b)**   
 **overloaded +(Object ^ a, String ^ b)**   
 **String ^ a**   
 **const char \* a** **Example**  
  
 The following sample shows that the compiler distinguishes between native strings and <xref:System.String?qualifyHint=False> strings.  
  
```cpp  
// string_operators_3.cpp  
// compile with: /clr  
using namespace System;  
int func() {  
   throw "simple string";   // const char *  
};  
  
int func2() {  
   throw "string" + "string";   // returns System::String  
};  
  
template<typename T>  
void func3(T t) {  
   Console::WriteLine(T::typeid);  
}  
  
int main() {  
   try {  
      func();  
   }  
   catch(char * e) {  
      Console::WriteLine("char *");  
   }  
  
   try {  
      func2();  
   }  
   catch(String^ str) {  
      Console::WriteLine("String^ str");  
   }  
  
   func3("string");   // const char *  
   func3("string" + "string");   // returns System::String  
}  
```  
  
 **Output**  
  
 **char \***   
 **String^ str**   
 **System.SByte\***   
 **System.String**   
## See Also  
 [Component Extensions for Runtime Platforms](../VS_visualcpp/Component-Extensions-for-Runtime-Platforms.md)   
 [String and Character Literals](../VS_visualcpp/String-and-Character-Literals---C---.md)   
 [/clr (Common Language Runtime Compilation)](../VS_visualcpp/-clr--Common-Language-Runtime-Compilation-.md)