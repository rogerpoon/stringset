## StringSet

An optimized hash set for string values for JS++.

If optimization is not critical, use the JS++ Standard Library `System.HashSet<T>`.

### Usage

```
import ThirdParty;

auto set = new StringSet("initial", "values", "go", "here");
```

### Performance

A test using `System.Benchmark` on the LibreOffice English (US) dictionary (~49,000 terms):

```
StringSet : 70ms     (00.07 seconds)
string[]  : 82299ms  (82.29 seconds)
```

Benchmark Code:

```
auto bench = new Benchmark();
bench.start();
bool x;
for (int i = 0; i < 500000; ++i) {
	x = DictionaryEnUS.contains(i.toString());
}
Console.log(x);
bench.stop();
Console.log(bench.duration);
```

Benchmark System Specifications:

* Intel Core i7-4790k
* 32gb DDR3 RAM
* Samsung 840 Pro SATA III SSD
* Node.js 7.9.0
* Linux kernel 4.1.0-1-amd64 (Debian 9)

### License

MIT License
