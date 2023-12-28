# Socket Programming-Based Intelligent File Backup system

## Introduction
Welcome to our GitHub organization hosting the Intelligent Backup System, a robust Client-Server paradigm-based File Backup System developed using Python Socket programming. This system stands out with its unique approach to file segmentation, dynamic tag generation using Machine Learning, and enhanced security features for sensitive data protection.

## System Overview

### Backup Process
1. **Initialization**: Users start by providing a directory path, the server's IP address, desired chunk size, and a CSV containing user-specific sensitive data keywords.
2. **File Parsing and ML Tagging**: Our system efficiently parses files based on their extensions. Utilizing advanced ML models, text files undergo processes like PII detection, Topic Modeling, and Abstractive Summarization, while images are subject to Image Classification and Object Detection.
3. **File Chunking**: Files are divided into manageable chunks, each with a common checksum for integrity.
4. **Metadata Storage**: The client database securely stores file metadata, chunk information, and generated tags.
5. **Server Connection**: A socket connection is established to transfer file details, chunks, and metadata to the server.
6. **Socket Closure**: The client concludes the backup by closing the socket after data transmission.

### Recovery Process
1. **Initialization**: Recovery is initiated by providing the server hostname and desired directory.
2. **Database Query**: The client queries its database to retrieve file details and associated tags.
3. **Server Connection**: A socket connection is established for requesting file chunks.
4. **Chunk Retrieval**: Based on the provided details and tags, file chunks are retrieved and sent back to the client for reconstruction.
5. **File Retrieval**: Post successful reconstruction, clients can proceed with further retrievals or close the connection.

## ML Tag Generation Modules
- **PII Data Detector**: Employs MiniLM-L6-v2 and KeyBERT for PII detection, categorizing risk levels and securing high-risk files with password protection.
- **Abstractive Summarizer**: Uses PEGASUS for generating concise summaries, ensuring context relevance and key information extraction.
- **Keyword Extractor**: Implements KeyBERT for generating simple tags from top-n keywords.
- **Image Classification**: Utilizes MobileNet for descriptive tag generation on images, enhancing the system's capability to categorize and retrieve image files effectively.

## Repository Structure
- `Client`: Contains all client-side scripts, ML models, and utilities for file processing and backup.
- `Machine Learning`: Contains specialized ML scripts and models used in the system, including PII detection, topic modeling, abstractive summarization, image classification, and object detection algorithms.
- `Backend`:  Hosts the server-side components, responsible for managing incoming data, storage, and overall system functionality.

## Contributing
We greatly appreciate and encourage contributions! Your insights and improvements can play a vital role in enhancing this innovative backup system.
