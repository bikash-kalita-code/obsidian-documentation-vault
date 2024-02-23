- Client sends a Request
- Server parses the Request
- Server processes the Request
- Server sends a Response
- Client parses the Response and consume

One of the reason for people moving from SOAP (XML) to REST (JSON) is that the expense of parsing XML is way higher than parsing JSON. Actually, parsing JSON is also slow which is the reason why people moved to protocol buffers as a quick parser.

### Where is it used?
- Web, HTTP, DNS, SSH
