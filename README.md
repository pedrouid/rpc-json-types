# rpc-json-types [![npm version](https://badge.fury.io/js/rpc-json-types.svg)](https://badge.fury.io/js/rpc-json-types)

JSON-RPC Types

## API

```typescript
// ---------- Typings ----------------------------------------------- //

interface JsonRpcRequest<T = any> {
  id: number;
  jsonrpc: string;
  method: string;
  params: T;
}

interface JsonRpcResult<T = any> {
  id: number;
  jsonrpc: string;
  result: T;
}

interface JsonRpcError {
  id: number;
  jsonrpc: string;
  error: ErrorResponse;
}

interface ErrorResponse {
  code: number;
  message: string;
}

type JsonRpcResponse<T = any> = JsonRpcResult<T> | JsonRpcError;

type JsonRpcPayload<P = any, R = any> = JsonRpcRequest<P> | JsonRpcResponse<R>;
```
