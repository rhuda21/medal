Medal's LuaU decompiler

All credits to this project goes to in honor and memory of:
Jujhar Singh (KowalskiFX)
Mathias Pedersen (Costomality)

While details of how they passed and our relationship with them are completely irrelevant its better if their legacy 
does not go in vain. 

Keep the Singh and Pedersen family in you guys prayers.
We love you both.
```lua
getgenv().decompile = function(scriptInstance)
    local bytecode = getscriptbytecode(scriptInstance)
    local encoded = crypt.base64.encode(bytecode)
    local response = request({
        Url = "https://medal-decom.rhuda21.workers.dev/decompile",
        Method = "POST",
        Headers = {
            ["Authorization"] = "ymjKH2O3BbO3bDSsKmpo3ek3vHxIWYLQfj0",
            ["Content-Type"] = "application/octet-stream"
        },
        Body = encoded
    })
    return response.Body
end
```
