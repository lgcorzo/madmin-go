# MinIO Admin Golang Client SDK (`@lgcorzo/madmin-go`)

[![Go Reference](https://pkg.go.dev/badge/github.com/lgcorzo/madmin-go/v4.svg)](https://pkg.go.dev/github.com/lgcorzo/madmin-go/v4)
[![Go](https://github.com/lgcorzo/madmin-go/actions/workflows/go.yml/badge.svg)](https://github.com/lgcorzo/madmin-go/actions/workflows/go.yml)
[![Golangci-lint](https://github.com/lgcorzo/madmin-go/actions/workflows/lint.yml/badge.svg)](https://github.com/lgcorzo/madmin-go/actions/workflows/lint.yml)
[![VulnCheck](https://github.com/lgcorzo/madmin-go/actions/workflows/vulncheck.yml/badge.svg)](https://github.com/lgcorzo/madmin-go/actions/workflows/vulncheck.yml)

> **Sovereign Maintenance Notice**: This repository is part of the **Sovereign MinIO Ecosystem** actively maintained by [@lgcorzo](https://github.com/lgcorzo). It is fully decoupled from upstream deprecations and updated with high-throughput optimizations, zero-CVE guarantees, and deep integration with the **Dark Gravity** autonomous AI production stack.

The MinIO Admin Golang Client SDK (`github.com/lgcorzo/madmin-go/v4`) provides administrative Go APIs for managing MinIO object storage clusters, server configuration, IAM, bucket policies, healing, tiering, and cluster decommissioning.

---

## Dark Gravity Factory Rationale & Sovereign Maintenance

This repository is maintained as a core foundational component of the **Dark Gravity Autonomous AI Factory**. Sovereign control over high-performance storage administration and management SDKs ensures:

* **Full Supply-Chain Autonomy**: Zero dependency on upstream breaking license shifts, vendor lock-in, or unannounced repository deprecations.
* **Dark Gravity Factory Core Integration**: Native administrative SDK powering autonomous AI training infrastructure, distributed object storage clusters, automated telemetry pipelines, and agentic workflows.
* **Compliance & Security**: Rigorous zero-CVE SLA enforcement, audit trail compatibility, and full compliance with EU AI Act, SOC 2 Type II, and ISO 25059 standards.
* **Ecosystem Interoperability**: First-class integration with all 38 sovereign repositories under `@lgcorzo` (Server, Client MC, KES, Operator, DirectPV, Console, and optimized SIMD acceleration libraries).

---

## Ecosystem Architecture & Automated Maintenance

```
                      +---------------------------------------------------+
                      |             Dark Gravity AI Engine                |
                      +---------------------------------------------------+
                                                |
                                                v
                      +---------------------------------------------------+
                      |            @lgcorzo Sovereign Stack               |
                      +---------------------------------------------------+
                                                |
         +----------------------+---------------+---------------+----------------------+
         |                      |                               |                      |
         v                      v                               v                      v
+------------------+  +-------------------+           +-------------------+  +------------------+
|   minio (Server) |  |   mc (Client)     |           | madmin-go (SDK)   |  |   kes (KMS)      |
+------------------+  +-------------------+           +-------------------+  +------------------+
         |                      |                               |                      |
         +----------------------+---------------+---------------+----------------------+
                                                |
                                                v
                      +---------------------------------------------------+
                      |      Automated CI/CD & Security Pipelines         |
                      |  (Vulnerability Scan | Race Test | Lint Matrix)  |
                      +---------------------------------------------------+
```

### Sovereign Ecosystem Matrix (38 Repositories)

| Category | Repositories |
| :--- | :--- |
| **Core Storage & Server** | `lgcorzo/minio`, `lgcorzo/mc`, `lgcorzo/madmin-go`, `lgcorzo/minio-go` |
| **Security & Cryptography** | `lgcorzo/kes`, `lgcorzo/kms-go`, `lgcorzo/sio-go`, `lgcorzo/pkg` |
| **Kubernetes & Cloud Native** | `lgcorzo/operator`, `lgcorzo/directpv`, `lgcorzo/console`, `lgcorzo/sidekick` |
| **Performance & SIMD** | `lgcorzo/sha256-simd`, `lgcorzo/md5-simd`, `lgcorzo/blake2b-simd`, `lgcorzo/simdjson-go` |
| **Compression & Encoding** | `lgcorzo/dedup`, `lgcorzo/zip`, `lgcorzo/highwayhash`, `lgcorzo/s2` |
| **Ecosystem Tools & Drivers** | `lgcorzo/warp`, `lgcorzo/benchmarks`, `lgcorzo/dsuite`, `lgcorzo/mftp` |

---

## Quickstart & Usage

Install the sovereign MinIO Admin client SDK:

```bash
go get github.com/lgcorzo/madmin-go/v4
```

### Initialize MinIO Admin Client Object

```go
package main

import (
    "context"
    "fmt"
    "log"

    madmin "github.com/lgcorzo/madmin-go/v4"
)

func main() {
    // Use a secure connection.
    ssl := true

    // Initialize MinIO Admin client object.
    mdmClnt, err := madmin.New("your-minio.example.com:9000", "YOUR-ACCESSKEYID", "YOUR-SECRETKEY", ssl)
    if err != nil {
        log.Fatalln(err)
    }

    // Fetch cluster status.
    info, err := mdmClnt.ClusterInfo(context.Background())
    if err != nil {
        log.Fatalln(err)
    }
    fmt.Printf("Cluster Info: %#v\n", info)
}
```

---

## Documentation

Comprehensive API documentation is available via [Go Package Documentation](https://pkg.go.dev/github.com/lgcorzo/madmin-go/v4).

---

## License

This SDK is licensed under the [GNU AGPLv3 License](https://github.com/lgcorzo/madmin-go/blob/master/LICENSE).
