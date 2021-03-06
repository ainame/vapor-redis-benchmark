# swift-redis-client-benchmarks

A benchmark for vapor/redis, IBM-Swift/Kitura-redis and PerfectlySoft/PerfectRedis based on https://github.com/stefanwille/redis-client-benchmarks

## My Result

### environment

Macbook Pro 15-inch 2017
2.9GHz Core i7 4core/16GB RAM
Mac OSX 10.12.5

```
$ swift --version
Apple Swift version 4.0 (swiftlang-900.0.43 clang-900.0.22.8)
Target: x86_64-apple-macosx10.9
```

```
$ redis-server --version
Redis server v=3.2.9 sha=00000000:0 malloc=libc bits=64 build=d97708fd9e007be7
```

### measurement

#### vapor/redis v2.0.0

```
$ ./.build/release/vapor-redis-performance
Elapsed time: 10.6762710213661, throughput: 93665.6626643074 commands/sec
Done
```

#### IBM-Swift/Kitura-redis v1.8.0

```
$ ./.build/x86_64-apple-macosx10.10/release/kitura-redis-performance
Elapsed time: 53.8855229616165, throughput: 18557.8601642656 commands/sec
Done
```

#### PerfectlySoft/Perfect-Redis v2.0.3

```
$ ./.build/x86_64-apple-macosx10.10/release/perfect-redis-performance
Elapsed time: 49.3147420287132, throughput: 20277.9120170142 commands/sec
Done
```

#### crystal-redis

https://github.com/stefanwille/redis-client-benchmarks

```
$ crystal --version
Crystal 0.22.0 (2017-04-20) LLVM 4.0.0
$ shards install
$ crystal build crystal_redis_performance.cr --release
$ time ./crystal_redis_performance

real	0m1.109s
user	0m0.373s
sys	0m0.071s
```

throughput => 901713.3 commands/sec!!!
