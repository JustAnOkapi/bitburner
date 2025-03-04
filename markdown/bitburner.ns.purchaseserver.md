<!-- Do not edit this file. It is automatically generated by API Documenter. -->

[Home](./index.md) &gt; [bitburner](./bitburner.md) &gt; [NS](./bitburner.ns.md) &gt; [purchaseServer](./bitburner.ns.purchaseserver.md)

## NS.purchaseServer() method

Purchase a server.

<b>Signature:</b>

```typescript
purchaseServer(hostname: string, ram: number): string;
```

## Parameters

|  Parameter | Type | Description |
|  --- | --- | --- |
|  hostname | string | Host of the purchased server. |
|  ram | number | Amount of RAM of the purchased server. Must be a power of 2 (2, 4, 8, 16, etc.). Maximum value of 1048576 (2^20). |

<b>Returns:</b>

string

The hostname of the newly purchased server.

## Remarks

2.25 GB

Purchased a server with the specified hostname and amount of RAM.

The hostname argument can be any data type, but it will be converted to a string and have whitespace removed. Anything that resolves to an empty string will cause the function to fail. If there is already a server with the specified hostname, then the function will automatically append a number at the end of the hostname argument value until it finds a unique hostname. For example, if the script calls `purchaseServer(“foo”, 4)` but a server named “foo” already exists, the it will automatically change the hostname to `foo-0`<!-- -->. If there is already a server with the hostname `foo-0`<!-- -->, then it will change the hostname to `foo-1`<!-- -->, and so on.

Note that there is a maximum limit to the amount of servers you can purchase.

Returns the hostname of the newly purchased server as a string. If the function fails to purchase a server, then it will return an empty string. The function will fail if the arguments passed in are invalid, if the player does not have enough money to purchase the specified server, or if the player has exceeded the maximum amount of servers.

## Example 1


```ts
// NS1:
var ram = 64;
var prefix = "pserv-";
for (i = 0; i < 5; ++i) {
   purchaseServer(prefix + i, ram);
}
```

## Example 2


```ts
// NS2:
const ram = 64;
const prefix = "pserv-";
for (i = 0; i < 5; ++i) {
   ns.purchaseServer(prefix + i, ram);
}
```

