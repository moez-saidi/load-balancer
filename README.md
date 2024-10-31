# Load Balancer with Health Check
This Go program implements a basic load balancer with periodic health checks for backend servers.
It is configured via a JSON file specifying the port, health check interval, and server URLs.
The load balancer forwards client requests to healthy backend servers using a round-robin approach.

## Features
- Round-Robin Load Balancing: Distributes incoming requests across available servers in a cyclic manner.
- Health Checks: Periodically verifies the health of backend servers by sending HEAD requests. Only healthy servers receive traffic.
- Reverse Proxy: Forwards client requests to backend servers, preserving the origin URL via a reverse proxy.


## Usage
Create a `config.json` file specifying:

```json
{
  "port": ":8080",
  "healthCheckInterval": "10s",
  "servers": ["http://server1.com", "http://server2.com"]
}
```
Run the program:

```bash
go run main.go
```