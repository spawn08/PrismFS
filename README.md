# PrismFS
A lightweight, high-performance distributed file system written in Go. PrismFS slices and replicates files across a network of nodes, providing fault tolerance, scalability, and low-latency access to your data.

## Key Features

- **Distributed Sharding**: Automatically splits files into shards and distributes them across available nodes.
- **Replication & Fault Tolerance**: Configurable replication factor ensures data availability even if nodes go offline.
- **Raft-based Consensus**: Built-in Raft algorithm for leader election and cluster coordination.
- **Go-Native**: Fully implemented in Go, with a clean, idiomatic API.
- **Pluggable Storage Backends**: Support for local disk, S3-compatible object stores, or custom plugins.
- **Zero-Downtime Scaling**: Add or remove nodes without interrupting ongoing operations.
- **CLI & RESTful API**: Intuitive command-line tools and HTTP endpoints for management and file operations.

## Architecture Overview

1. **Client**: CLI or HTTP client sends file operations (`put`, `get`, `delete`, `list`) to the cluster.
2. **Proxy/Coordinator**: Routes requests to the appropriate leader node using Raft membership data.
3. **Storage Nodes**: Store file shards locally or in object storage, and participate in consensus for metadata consistency.
4. **Consensus Layer**: Ensures metadata (shard mappings, replication state) is consistent across the cluster.

## Getting Started

### Prerequisites

- Go 1.22+ installed
- At least 3 machines (or Docker containers) for a production cluster

### Installation

```bash
# Clone the repo
git clone https://github.com/spawn08/PrismFS.git
cd prismfs

# Build the binary
make build
```  

### Running a Local Cluster (Dev)

Work in Progress

## Configuration

Work in Progress

## Contributing

Contributions are welcome! Please follow these guidelines:

1. Fork the repository.
2. Create a feature branch (`git checkout -b feature/YourFeature`).
3. Commit your changes with clear messages.
4. Run tests and ensure coverage remains high.
5. Submit a Pull Request.

## License

This project is licensed under the Apache License 2.0. See [LICENSE](LICENSE) for details.

---

> PrismFS – Slicing, replicating, and serving your files at light speed.
