# Abstract classes and interfaces

* Pure virtual function

```cpp
virtual int area() = 0; // pure virtual function
```

> Classes that contain at least one pure virtual function are known as abstract base classes.

* Interfaces

```cpp
class ICoffeeMaker
{
	public:
		virtual void	filWaterTank(IWatersource *src) = 0;
		virtual ICoffee	*makecoffee(std::string const &type) = 0;
}
```
> Do not use attributs inside interfaces.

More details : [Abstract base classes](https://cplusplus.com/doc/tutorial/polymorphism/)

    #tags

