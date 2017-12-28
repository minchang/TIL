# Resolving "multiple method named ... " error in Objective-C

You should be able to fix the "multiple methods named" error by casting to the class that you want in the mock method. This error happens when you use the generic id type. For example:

```
@property (nonatomic) id mock; 
...
self.mock = OCMClassMock([SpecificThing class])
...
OCMStub([((SpecificThing*)mock) ambiguousMethodSignature])
```
