## E2E encryption example

Demonstrates how to register, log in and communicate with the server over unsecured network.

- The Seed app is served by [warp](https://crates.io/crates/warp).
- Warp also provides REST API endpoints.
- [opaque-ke](https://crates.io/crates/opaque-ke) is used for registration and log in. I strongly recommend to read its docs and the article ["OPAQUE: The Best Passwords Never Leave your Device"](https://blog.cloudflare.com/opaque-oblivious-passwords/) before you start to learn this example.
- [cocoon](https://crates.io/crates/cocoon) is used for encrypted communication. Messages are encrypted with the shared key generated by `opaque-ke` in the final log in step. 

_Warning_: The code is heavily inspired by `opaque-ke` examples and simplified to demonstrate basic principles. So there is too much `expect` calls, some strangely named variables and other things that you probably don't want in a production app. Also I'm not a security expert, so I don't guarantee there are no security bugs - use the example as a proof-of-concept and inspiration for your projects.

---

```bash
cargo make start
```

Open [127.0.0.1:8000](http://127.0.0.1:8000) in your browser.

Click `Register`, then `Login` and then `Send` button. 
Watch the changes between clicks on the website, browser console log and server log.