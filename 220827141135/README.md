# CPP0 Classes and instance

keywords :
* instantiation of a class => object instance
* constructor
* destructor

Class declaration :
```cpp
class Sample {
public:
	Sample(void);
	~Sample(void);
};
```
> Don't forget semi-colon at the end of class declaration :)

Class definition :
```cpp
Sample::Sample(void){
	return ;
}

Sample::~Sample(void){
	return ;
}
```

More details : [Classes](https://cplusplus.com/doc/tutorial/classes/)

    #cpp #classes #oop
