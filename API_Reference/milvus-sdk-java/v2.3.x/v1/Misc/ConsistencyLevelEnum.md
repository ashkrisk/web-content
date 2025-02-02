# ConsistencyLevelEnum

The enumeration for consistency level during a search/query.

```java
package io.milvus.common.clientenum;
public enum ConsistencyLevelEnum
```

|  **Type**   |  **Code** |  **Description**                                                            |
| ----------- | --------- | --------------------------------------------------------------------------- |
|  STRONG     |  0        |  Waits until all operations are completed before a search/query.            |
|  BOUNDED    |  2        |  Waits until operations in a time span are completed before a search/query. |
|  EVENTUALLY |  3        |  Executes a search/query immediately.                                       |