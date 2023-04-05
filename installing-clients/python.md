# Python

### 1. Install the Supergood library

{% code title="Pip" %}
```bash
pip install supergood
```
{% endcode %}

### 2. Initialize the Supergood Library

**Environment Variables**

Set the environment variables `SUPERGOOD_CLIENT_ID` and `SUPERGOOD_CLIENT_SECRET` respectively, using the API keys generated in the previous instructions.

Initialize the Supergood Client at the root of your application, or anywhere you're making API calls with the following lines of code:

```python
from Supergood import Client

Client()
```

**Passing Keys**

You can also pass the API keys in manually without setting environment variables.\
\
Replace `<CLIENT_ID>` and `<CLIENT_SECRET>` with the API keys you generated in the previous step.

```python
from Supergood import Client

Client(client_id="<CLIENT_ID>", client_secret="<CLIENT_SECRET>")
```

### 3. That's it!&#x20;

Head back to your [dashboard](https://dashboard.supergood.ai) to start monitoring your API calls and receiving reports.

### Links

* [Supergood PyPi Project](https://pypi.org/project/supergood/)
* [Supergood\_py Source Code](https://github.com/supergoodsystems/supergood-py)
