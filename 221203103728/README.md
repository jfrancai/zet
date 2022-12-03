## Effective C++: 55 Specific Ways to Improve Your Programs and Designs


### Chapter 1: Accustoming Yourself to C++

---

**Item 1: View C++ as a federation of languages.**

Today’s C++ is a multiparadigm programming language, one supporting a combination of procedural, object-oriented, functional, generic,
and metaprogramming features : C, Object-Oriented C++, Template C++, The STL.

> **Things to Remember** 
> * Rules for effective C++ programming vary, depending on the part of C++ you are using.

---

**Item 2: Prefer consts, enums, and inlines to #defines.**

* Constructors declared explicit are usually preferable to non-explicit
ones.

* Rules for effective C++ programming vary, depending on the part of
C++ you are using.

* Prefer the compiler to preprocessor.

* Symbol Table is an important data structure created and maintained by the compiler in order to keep track of semantics of variable (scope, names, instances, classes, objects etc.)

* But still #include remains essential, and #ifdef/#ifndef continue to play important roles in controlling compilation. 

> **Things to Remember** 
> * For simple constants, prefer const objects or enums to #defines.
> * For function-like macros, prefer inline functions to #defines.

---

**Item 3: Use const whenever possible.**

```cpp
char greeting[] = "Hello";
char *p = greeting; // non-const pointer, non-const data
const char *p = greeting; // non-const pointer, const data
char * const p = greeting; // const pointer, non-const data
const char * const p = greeting; // const pointer, const data
```

```cpp
std::vector<int>::const_iterator iter; // iter acts like a T* const
const std::vector<int>::iterator cIter; // cIter acts like a const T*
```

```cpp
class TextBlock {
	public:
		...
		const char& operator[](std::size_t position) const
		{
			...
			...
			...
			return text[position];
		}

		char& operator[](std::size_t position) // now just calls const op[]
		{
			return (
				const_cast<char&>( // cast away const on op[]’s return type;
					static_cast<const TextBlock&>(*this) // add const to *this’s type;
					[position] // call const version of op[]
				)
			);
		}
	...
};
```

> **Things to Remember**
> * Declaring something const helps compilers detect usage errors. const can be applied to objects at any scope, to function parameters and return types, and to member functions as a whole.
> * Compilers enforce bitwise constness, but you should program using logical constness (see mutable specifier).
> * When const and non-const member functions have essentially identical implementations, code duplication can be avoided by having the non-const version call the const version.

---

**Item 4: Make sure that objects are initialized before they’re used.**

> **Things to Remember**
> * Manually initialize objects of built-in type, because C++ only sometimes initializes them itself.
> * In a constructor, prefer use of the member initialization list to assignment inside the body of the constructor. List data members in the initialization list in the same order they’re declared in the class.
> * Avoid initialization order problems across translation units by replacing non-local static objects with local static objects.

---

### Chapter 2: Construtors, Destructors, and Assignment Operators

---

**Item 5: Know what functions C++ silently writes and calls.**

> **Things to Remember**
> * Compilers may implicitly generate a class’s default constructor, copy constructor, copy assignment operator, and destructor.

---

**Item 6: Explicitly disallow the use of compilergenerated functions you do not want.**

> **Things to Remember**
> *To disallow functionality automatically provided by compilers, declare the corresponding member functions private and give no implementations. Using a base class like Uncopyable is one way to do this

---

**Item 7: Declare destructors virtual in polymorphic base classes.**

---

**Item 20: Prefer pass-by-reference-to-const to pass-byvalue.**

```cpp
bool validateStudent(Student s); // function taking a Student by value

bool validateStudent(const Student& s); // function taking a Student by reference
```

```cpp
class Window {
	public:
		...
		std::string name() const; // return name of window
		virtual void display() const; // draw window and contents
};

class WindowWithScrollBars: public Window {
	public:
		...
		virtual void display() const;
};

void printNameAndDisplay(Window w) // incorrect! parameter may be sliced!
{
	std::cout << w.name();
	w.display();
}

WindowWithScrollBars wwsb;
printNameAndDisplay(wwsb); //will behave as a Window inside printNameAndDisplay : slicing
```

> **Things to Remember**
> * Prefer pass-by-reference-to-const over pass-by-value. It’s typically more efficient and it avoids the slicing problem.
> *The rule doesn’t apply to built-in types and STL iterator and function object types. For them, pass-by-value is usually appropriate.

---

**Item 30: Understand the ins and outs of inlining.**

The ``inline`` keyword tells the compiler to substitute the code within the function definition for every instance of a function call.

A function defined entirely inside a class/struct/union definition, whether it's a member function or a non-member friend function, is implicitly an inline function.

> **Things to Remember** 
> * Limit most inlining to small, frequently called functions. This facilitates debugging and binary upgradability, minimizes potential code bloat, and maximizes the chances of greater program speed. 
> * Don’t declare function templates inline just because they appear in header files.

---

### Chapter 7: Templates and Generic Programming

---

**Item 41: Understand implicit interfaces and compiletime polymorphism.**

> **Things to Remember** 

---

**Item 53: Pay attention to compiler warnings.**
> **Things to Remember** 
> * Take compiler warnings seriously, and strive to compile warningfree at the maximum warning level supported by your compilers. 
> * Don’t become dependent on compiler warnings, because different compilers warn about different things. Porting to a new compiler may eliminate warning messages you’ve come to rely on.

---

```cpp
Widget w1; // invoke default constructor
Widget w2(w1); // invoke copy constructor
w1 = w2; // invoke copy assignment operator
Widget w3 = w2; // invoke copy constructor!
```

---

More details : [What Books to Read to Get Better In C++](https://www.fluentcpp.com/2017/07/28/what-books-to-read-to-get-better-at-c/)

    #c++ #readings
