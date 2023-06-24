# Configuration

Optional configuration may be passed to the `new` function, the parameters may be configured as follows:

### RecordRequestBody

_Default: false_

RecordRequestBody additionally sends the body of requests to the Supergood cloud for debugging. Defaults to false, if set true all values will be completely redacted unless otherwise specified.

### IncludeSpecifiedRequestBodyKeys

_Default: \[]_

IncludeSpecifiedRequestBodyKeys is a list of keys who's value which to NOT redact in the request body, if RecordRequestBody is set to 'true'

### RecordResponseBody

_Default: false_

RecordResponseBody additionally sends the body of responses to the Supergood cloud for debugging. Defaults to false, if set true all values will be redacted unless otherwise specified.

### **IncludeSpecifiedResponseBodyKeys**

_Default: \[]_

IncludeSpecifiedResponseBodyKeys is a list of keys who's values which to NOT redact in the response body, if RecordResponseBody is set to 'true'

### **IncludeSpecifiedRequestHeaderKeys**

_Default: \[]_

Supergood replaces sensitive headers by the sha1 of their contents, by default. IncludeSpecifiedRequestHeaderKeys will override this behavior and include the specified value. Matching is case insensitive.

### **AllowedDomains**

_Default: \[]_

List of strings to match against the host of the request URL in order to determine whether or not to log the request to Supergood, based on the domain. Case sensitive. By default, requests from all domains are logged.

### **FlushInterval**

_Default: 1 \* time.Second_

Flush interval configures how frequently Supergood sends batches of logs to the API.
