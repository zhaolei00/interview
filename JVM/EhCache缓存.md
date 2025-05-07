1. 本地缓存，在分布式环境下，如何让别的本地缓存失效。需要一种手段同步到其他JVM进程上，Zookeeper、MQ、Redis等都可以。
    Caffeine本地缓存，用dubbo的广播来刷新本地缓存的。
2. 存储位置
    堆内
    堆外
    磁盘
3. 数据过期时间
    不设置
    放入缓存开始计算时间
    最后一次访问开始计算时间
    ```
    CacheManager cacheManager = CacheManagerBuilder.newCacheManagerBuilder()
                .withCache("singleDog", CacheConfigurationBuilder
                        // 缓存大小设置
                        .newCacheConfigurationBuilder(
                                String.class,
                                String.class,
                                ResourcePoolsBuilder.heap(10))
                        // 过期时间设置
                        .withExpiry(ExpiryPolicyBuilder.timeToIdleExpiration(Duration.ofMillis(1000))))
                .build(true);

        Cache<String, String> cache = cacheManager.getCache("singleDog", String.class, String.class);
        cache.put("12", "23");
        System.out.println(cache.get("12"));
        Thread.sleep(500);
        System.out.println(cache.get("12"));
        Thread.sleep(1000);
        System.out.println(cache.get("12"));
        cacheManager.close();
    ```