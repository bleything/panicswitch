# Panic Switch

Ever thought to yourself "dang, I wish I could control my light bulbs from
Panic's Status Board app"? Good news! Panic Switch is a widget for Panic's
[Status Board] app that controls your [Philips Hue] lights.

[Status Board]: https://panic.com/statusboard/
[Philips Hue]: https://meethue.com

### How Do?

First we need to create the Panic Switch user on your Hue bridge. This is a
one-time operation that will not need to be repeated unless you replace or
factory reset your bridge.

* Go to http://www.meethue.com/api/nupnp and note the IP address of your bridge
* Go to http://BRIDGE_IP/debug/clip.html
* Use the CLIP interface to `POST` the following JSON to `/api`:

```json
{"devicetype": "Panic Switch"}
```

* You should see an error saying `link button not pressed`. Push the link button
  on your bridge and submit the `POST` again. You should see a success message
  that includes a username:

```json
[
  {
    "success": {
      "username": "zg0uAT9k1PaZ3Q89ocQlJhDDLeBTtFDAMKdVhqaI"
    }
  }
]
```

Next, set up Status Board. Add a Do-It-Yourself widget and set the Panel URL to
http://bleything.github.io/panicswitch/widget.html?username=your-username-from-before

All done!

### License

(The MIT License)

Copyright (c) 2013 [Ben Bleything](mailto:ben@bleything.net)

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
