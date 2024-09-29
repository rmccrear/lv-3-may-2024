* Diagram of Proxy Server
  * client - API
  * client - proxy - API
  * Show data flow
  * Show keys


### Hour 2 Proxy Server Demo

* Show Deno app
  1. Demo a new GET route for a cat.
  2. Demo fetch proxy
  3. Demo env variable to hold key, demo how to get key and accept EUA
  4. Hands on: let students clone and update
    1. Clone start code on deno.com
    2. Add env variable - hugging face key
      * need to accept mixtral at https://huggingface.co/mistralai/Mixtral-8x7B-Instruct-v0.1
    3. change name of route from caesar-salad to fettuccine-alfredo
    4. add a new route
    5. add your own fetch function - the one you used for your project
    6. BONUS: Update your project to use this proxy server to hide your keys!