# Web Infrastructure

## What is DNS?

DNS stands for Domain Name System. It functions like a phonebook for the internet, translating human-readable domain names into IP addresses.

### How DNS Works

1. **User Input:** A user enters a domain name into their web browser, for example, `example.com`.
2. **Initial Request:** The user's computer sends a request to a DNS server asking for the IP address of the domain name.
3. **Cache Check:** The DNS server checks its cache. If it has the IP address stored, it returns it to the user's computer.
4. **Forwarding Request:** If the DNS server does not have the IP address in its cache, it forwards the request to another DNS server. This process continues until a DNS server with the IP address is found.
5. **Response:** Once the IP address is found, it is returned to the user's computer.
6. **Connection:** The user's computer uses the IP address to connect to the website.

### DNS Hierarchy

DNS is hierarchical. At the top are root DNS servers, containing IP addresses of top-level domains (TLDs) like `.com` and `.org`. TLD DNS servers have IP addresses of second-level domains (SLDs) such as `example.com`. SLD DNS servers hold IP addresses of individual websites.

### DNS Distribution

DNS is distributed, meaning there are many DNS servers around the world. This distribution ensures DNS availability even if some servers fail.

### Importance of DNS

DNS is essential for the internet, allowing users to access websites using domain names instead of IP addresses.

### Types of DNS Records

1. **A Record (Address Record):** Maps a hostname to an IPv4 address.
2. **MX Record (Mail Exchange):** Directs email to a domain’s mail server.
3. **NS Record (Name Server):** Delegates a domain to a specific DNS server.
4. **AAAA Record:** Maps a hostname to an IPv6 address.

## What is IPv4?

IPv4 (Internet Protocol version 4) is the fourth version of the Internet Protocol, widely used for assigning IP addresses.

### Characteristics of IPv4

- **Address Size:** 32-bit, allowing for approximately 4.3 billion unique addresses.
- **Address Notation:** Dotted-decimal (e.g., `192.168.1.1`).

### Limitations of IPv4

- **Limited Address Space:** Only approximately 4.3 billion addresses, insufficient for the growing number of internet devices.
- **Lack of Built-in Security:** Vulnerable to attacks like spoofing and denial-of-service.
- **No Mobility Support:** Not designed for mobile devices like smartphones and laptops.

### IPv6 as a Solution

IPv6 addresses these limitations with a larger address space, built-in security features, and support for mobile devices.

## What is IPv6?

IPv6 (Internet Protocol version 6) is designed to replace IPv4, offering a much larger address space and additional features.

### Characteristics of IPv6

- **Address Size:** 128-bit, allowing for approximately 3.4×10^38 unique addresses.
- **Address Notation:** Hexadecimal (e.g., `2001:0db8:85a3:08d3:1319:8a2e:0370:7334`).

### Advantages of IPv6

- **Larger Address Space:** Vastly more addresses than IPv4.
- **Built-in Security:** Features like IPsec for enhanced security.
- **Mobility Support:** Designed to handle mobile devices seamlessly.

### IPv6 Adoption

While IPv6 is gradually being adopted, IPv4 is still widely used. However, IPv6 is expected to eventually replace IPv4.

## IPv4 vs IPv6

### Comparison

| Feature             | IPv4                         | IPv6                                     |
|---------------------|------------------------------|------------------------------------------|
| Address Size        | 32 bits                      | 128 bits                                 |
| Unique Addresses    | Approximately 4.3 billion    | Approximately 3.4×10^38                  |
| Address Notation    | Dotted-decimal (e.g., `192.168.1.1`) | Hexadecimal (e.g., `2001:0db8:85a3:08d3:1319:8a2e:0370:7334`) |
| Security            | No built-in security         | Built-in security (IPsec)                |
| Mobility Support    | Not designed for mobility    | Designed for mobility                    |

### Key Differences

- **Address Space:** IPv6 supports a vastly larger number of devices.
- **Security:** IPv6 includes built-in security features.
- **Mobility:** IPv6 is better suited for mobile devices.

## Database (DB)

A database is an organized collection of structured data stored electronically. It is managed by a Database Management System (DBMS), which allows for data storage, retrieval, updating, and deletion.

### Key Points

- **Organized Collection:** Data is organized, often in tables with rows and columns.
- **Structured Data:** Data follows a defined format, adhering to specific data types and rules.
- **Electronically Stored:** Databases are stored on computers, enabling efficient access and management.
- **DBMS:** Software that interacts with the database, facilitating data operations and access control.

### Real-world Examples

- **E-commerce:** Databases store information about products, customers, and orders.
- **Libraries:** Databases catalog books, authors, and patrons.
- **Hospitals:** Databases manage patient medical records.

### Types of Databases

1. **Relational Databases:** Organized in tables with relationships between them (e.g., MySQL, Oracle, PostgreSQL).
2. **NoSQL Databases:** Flexible data structures for unstructured or semi-structured data (e.g., MongoDB, Redis, Neo4j).
3. **Object-Oriented Databases:** Store data as objects, suitable for complex data structures (e.g., GemStone, ObjectStore).
4. **Cloud Databases:** Hosted on cloud platforms, offering scalability and ease of management (e.g., AWS, Azure).

### Choosing the Right Database

Consider data structure, size, scalability, performance requirements, and query complexity.

## Database Management System (DBMS)

A DBMS is a collection of programs that enable users to access and manage a database efficiently.

## Web Server vs Application Server

### Web Server

A web server is a computer that serves web content (HTML, CSS, JavaScript) to clients via the internet.

### Application Server

An application server provides an environment for running specific applications, often involving business logic, data processing, and backend services.

### Key Differences

- **Web Server:** Delivers web pages to clients.
- **Application Server:** Manages business logic and application services.

## HTTP vs HTTPS

### HTTP

Hypertext Transfer Protocol (HTTP) is used for transferring data over the internet using methods like GET and POST.

### HTTPS

Hypertext Transfer Protocol Secure (HTTPS) is the secure version of HTTP. It encrypts data transferred between the client and server, enhancing security.

### SSL vs TLS

- **SSL (Secure Socket Layer):** An older encryption method for securing data.
- **TLS (Transport Layer Security):** An improved version of SSL, offering better security.

### Ports

- **Port 80:** Used for HTTP, offers fast connections but is insecure.
- **Port 443:** Used for HTTPS, offers secure connections but can be slower.

---
## What is System Redundancy?

System redundancy refers to the principle of duplicating critical components or systems to ensure continued operation in case of component failure or maintenance.

## Lamp
Linux
Apache
MySQL
Php/perl/python

## SPOF 
single point of failure.

Single Point of Failure (SPOF) is a critical concept in system design, referring to a single component or system that, if it fails, can bring the entire system down.

## Query Per Second (QPS)

Query Per Second (QPS) refers to the average number of queries or requests processed by a system, database, or application within a one-second time frame .


---
## some common web-related terms:
1. Server:
    A computer system or software program that provides functionality for other programs or devices known as clients.
2. client:
    is a software program used to connect to a server.
3. Host:
    is a device which store a web app or any resources which later need to be served.
