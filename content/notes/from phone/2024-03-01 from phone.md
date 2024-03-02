Interesting how Google has made it so that links you send come from Google Maps include a link to the app instead of coordinates. Or even an address. Because they know that if they sent any identifying information, be it latitude/longitude coordinates or an address, the receiving company would hijack it.

For example, if you share an address in a text to an iPhone, Apple shows it in Apple Maps.

I think Google noticed this, and so they implemented this weird Google shortlink sharing to combat it.

In corporate-speak: It’s effectively a strategy used to protect leads and combat lead theft, which also benefits the company’s SEO.

—

Note: using Anthropic's Python SDK, they don't actually return a json, like I assumed based on their documentation. So, you can't check

`if "text" not in response["content"][0]`

Instead, my code now reads
`if not response.content[0]`

They made a Message object, which you call like a package, the way it should be.

Another thing I noticed:
These guys straight up completely copied OpenAI. Didn't even change the API key style, instead opting to add “ant” after the `sk-` prefix. On the other hand, that makes it obvious it’s an API key for a transformer