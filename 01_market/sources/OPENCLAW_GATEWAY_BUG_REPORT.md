# OpenClaw Gateway/Cron Bug Report Draft

## Title
Docker container gateway/CLI local loopback handshake timeout prevents `openclaw cron` commands

## Environment
- Image: `ghcr.io/openclaw/openclaw:latest`
- Container name: `openclaw-gateway`
- Entrypoint/Cmd: `node openclaw.mjs gateway --allow-unconfigured`
- Inside-container user: `node`
- Config path: `/home/node/.openclaw/openclaw.json`

## Relevant Config
```json
"gateway": {
  "mode": "local",
  "auth": {
    "mode": "none"
  }
}
```

## What Works
- Gateway starts and listens successfully
- Logs show:
  - `listening on ws://127.0.0.1:18789, ws://[::1]:18789`
- Cron store initializes successfully:
  - `/home/node/.openclaw/cron/jobs.json`
  - `jobCount: 0`
  - `enabledCount: 0`

## What Fails
Inside the container, these commands fail:
```bash
/usr/local/bin/openclaw cron status
/usr/local/bin/openclaw cron list
/usr/local/bin/openclaw gateway call ...
```

Observed errors include:
```text
gateway connect failed: Error: gateway closed (1000)
Error: gateway closed (1000 normal closure): no close reason
Gateway target: ws://127.0.0.1:18789
Source: local loopback
Config: /home/node/.openclaw/openclaw.json
Bind: loopback
```

Also observed in status output:
```text
gateway url override requires explicit credentials
Fix: pass --token or --password (or gatewayToken in tools)
```

## Key Logs
```text
gateway/ws handshake timeout ... remote=127.0.0.1
closed before connect ... code=1008 reason=connect challenge timeout
```

## What Was Already Tried
- Confirmed the real runtime is Docker, not host shell
- Verified container entrypoint is simple and does not obviously override gateway config
- Verified `openclaw.json` was successfully updated and persisted
- Set:
  - `gateway.mode = local`
  - `gateway.auth.mode = none`
- Restarted the container
- Re-checked config after restart
- Confirmed gateway still listens on 127.0.0.1:18789
- Confirmed cron store starts

## Expected Behavior
Inside the container, with `gateway.mode=local` and `gateway.auth.mode=none`, local CLI commands such as `openclaw cron status` and `openclaw cron list` should work.

## Actual Behavior
Gateway listens successfully, but CLI loopback RPC fails during connect challenge / websocket handshake.

## Impact
- Prevents enabling cron-based automation inside this Docker deployment
- Business logic and workspace development can continue, but scheduled automation is blocked
