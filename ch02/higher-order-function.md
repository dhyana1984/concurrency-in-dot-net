 # C# HOF
 ```c#
Func<CoffeeBeans, CoffeeGround> grindCoffee = coffeeBeans => new CoffeeGround(coffeeBeans);
Func <CoffeeGround, Espresso> brewCoffee = coffeeGround => new Espresso(coffeeGround)
//Create a extention method
static Func<A, C> Compose<A, B, C>(this Func<A, B> f, Func<B, C> g) => n => g(f(n));

//Create a new makeExpresso method based by the extention method
Func<CoffeeBeans, Espresso> makeEspresso = grindCoffee.Compose(brewCoffee);
Espresso expresso = makeEspresso(coffeBeans)

 ```