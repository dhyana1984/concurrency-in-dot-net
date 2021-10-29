 # C# HOF
 ```c#
//Create a extention method
static Func<A, C> Compose<A, B, C>(this Func<A, B> f, Func<B, C> g) => n => g(f(n));

//Create a new makeExpresso method based by the extention method
Func<CoffeeBeans, Expresso> makeExpresso = grindCoffee.Compose(brewCoffee);
Expresso expresso = makeExpresso(coffeBeans)

 ```