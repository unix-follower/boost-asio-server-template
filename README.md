# boost-asio-server-template

Build and run it with:

```bash
cmake -S . -B build
cmake --build build --target boost_asio_api_server -j4
./build/boost_asio_api_server --host 127.0.0.1 --port 9447
```

Optional runtime settings:
- `CPP_ASIO_HOST` and `CPP_ASIO_PORT` override bind address and port
- `CPP_HOST` and `CPP_PORT` are also accepted
- `CPP_ASIO_MODE` supports `thread-per-request`, `thread-pool`, `blocking`, and `nonblocking`
- `CPP_ASIO_THREADS` sets worker count for `thread-pool` mode
- `SERVER_HOST`, `SERVER_PORT`, and `PORT` remain generic fallbacks
- `TLS_CERT_FILE`, `TLS_KEY_FILE`, and optional `TLS_KEY_PASSWORD` can be set explicitly

## API
```bash
curl -k https://127.0.0.1:9447/api/health
curl -k "https://127.0.0.1:9447/api/health?mode=error"
curl -k https://127.0.0.1:9447/api/cid4/conformer/1
curl -k https://127.0.0.1:9447/api/cid4/compound
```
