1. SpringBoot通过封装CacheManager和Cache来统一缓存的使用。具体存储在哪不管，需要使用者进行配置定义。
2. 如果@Bean主动配置CacheManager，那么会用配置的。如果有多个用@Primary进行指定。
3. 接着上面2进行讨论，如果不主动配置Bean，通过spring.cache.type进行指定的，那么具体的实现类是哪个呢？