# Exceptions

* handlers
* try-block

```cpp
try
{
	throw -1;
}
catch (int e)
{
	std::cout << "error" << std::endl;
}
catch (...)
{
	std::cout << "default exception" << std::endl;
}
```

> The type of the thrown variable must be the same as the type captured in the catch block. If an ellipsis (...) is used as the parameter of catch, that handler will catch any exception no matter what the type of the exception thrown. 

More details : [exceptions](https://cplusplus.com/doc/tutorial/exceptions/)

    #cpp #try #catch #throw
