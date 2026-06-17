# CHANGELOG v1.0.0

Initial release of the logger library.

## Added

- **Five log levels**: Debug, Info, Warn, Error, Critical, with Info as the default level.
- **Package-level singleton API**: `Infof`, `Debugf`, `Warnf`, `Errorf`, `Criticalf` operate on a global default logger instance.
- **Instance-based API**: `New()` creates independent `Logger` instances with configurable output via `SetOutput()`.
- **Callstack control**: `HideCallstack()` / `ShowCallstack()` to toggle file:line annotation per log line.
- **Log level control**: `SetLevelByString()` for runtime level changes using atomic operations (thread-safe).
- **Context integration** (`ctxutil` subpackage): `SetRequestId`, `GetRequestId`, `ClearRequestId`, `SetMessageId`, `AppendMessageId`, `ClearMessageId` — stored in `context.Context` and propagated through gRPC outgoing metadata.
- **Newline escaping**: Log messages containing `\n` or `\r` are escaped to `\n` and `\r` to preserve single-line output.
- **Structured log parser** (`reader.go`): Internal utility to parse log output back into structured `logMessage` structs for test assertions.
- **CI**: Travis CI configuration with `go test` and `go vet`.

## Changed

- Module path renamed from `openpitrix.io/logger` to `github.com/codefuture-io/logger`.
