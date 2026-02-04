# Proto

**Reference**  
Proto

Ubo App uses **Protocol Buffers** for the gRPC API and for serializing store actions and events. Proto definitions live under `ubo_app/rpc/proto/`; Python bindings are generated into `ubo_app/rpc/ubo_bindings/`.

## What you see

- **Hand-written protos** (`ubo_app/rpc/proto/`):
  - **store/v1/store.proto** — `StoreService`: `DispatchAction`, `DispatchEvent`, `SubscribeEvent`, `SubscribeStore`. Messages: `DispatchActionRequest/Response`, `SubscribeEventRequest/Response`, etc. Uses `ubo/v1/ubo.proto` for the action/event oneofs.
  - **secrets/v1/secrets.proto** — Secrets service RPCs.
  - **package_info/v1/package_info.proto** — Package info.
  - **buf.yaml** — Buf lint/format config.
- **Generated from Python** — The `Action` and `Event` oneofs in `ubo/v1/ubo.proto` are generated from the store’s Python action and event classes by `ubo_app/rpc/generator/generate_proto.py`. Run `uv run poe proto:generate` (or `poe proto`) to regenerate after changing actions/events. The generator parses the Python modules and writes message definitions; then `proto:compile` compiles all protos with `grpc_tools.protoc` and **betterproto** into `ubo_bindings/`.
- **Usage** — The gRPC server (`ubo_app/rpc/server.py`, `store_service.py`) converts between proto messages and Python action/event objects (see `message_to_object.py`, `object_to_message.py`). Clients use the same protos; sample clients: [ubo-grpc-clients](https://github.com/ubopod/ubo-grpc-clients). The web app runs `npm run proto:compile` to generate TypeScript types from the same protos.
- **Lint** — `poe proto:lint` runs `buf format -w` on the proto directory.

## Navigation

- [Architecture → RPC](../architecture/rpc.md)
- [Development → Scripts](../development/scripts.md)
- [Getting Started](../getting-started.md)
