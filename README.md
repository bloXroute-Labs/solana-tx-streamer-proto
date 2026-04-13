# Protobuf Files for Solana Tx Streamer

This repository contains Protocol Buffers (`.proto`) definition files for gRPC communication with the Solana Tx Streamer. See complete documentation in https://docs.bloxroute.com/solana/optimized-feed-relay/transaction-streamer.

## TxStreamerService

The `TxStreamerService` provides the following methods:

### StreamTransactions

Streams transactions, optionally filtered by associated accounts. Each streamed transaction includes:

- `signature` – The transaction’s unique identifier.
- `slot` – The slot in which the transaction was recorded.
- `data` – The raw transaction bincode-encoded data.
- `unverified_match` – Indicates potential irrelevance of the transaction based on the specified filtering criteria. If `true`, the service is uncertain about the match but includes the transaction to prevent the client from missing potentially relevant data.
- `number` – Index position of this transaction within the block.
