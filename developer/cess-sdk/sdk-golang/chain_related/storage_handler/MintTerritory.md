This is the interface for purchasing a territory.

```golang
// MintTerritory purchase a territory
//   - gib_count: territory size
//   - territory_name: territory name
//   - days: effective days
//
// Return:
//   - string: block hash
//   - error: error message
func (c *ChainClient) MintTerritory(gib_count uint32, territory_name string, days uint32) (string, error)
```

Example code:
```golang
package main

import (
    "context"
    "fmt"
    "time"

    sdkgo "github.com/CESSProject/cess-go-sdk"
)

// Substrate well-known mnemonic:
//
//   - https://github.com/substrate-developer-hub/substrate-developer-hub.github.io/issues/613
//   - cXgaee2N8E77JJv9gdsGAckv1Qsf3hqWYf7NL4q6ZuQzuAUtB
var MY_MNEMONIC = "bottom drive obey lake curtain smoke basket hold race lonely fit walk"

var RPC_ADDRS = []string{
    //testnet
    "wss://testnet-rpc.cess.network/ws/",
}

func main() {
    sdk, err := sdkgo.New(
        context.Background(),
        sdkgo.ConnectRpcAddrs(RPC_ADDRS),
        sdkgo.Mnemonic(MY_MNEMONIC),
        sdkgo.TransactionTimeout(time.Second*10),
    )
    if err != nil {
        panic(err)
    }
    defer sdk.Close()

    // purchase a 100GiB territory
    fmt.Println(sdk.MintTerritory(100, "myTerritory", 300))
}
```