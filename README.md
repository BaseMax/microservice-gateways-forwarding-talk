# "Next-Gen Microservice Gateways: Real-Time Forwarding with Bun"

Explore how Bun and TypeScript can be combined to build a lightning-fast, real-time gateway that forwards incoming requests to microservices based on live context. Learn how this modern architecture improves performance, simplifies routing logic, and reduces latency in microservice communication.

In today's microservice architectures, latency and scalability remain critical challenges, especially when handling live, dynamic routing of client requests. Traditional solutions like NGINX or Express-based proxies often introduce bottlenecks or complexity.
This session presents a high-performance gateway built with Bun and TypeScript, designed to forward HTTP requests in real time to sub-projects or microservices based on context, headers, or routing rules. We’ll dive into how Bun’s speed and native TypeScript support make it ideal for this task, and demonstrate a working use case of live request forwarding across multiple services — with benchmarks, architecture, and lessons learned.
Whether you're scaling a platform or designing your next startup backend, this session will show how to rethink your gateway layer using modern tools.

1. Learn how to design and implement a real-time gateway using Bun + TypeScript that efficiently forwards requests to microservices with minimal latency.

2. Discover how Bun can replace traditional reverse proxies and Node.js-based routers in microservice environments for better performance.

## Getting start

```
$ bun init

✓ Select a project template: Blank

 + .gitignore
 + index.ts
 + tsconfig.json (for editor autocomplete)

To get started, run:

    bun run index.ts
```

```
$ cat index.ts
console.log("Hello via Bun!");
```

```
$ bun run index.ts
Hello via Bun!
```

## Bun

Why Bun?
What is Bun?

We are using Bun serve, not express, nestjs, etc.
Because Bun is really fast and quick and can serve many more requests in one second.

No need to include any libs, if you are using Bun, internally you can use network and serve library.

Just use `Bun.serve`.

One example:
```
const server = Bun.serve({
  port: 9999,
  fetch(req) {
    return new Response("Not Found", { status: 404 });
  },
});
```

Everytime someone send a request to your IP and Port, fetch() function will be executed. you will receive the details of the request in `req` variable, feel free to explore more and console.log that variable.

For more - If you want to get request url and details, you can use `new URL()` to parse `req.url`.

```
const server = Bun.serve({
  port: 9999,
  fetch(req) {
    const ur = newl URL(req.url);
    console.log(url);
    return new Response("Not Found", { status: 404 });
  },
});
```

Output of `req` is like this:

```
Request (0 KB) {
  method: "GET",
  url: "http://localhost:9999/",
  headers: Headers {
    "host": "localhost:9999",
    "connection": "keep-alive",
    "cache-control": "max-age=0",
    "upgrade-insecure-requests": "1",
    "user-agent": "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/136.0.0.0 Safari/537.36",
    "accept": "text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7",
    "sec-fetch-mode": "navigate",
    "sec-fetch-dest": "document",
    "accept-encoding": "gzip, deflate, br, zstd",
    "accept-language": "en-US,en;q=0.9,fa;q=0.8,it;q=0.7",
    "cookie": "_pk_id.1.1fff=85d6240db28b6e81.1743525621.; PHPSESSID=p8arc5lojukmbb9hg27oqfbj7p",
    "sec-ch-ua": "\"Chromium\";v=\"136\", \"Google Chrome\";v=\"136\", \"Not.A/Brand\";v=\"99\"",
    "sec-ch-ua-mobile": "?0",
    "sec-ch-ua-platform": "\"Windows\"",
    "sec-fetch-site": "none",
    "sec-fetch-user": "?1",
  }
}
```

So main values are:

- req.method
- req.url
- req.headers

We can analyse and parse req.url into sub values, so in this case: Output of `newl URL(req.url)` is:

```
URL {
  href: "http://localhost:9999/favicon.ico",
  origin: "http://localhost:9999",
  protocol: "http:",
  username: "",
  password: "",
  host: "localhost:9999",
  hostname: "localhost",
  port: "9999",
  pathname: "/favicon.ico",
  hash: "",
  search: "",
  searchParams: URLSearchParams {},
  toJSON: [Function: toJSON],
  toString: [Function: toString],
}
```
