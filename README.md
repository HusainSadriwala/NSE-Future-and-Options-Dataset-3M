# NSE-Future-and-Options-Dataset-3M
The source dataset is a flat CSV containing high-volume NSE Futures & Options data with repeated attributes such as symbol, expiry date, and strike price. To eliminate redundancy and improve scalability, the schema is normalized to 3NF by separating exchanges, instruments, and trade metrics into distinct tables.

A star schema was intentionally avoided because this system is optimized for frequent ingestion. Normalization reduces storage duplication, improves write performance, and simplifies future data ingestion.

The design scales beyond 10M+ rows by isolating high-volume data in the trades table, supporting indexing on timestamps and foreign keys, and enabling partitioning by date or exchange. Although the dataset contains only NSE data, an exchange dimension is included to support future ingestion from BSE and MCX without schema changes.
