# Sample Dataset

This repository contains a sample dataset provided for evaluation during the double-blind review process. To ensure privacy and compliance, IP addresses have been anonymized using the `ipcrypt-pfx` algorithm, and all timestamps have been shifted to a zero-epoch start (1970-01-01). 

> **Note:** The complete, unredacted dataset will be made publicly available in this repository upon the acceptance of the paper.

## File

The sample data is provided as a single Parquet file:
* `example_data_ano.parquet`

## Data Format

The dataset contains network flow records with corresponding attack labels. The schema is detailed below:

| Column | Description |
| :--- | :--- |
| `first`, `last` | The start and end timestamps of the network flow (shifted to relative time). |
| `src_addr`, `dst_addr` | Source and destination IP addresses (anonymized via `ipcrypt-pfx`). |
| `in_pkts`, `in_bytes` | Total number of incoming packets and bytes in the flow. |
| `src_port`, `dst_port` | Source and destination network ports. |
| `tcp_flags` | TCP flags observed in the flow. |
| `proto` | Transport layer protocol (e.g., UDP, TCP). |
| `atk_type`, `atk_id` | The classification category and specific ID of the attack. |
| `start_time`, `end_time` | The global start and end timestamps of the overarching attack event. |

## Example Data Snippet

Below is a preview of the data structure contained within the Parquet file:

```text
               last               first                                  src_addr                                  dst_addr  in_pkts  in_bytes  src_port  dst_port tcp_flags proto   atk_type atk_id start_time            end_time  
0  1970-01-01 00:00:08 1970-01-01 00:00:06  cf11:d515:3015:9a8:5c8:d2c2:6f1c:bf5a  c861:6b27:db6e:5e4e:6320:c421:30dd:2409        2       770     36739     59686  ........   UDP  UDP Flood      1 1970-01-01 1970-01-01 00:11:00  
1  1970-01-01 00:00:09 1970-01-01 00:00:09  c861:7b91:8ceb:2b1f:6b54:7f80:e748:9a7d  c861:6b27:db6e:5e4e:6320:c421:30dd:2409        1       385      9993     48621  ........   UDP  UDP Flood      1 1970-01-01 1970-01-01 00:11:00  
2  1970-01-01 00:00:19 1970-01-01 00:00:19  c861:7621:290f:69ff:142d:50a8:cc2b:3658  c861:6b27:db6e:5e4e:6320:c421:30dd:2409        1       385     13195     48621  ........   UDP  UDP Flood      1 1970-01-01 1970-01-01 00:11:00  
3  1970-01-01 00:00:26 1970-01-01 00:00:26  c861:7621:1f17:e41e:cb6d:62b3:8cda:d4b3  c861:6b27:db6e:5e4e:6320:c421:30dd:2409        1       385      9993     32132  ........   UDP  UDP Flood      1 1970-01-01 1970-01-01 00:11:00  
4  1970-01-01 00:00:53 1970-01-01 00:00:53  c861:7b91:f56e:6a9b:f953:1ad4:f1b3:a41c  c861:6b27:db6e:5e4e:6320:c421:30dd:2409        1       221      9993     39745  ........   UDP  UDP Flood      1 1970-01-01 1970-01-01 00:11:00  
..                 ...                 ...                                    ...                                       ...      ...       ...       ...       ...       ...   ...        ...    ...        ...                 ...  
64 1970-01-01 00:10:10 1970-01-01 00:10:10  c861:7b91:43b3:cbfa:93fe:51c5:3a3e:4265  c861:6b27:db6e:5e4e:6320:c421:30dd:2409        1       385     62037     21023  ........   UDP  UDP Flood      1 1970-01-01 1970-01-01 00:11:00  
65 1970-01-01 00:10:13 1970-01-01 00:09:14    cf11:d515:3015:9a8:5c8:d2c2:6f1c:bf5a  c861:6b27:db6e:5e4e:6320:c421:30dd:2409       58     22330     36739     59686  ........   UDP  UDP Flood      1 1970-01-01 1970-01-01 00:11:00  
66 1970-01-01 00:10:26 1970-01-01 00:10:26  c861:7b91:7573:f1a5:40e6:bfcb:b883:fb8c  c861:6b27:db6e:5e4e:6320:c421:30dd:2409        1        99     39517     48621  ........   UDP  UDP Flood      1 1970-01-01 1970-01-01 00:11:00  
67 1970-01-01 00:10:43 1970-01-01 00:10:16    cf11:d515:3015:9a8:5c8:d2c2:6f1c:bf5a  c861:6b27:db6e:5e4e:6320:c421:30dd:2409       26     10010     36739     59686  ........   UDP  UDP Flood      1 1970-01-01 1970-01-01 00:11:00  
68 1970-01-01 00:10:59 1970-01-01 00:10:59    c861:7b91:f559:45:6f36:3f7a:7445:160b  c861:6b27:db6e:5e4e:6320:c421:30dd:2409        1       385     37297     39745  ........   UDP  UDP Flood      1 1970-01-01 1970-01-01 00:11:00
