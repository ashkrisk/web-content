# MilvusClient

A __MilvusClient__ instance represents a Python client that connects to a specific Milvus instance.

```python
pymilvus.MilvusClient
```

## Constructor

Constructs a client for common use cases.

<div class="admonition note">

<p><b>notes</b></p>

<p>This client serves as an easy-to-use alternative for the current set of APIs that handles Create, Read, Update, and Delete (CRUD) operations in Milvus.</p>

</div>

```python
MilvusClient(
    uri: str,
    user: str,
    password: str,
    db_name: str,
    token: str,
    timeout=None,
    **kwargs
)
```

__PARAMETERS:__

- __uri__ (_string_) -

    The URI of the Milvus instance. For example:

    ```plaintext
    http://localhost:19530
    ```

- __user__ (_string_) -

    A valid username used to connect to the specified Milvus instance.

    Use this if authentication has been enabled on the target Milvus instance. To enable authentication, refer to [Authenticate User Access](https://milvus.io/docs/authenticate.md).

    This should be used along with __password__.

- __password__ (_string_) -

    A valid password used to connect to the specified Milvus instance.

    Use this if authentication has been enabled on the target Milvus instance. To enable authentication, refer to [Authenticate User Access](https://milvus.io/docs/authenticate.md).

    This should be used along with __user__.

- __db_name__ (_string_) -

    The name of the database to which the target Milvus instance belongs.

- __token__ (_string_) -

    A valid access token to access the specified Milvus instance. 

    This can be used as a recommended alternative to setting __user__ and __password__ separately.

    When setting this field, notice that:

    A valid token should be a pair of username and password used to access the target cluster, joined by a colon (:). For example, you can set this to `root:Milvus`, which is the default credential of the root user.

    Use this if authentication has been enabled on the target Milvus instance. To enable authentication, refer to [Authenticate User Access](https://milvus.io/docs/authenticate.md).

- __timeout__ (_float _|_ None_)  

    The timeout duration for this operation. 

    Setting this to __None__ indicates that this operation timeouts when any response arrives or any error occurs.

## Examples

```python
from pymilvus import MilvusClient

# Authentication not enabled
client = MilvusClient("http://localhost:19530")

# Authentication enabled with the root user
client = MilvusClient(
    uri="http://localhost:19530",
    token="root:Milvus",
    db_name="default"
)

# Authentication enabled with a non-root user
client = MilvusClient(
    uri="http://localhost:19530",
    token="user:password", # replace this with your token
    db_name="default"
)
```

## Class members

Refer to [MilvusClient](./MilvusClient.md) for a categorized list of class members.

