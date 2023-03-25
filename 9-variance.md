In Scala, variance is about how types relate to each other in terms of inheritance when dealing with generic types (like classes or traits that work with type parameters). To put it simply, variance tells us how the subtyping relationships of the type parameters of a generic class behave when that class is subclassed.
```
// +T covariance any Container1[B] is a Container1[A]
class Container1[+T]
class A
class B extends A
val a: Container1[A] = new Container1[B]

// -T contravariance any Container2[C] is a Container2[D]
class Container2[-T]
class C
class D extends C
val b: Container2[D] = new Container2[C]

// No symbol Invariance Container3[E] and Container3[F] cannot be interchanged at all
class E
class F extends E
class Container3[T]

val c: Container3[E] = new Container3[F] // ERROR
```
