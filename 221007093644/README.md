# Intro to Upcast and Downcast

> reintrepretation

```cpp
#include <iostream>

class Parent{};
class Child1: public Parent{};
class Child2: public Parent{};

int	main(void)
{
	Child1	a;

	Parent	*b = &a;			// Impicit 'reinterpretation' cast
	Parent	*c = (Parent *) &a;	// Explicit 'reinterpretation' cast

	Parent	*d = &a;			// Implicit upcast OK
	Child1	*e = d;				// Implicit downcast no!
	Child2	*f = (Child2 *)d;	// Explicit downcast OK but no.

	return (0);
}
	Parent	*c = (Parent
```

More details : [topic]()

    #cpp #reinterpretation #cast
