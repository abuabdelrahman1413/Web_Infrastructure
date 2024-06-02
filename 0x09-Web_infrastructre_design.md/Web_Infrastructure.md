# <span style="color: #007bff;">Web Infrastructure Overview</span>

## <span style="color: #28a745;">Domain Name System (DNS)</span>

### <span style="color: #dc3545;">What is DNS?</span>
DNS stands for Domain Name System. It functions like a phonebook for the internet, translating human-readable domain names into IP addresses.

### <span style="color: #dc3545;">How DNS Works</span>

1. **User Input:** A user enters a domain name into their web browser, for example, `example.com`.
2. **Initial Request:** The user's computer sends a request to a DNS server asking for the IP address of the domain name.
3. **Cache Check:** The DNS server checks its cache. If it has the IP address stored, it returns it to the user's computer.
4. **Forwarding Request:** If the DNS server does not have the IP address in its cache, it forwards the request to another DNS server. This process continues until a DNS server with the IP address is found.
5. **Response:** Once the IP address is found, it is returned to the user's computer.
6. **Connection:** The user's computer uses the IP address to connect to the website.

### <span style="color: #dc3545;">DNS Hierarchy</span>
DNS is hierarchical. At the top are root DNS servers, containing IP addresses of top-level domains (TLDs) like `.com` and `.org`. TLD DNS servers have IP addresses of second-level domains (SLDs) such as `example.com`. SLD DNS servers hold IP addresses of individual websites.

### <span style="color: #dc3545;">DNS Distribution</span>
DNS is distributed, meaning there are many DNS servers around the world. This distribution ensures DNS availability even if some servers fail.

### <span style="color: #dc3545;">Importance of DNS</span>
DNS is essential for the internet, allowing users to access websites using domain names instead of IP addresses.

### <span style="color: #dc3545;">Types of DNS Records</span>
1. **A Record (Address Record):** Maps a hostname to an IPv4 address.
2. **MX Record (Mail Exchange):** Directs email to a domain’s mail server.
3. **NS Record (Name Server):** Delegates a domain to a specific DNS server.
4. **AAAA Record:** Maps a hostname to an IPv6 address.

## <span style="color: #28a745;">Internet Protocol Versions</span>

### <span style="color: #dc3545;">What is IPv4?</span>
IPv4 (Internet Protocol version 4) is the fourth version of the Internet Protocol, widely used for assigning IP addresses.

#### <span style="color: #dc3545;">Characteristics of IPv4</span>
- **Address Size:** 32-bit, allowing for approximately 4.3 billion unique addresses.
- **Address Notation:** Dotted-decimal (e.g., `192.168.1.1`).

#### <span style="color: #dc3545;">Limitations of IPv4</span>
- **Limited Address Space:** Only approximately 4.3 billion addresses, insufficient for the growing number of internet devices.
- **Lack of Built-in Security:** Vulnerable to attacks like spoofing and denial-of-service.
- **No Mobility Support:** Not designed for mobile devices like smartphones and laptops.

### <span style="color: #dc3545;">What is IPv6?</span>
IPv6 (Internet Protocol version 6) is designed to replace IPv4, offering a much larger address space and additional features.

#### <span style="color: #dc3545;">Characteristics of IPv6</span>
- **Address Size:** 128-bit, allowing for approximately 3.4×10^38 unique addresses.
- **Address Notation:** Hexadecimal (e.g., `2001:0db8:85a3:08d3:1319:8a2e:0370:7334`).

#### <span style="color: #dc3545;">Advantages of IPv6</span>
- **Larger Address Space:** Vastly more addresses than IPv4.
- **Built-in Security:** Features like IPsec for enhanced security.
- **Mobility Support:** Designed to handle mobile devices seamlessly.

### <span style="color: #dc3545;">IPv4 vs IPv6</span>

| Feature             | IPv4                         | IPv6                                     |
|---------------------|------------------------------|------------------------------------------|
| Address Size        | 32 bits                      | 128 bits                                 |
| Unique Addresses    | Approximately 4.3 billion    | Approximately 3.4×10^38                  |
| Address Notation    | Dotted-decimal (e.g., `192.168.1.1`) | Hexadecimal (e.g., `2001:0db8:85a3:08d3:1319:8a2e:0370:7334`) |
| Security            | No built-in security         | Built-in security (IPsec)                |
| Mobility Support    | Not designed for mobility    | Designed for mobility                    |

## <span style="color: #28a745;">Database (DB)</span>

### <span style="color: #dc3545;">What is a Database?</span>
A database is an organized collection of structured data stored electronically. It is managed by a Database Management System (DBMS), which allows for data storage, retrieval, updating, and deletion.

#### <span style="color: #dc3545;">Key Points</span>
- **Organized Collection:** Data is organized, often in tables with rows and columns.
- **Structured Data:** Data follows a defined format, adhering to specific data types and rules.
- **Electronically Stored:** Databases are stored on computers, enabling efficient access and management.
- **DBMS:** Software that interacts with the database, facilitating data operations and access control.

#### <span style="color: #dc3545;">Real-world Examples</span>
- **E-commerce:** Databases store information about products, customers, and orders.
- **Libraries:** Databases catalog books, authors, and patrons.
- **Hospitals:** Databases manage patient medical records.

#### <span style="color: #dc3545;">Types of Databases</span>
1. **Relational Databases:** Organized in tables with relationships between them (e.g., MySQL, Oracle, PostgreSQL).
2. **NoSQL Databases:** Flexible data structures for unstructured or semi-structured data (e.g., MongoDB, Redis, Neo4j).
3. **Object-Oriented Databases:** Store data as objects, suitable for complex data structures (e.g., GemStone, ObjectStore).
4. **Cloud Databases:** Hosted on cloud platforms, offering scalability and ease of management (e.g., AWS, Azure).

### <span style="color: #dc3545;">Database Management System (DBMS)</span>
A DBMS is a collection of programs that enable users to access and manage a database efficiently.

## <span style="color: #28a745;">Web and Application Servers</span>

### <span style="color: #dc3545;">Web Server</span>
A web server is a computer that serves web content (HTML, CSS, JavaScript) to clients via the internet.

### <span style="color: #dc3545;">Application Server</span>
An application server provides an environment for running specific applications, often involving business logic, data processing, and backend services.

#### <span style="color: #dc3545;">Key Differences</span>
- **Web Server:** Delivers web pages to clients.
- **Application Server:** Manages business logic and application services.

## <span style="color: #28a745;">HTTP vs HTTPS</span>

### <span style="color: #dc3545;">HTTP</span>
Hypertext Transfer Protocol (HTTP) is used for transferring data over the internet using methods like GET and POST.

### <span style="color: #dc3545;">HTTPS</span>
Hypertext Transfer Protocol Secure (HTTPS) is the secure version of HTTP. It encrypts data transferred between the client and server, enhancing security.

#### <span style="color: #dc3545;">SSL vs TLS</span>
- **SSL (Secure Socket Layer):** An older encryption method for securing data.
- **TLS (Transport Layer Security):** An improved version of SSL, offering better security.

#### <span style="color: #dc3545;">Ports</span>
- **Port 80:** Used for HTTP, offers fast connections but is insecure.
- **Port 443:** Used for HTTPS, offers secure connections but can be slower.

## <span style="color: #28a745;">System Redundancy</span>

### <span style="color: #dc3545;">What is System Redundancy?</span>
System redundancy refers to the principle of duplicating critical components or systems to ensure continued operation in case of component failure or maintenance.

## <span style="color: #28a745;">Common Web-related Terms</span>

1. **Server:** A computer system or software program that provides functionality for other programs or devices known as clients.
2. **Client:** A software program used to connect to a server.
3. **Host:** A device that stores a web app or any resources which later need to be served; also any device that has established a connection to a network.
4. **Localhost:** Refers to the local computer you are using as a host.
5. **IP Address:** A numerical label assigned to each device connected to a computer network that uses the Internet Protocol for communication. For example, `127.0.0.1` is the loopback address, similar to a building number in an address system.
6. **Port:** A location where information is sent and received on a networked device like department number apache 80
7. **HTTP:** Hypertext transfer protocol 
8. **HTTP Session:** is a sequence of network request-response transactions
9. **HTTP Requests Methods:** get, post, put, delete, ... etc
10. **HTTP Response message** Status code 200 ... etc
11. HTTPS: secure data transmission.

## <span style="color: #28a745;">LAMP Stack</span>

### <span style="color: #dc3545;">What is LAMP?</span>
LAMP stands for Linux, Apache, MySQL, and PHP/Perl/Python. It is a stack of software used to build dynamic websites and web applications.

## <span style="color: #28a745;">Single Point of Failure (SPOF)</span>

### <span style="color: #dc3545;">What is SPOF?</span>
Single Point of Failure (SPOF) is a critical concept in system design, referring to a single component or system that, if it fails, can bring the entire system down.

## <span style="color: #28a745;">Query Per Second (QPS)</span>

### <span style="color: #dc3545;">What is QPS?</span>
Query Per Second (QPS) refers to the average number of queries or requests processed by a system, database, or application within a one-second time frame.

## <span style="color: #28a745;">URLs</span>

### <span style="color: #dc3545;">What is a URL?</span>
A URL (Uniform Resource Locator) is the address you type into a web browser to visit a specific web page or resource on the internet. It tells the browser where to find the resource.

### <span style="color: #dc3545;">Components of a URL</span>
1. **Protocol:** The method of accessing the resource. Common protocols are `http://` and `https://`.
2. **Domain Name:** The name of the website. For example, `www.example.com`.
3. **Path:** The specific location of a resource on the website. For example, `/about` in `www.example.com/about`.
4. **Parameters:** Extra data sent to the server, often used in web forms or searches. For example, `?id=123` in `www.example.com/search?id=123`.

### <span style="color: #dc3545;">Example</span>
In the URL `https://www.example.com/about?id=123`:
- `https` is the protocol.
- `www.example.com` is the domain name.
- `/about` is the path.
- `?id=123` is a parameter.

>  In simple terms, a URL is the address you use to access specific pages or resources on the web.

## <span style="color: #28a745;">HTTP Request</span>

### <span style="color: #dc3545;">What is an HTTP Request?</span>
An HTTP request is a message sent by a client (usually a web browser) to a server asking for a specific resource on the web. 

### <span style="color: #dc3545;">Components of an HTTP Request</span>

1. **Request Line**: Indicates the HTTP method, the resource URL, and the HTTP version.
2. **Headers**: Provide additional information about the request.
3. **Body**: Contains data sent to the server (only for methods like POST, PUT, etc.).

### <span style="color: #dc3545;">Example of an HTTP GET Request</span>

#### <span style="color: #dc3545;">Scenario: Accessing a Web Page</span>

Let's say you're visiting the homepage of `www.example.com`.

#### <span style="color: #dc3545;">Request Line</span>
- **GET**: The HTTP method used to request data.
- **/**: The resource path, in this case, the homepage.
- **HTTP/1.1**: The HTTP version.

#### <span style="color: #dc3545;">Headers</span>
- **Host**: Specifies the domain name of the server.
- **User-Agent**: Information about the client making the request (browser type and version).
- **Accept**: Types of content the client can process.
- **Accept-Language**: Preferred languages for the response.
- **Accept-Encoding**: Types of content encoding the client can handle.
- **Connection**: Controls whether the connection stays open after the current transaction.

#### <span style="color: #dc3545;">Body</span>
For a GET request, the body is usually empty because the client is only requesting data.

### <span style="color: #dc3545;">Real-Life Analogy</span>

Think of an HTTP request as a letter you send to a company to ask for information:

1. **Request Line**: The letter's subject line.
   - "Subject: Request for Company Information"

2. **Headers**: Additional details included in the letter's header.
   - "To: Customer Service, Example Company"
   - "From: John Doe"
   - "User-Agent: Firefox/91.0 (Windows NT 10.0)"
   - "Accept: Application form, Brochure"
   - "Preferred-Language: English"

3. **Body**: The content of the letter.
   - For a simple information request, the body might be empty or very brief: "Please send me your company's information."

### <span style="color: #dc3545;">Full Example</span>

Here’s how the complete HTTP GET request looks:

> When this request is sent, the web server at www.example.com processes it and responds with the requested web page, which the browser then displays to you.

## <span style="color: #28a745;">HTTP Response</span>

### <span style="color: #dc3545;">What is an HTTP Response?</span>
An HTTP response is a message sent by a server to a client (such as a web browser) containing the requested resource or providing information about the request. 

### <span style="color: #dc3545;">Components of an HTTP Response</span>

1. **Status Line**: Indicates the HTTP version, status code, and a brief message about the status.
2. **Headers**: Provide additional information about the response.
3. **Body**: Contains the actual content being sent back to the client.

### <span style="color: #dc3545;">Example of an HTTP Response</span>

#### <span style="color: #dc3545;">Scenario: Accessing a Web Page</span>

Continuing with the example of visiting the homepage of `www.example.com`.

#### <span style="color: #dc3545;">Status Line</span>
- **HTTP/1.1**: The HTTP version.
- **200 OK**: The status code indicating that the request was successful.

#### <span style="color: #dc3545;">Headers</span>
- **Date**: The date and time the response was sent.
- **Server**: The server software being used.
- **Content-Type**: The type of content being sent (in this case, HTML).
- **Content-Length**: The length of the content being sent (in bytes).

#### <span style="color: #dc3545;">Body</span>
The body contains the actual HTML content of the homepage.

### <span style="color: #dc3545;">Real-Life Analogy</span>

Think of an HTTP response as a package you receive in response to your letter:

1. **Status Line**: The label on the package indicating its status.
   - "Status: Package Delivered"

2. **Headers**: Additional information provided on a note attached to the package.
   - "From: Example Company"
   - "Date: June 5, 2022"
   - "Content-Type: Brochure"

3. **Body**: The contents of the package itself.
   - Inside the package, you find the company's brochure and other requested information.
