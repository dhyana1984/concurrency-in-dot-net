# Implement singleton pattern with Lazy<>
## The purpose to use Lazy<> is that to initial threads shared object with thead safe way. The Lazy is a way of "Cache", it will remember the result of calculation to avoid duplicated operation
```c#
   public sealed class Singleton
    {
        private static readonly Lazy<Singleton> lazy =
            new Lazy<Singleton>(() => new Singleton(), true); //#A

        public static Singleton Instance => lazy.Value;

        private Singleton()
        { }
    }
```