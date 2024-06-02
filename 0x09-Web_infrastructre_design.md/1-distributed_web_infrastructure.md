
![[Pasted image 20240601220044.png]]

![[Untitled (3).png]]

---

## Description

The image shows a high-level overview of a web infrastructure that hosts the website www.foobar.com.

**Components:**

* **Load Balancer (HAProxy):** Distributes incoming HTTP requests evenly across multiple servers, preventing any single server from becoming overloaded.
* **Servers:** Two servers, each running a web server (Nginx) and an application server (PHP), ensuring redundancy and improved load handling.
* **Application Files (PHP Code Base):** PHP scripts and other code files that are executed by the application servers.
* **Database (MySQL):** Stores the website's data, such as user information or product details, allowing for easy access, management, and updates.
* **Domain Name:** A human-readable alias for an IP address (e.g., www.foobar.com vs. 8.8.8.8). The mapping between domain names and IP addresses is handled by the Domain Name System (DNS).
* **DNS Record:** A specific record type in DNS that maps a domain name to an IP address. In this case, www.foobar.com uses an A record, mapping the domain to the IP address 8.8.8.8.

**Additional Elements:**

* **HAProxy Load Balancer:** 
  * **Distribution Algorithm:** Configured with a Round Robin algorithm.
  * **How it Works:** The Round Robin algorithm distributes incoming requests sequentially across the available servers. When a request arrives, it is sent to the next server in the list. After reaching the last server, it cycles back to the first server. This method ensures that all servers receive an equal share of the load, helping to balance traffic and improve performance.
  * **Setup Type:** Enables an Active-Active setup.

* **Active-Active Setup:** 
  * **Explanation:** In an Active-Active setup, both servers are active simultaneously, handling requests concurrently. This setup maximizes resource usage and availability because all servers share the load and can serve traffic at the same time. If one server fails, the other servers continue to handle the requests without any disruption.
  
* **Primary-Replica Database Cluster:** 
  * **Explanation:** A Primary (Master) node handles all write operations, and one or more Replica (Slave) nodes handle read operations. This setup improves performance and provides redundancy, as read traffic is offloaded to the replicas.

**Difference Between Active-Active and Active-Passive Setups:**

* **Active-Active Setup:** 
  * **Functionality:** All servers are active and handle requests simultaneously.
  * **Advantages:** Maximizes resource utilization and availability. If one server fails, others continue to handle requests without interruption.
  * **Example:** The described infrastructure, where both servers are active and handle requests distributed by HAProxy.
  
* **Active-Passive Setup:**
  * **Functionality:** One server (active) handles all requests, while the other server (passive) remains on standby. The passive server takes over only if the active server fails.
  * **Advantages:** Simple to configure and manage. Ensures availability during server failure.
  * **Disadvantages:** Underutilizes resources, as the passive server is idle most of the time. Potential downtime during the failover process.
  * **Example:** If one of the two servers were configured as a standby server, only becoming active when the primary server fails.

## Issues With This Infrastructure:

* **Single Point of Failure (SPOF):** While HAProxy mitigates some risks, the load balancer itself can be a SPOF if not made redundant. Additionally, the single database can be a SPOF if not configured with redundancy.
* **Security Issues:** 
  - **No Firewall:** Servers are left exposed to potential attacks.
  - **No HTTPS:** Data transmitted in plain text is vulnerable to interception.
* **No Monitoring:** Without monitoring tools, it is challenging to detect and respond to issues in real-time, which can lead to prolonged downtimes and performance degradation.

## Benefits of Adding a Firewall:

* **Enhanced Security:** Firewalls monitor and control incoming and outgoing network traffic based on predetermined security rules, providing a barrier between trusted and untrusted networks.
* **Protection Against Attacks:** Helps protect servers from various types of cyber-attacks, such as Distributed Denial of Service (DDoS) attacks, by filtering malicious traffic.
* **Access Control:** Allows administrators to enforce policies regarding which traffic is allowed to reach the servers, blocking unauthorized access and potentially harmful traffic.
* **Network Segmentation:** Can be used to segment different parts of the network, adding another layer of security by isolating different services and servers from each other.

**Additional Considerations for Scalability and Reliability:**

* **Proxy Servers:** Can improve performance and reduce load on the main web servers by caching frequently accessed content.
* **Redundant Load Balancers:** Implementing multiple load balancers in an active-passive configuration can eliminate the load balancer as a SPOF.
* **HTTPS:** Using HTTPS to encrypt data in transit ensures that data cannot be intercepted and read by unauthorized parties.
* **Monitoring Tools:** Using monitoring tools to track server health, performance, and uptime, enabling quick response to any issues that arise.

This infrastructure provides a balanced approach to handling web traffic with redundancy and load distribution, though further enhancements are necessary to address SPOFs, security, and monitoring concerns.

بالتأكيد، سأشرح النقاط الثلاثة بالتفصيل بالعربي:

1. **نقطة فشل واحدة (SPOF):**
   - المشكلة: عندما يكون هناك عنصر واحد في البنية التحتية يكون هو المسؤول عن توفير الخدمة بأكملها، فإن هذا العنصر يصبح نقطة فشل واحدة. إذا فشلت هذه النقطة، سيؤدي ذلك إلى تعطيل الخدمة بأكملها.
   - في البنية التحتية الموضحة:
     - نقاط فشل واحدة: الحمولة الموجهة والقاعدة البياناتية. إذا فشلت إحدى هذه العناصر، فإن الموقع بأكمله سيكون غير متاح.

2. **مشاكل الأمان (عدم وجود جدار ناري، عدم وجود HTTPS):**
   - المشكلة: عدم وجود جدار ناري يعرض البنية التحتية للهجمات الإلكترونية ويمكن للمهاجمين استغلال الثغرات الأمنية للوصول إلى البيانات أو تعطيل الخدمة.
   - بالإضافة إلى ذلك، عدم استخدام HTTPS يجعل البيانات التي ترسل بين المتصفح والخادم عرضة للاعتراض والتجسس، مما يمثل تهديدًا للخصوصية والأمان للمستخدمين.

3. **عدم التوجيه:**
   - المشكلة: عدم وجود أدوات لرصد ومراقبة أداء البنية التحتية يعني أن المشرفين لا يمكنهم اكتشاف المشاكل بسرعة أو الاستجابة لها. هذا يمكن أن يؤدي إلى تدهور أداء الخدمة وتوقفها بشكل مفاجئ دون تنبيه مسبق.

باختصار، هذه النقاط الثلاثة تمثل تحديات رئيسية في البنية التحتية الموضحة، حيث تؤثر على الأمان والاستقرار وقدرة الموقع على تقديم الخدمة بشكل فعال وموثوق به.
---
خوارزميات التوزيع لميزان التحميل (Load Balancer Algorithms) تعتمد على كيفية توجيه حركة المرور بين الخوادم المتاحة لضمان توزيع الحمل بشكل فعال وعادل. من بين الخوارزميات الشائعة:

1. **Round Robin**: يتم توجيه كل طلب جديد إلى الخادم التالي في قائمة الخوادم بشكل دوري. هذا يعني أن كل خادم يتلقى نفس العدد من الطلبات تقريبًا.

2. **Least Connections (أقل الاتصالات)**: يتم توجيه الطلب إلى الخادم الذي يقل عدد الاتصالات النشطة عليه. يستخدم هذا الخوارزمية لتجنب تحميل الخوادم الشاغرة.

3. **Least Response Time (أقل وقت استجابة)**: يتم توجيه الطلب إلى الخادم الذي يستجيب بأقل وقت. يهدف هذا الخوارزمية إلى تقليل وقت الاستجابة الشامل للنظام.

4. **IP Hashing (تجزئة عنوان الآي بي)**: يتم توجيه الطلبات استنادًا إلى عنوان الآي بي للمستخدم. يتيح ذلك توجيه نفس المستخدم دائمًا إلى نفس الخادم، مما يسهل عمليات الحفاظ على جلسة المستخدم.

5. **Weighted Round Robin**: يشابه خوارزمية Round Robin، ولكن يتم تعيين وزن مختلف لكل خادم بحيث يحصل الخادم ذو الوزن الأعلى على نسبة أكبر من الطلبات.

هذه بعض الخوارزميات الشائعة، وهناك المزيد من الخوارزميات المتاحة حسب احتياجات التوزيع المحددة لكل نظام وتطبيق.

Load Balancer Algorithms determine how traffic is directed among available servers to ensure effective and fair load distribution. Among the common algorithms are:

1. **Round Robin**: Each new request is directed to the next server in the list of servers in a circular manner. This means each server receives roughly the same number of requests.

2. **Least Connections**: Requests are directed to the server with the fewest active connections. This algorithm aims to avoid overloading servers with fewer active connections.

3. **Least Response Time**: Requests are directed to the server with the lowest response time. This algorithm aims to minimize the overall system response time.

4. **IP Hashing**: Requests are directed based on the user's IP address. This allows the same user to be directed consistently to the same server, facilitating session persistence.

5. **Weighted Round Robin**: Similar to Round Robin, but each server is assigned a different weight, so servers with higher weights receive a larger share of requests.

These are some common algorithms, and there are more available depending on the specific distribution needs of each system and application.
---

الفرق بين الخادم الرئيسي والخادم النسخي فيما يتعلق بالتطبيق يكمن في الوظائف التي يقوم كل منهما بها:

1. **الخادم الرئيسي (الماستر)**:
   - يتولى الخادم الرئيسي جميع العمليات الكتابية في التطبيق، مثل إدخال البيانات، وتحديثها، وحذفها.
   - يعتبر المصدر الرئيسي للبيانات حيث يتم تنفيذ جميع التعديلات الحقيقية على قاعدة البيانات.

2. **الخادم النسخي (السلاف)**:
   - يستخدم الخادم النسخي لتلبية العمليات القرائية في التطبيق، مثل استعراض البيانات أو استعلامات البحث.
   - يقوم بتلقي التحديثات من الخادم الرئيسي وتطبيقها على قاعدة بياناته الخاصة للحفاظ على نسخة محدثة من البيانات.

باختصار، الخادم الرئيسي هو المكان الذي يتم فيه إجراء التعديلات الفعلية على البيانات، بينما يتم استخدام الخادم النسخي للقراءة من البيانات ويكون مزودًا بنسخة محدثة من البيانات التي يمكن الوصول إليها بشكل فوري.

The difference between the Primary node and the Replica node regarding the application lies in the functions each performs:

1. **Primary Node (Master)**:
   - The primary node handles all write operations in the application, such as data insertion, updates, and deletion.
   - It serves as the primary source of data where all actual modifications to the database occur.

2. **Replica Node (Slave)**:
   - The replica node is used to fulfill read operations in the application, such as data browsing or search queries.
   - It receives updates from the primary node and applies them to its own database copy to maintain an updated version of the data.

In summary, the primary node is where actual data modifications take place, while the replica node is used for reading data and is provided with an up-to-date copy of the data that can be accessed immediately.
---

A Primary-Replica (or Master-Slave) database cluster is a configuration where data replication is used to maintain copies of the database across multiple servers. Here’s a detailed explanation of how this setup works:

### Overview
- **Primary (Master)**: The primary database server handles all the write operations (inserts, updates, deletes). It is the source of truth where data modifications occur.
- **Replicas (Slaves)**: The replica servers handle read operations. They receive updates from the primary server to maintain an up-to-date copy of the data.

### How It Works
1. **Write Operations**:
   - All write operations are directed to the primary server.
   - When a data modification occurs, the primary server logs these changes (often in a binary log).

2. **Replication**:
   - The replicas continuously or periodically read the changes from the primary server’s log.
   - They apply these changes to their own copies of the database, keeping them synchronized with the primary server.

1. **Read Operations**:
   - Read operations can be directed to any of the replica servers.
   - This distribution of read queries can significantly reduce the load on the
نظام الـ Primary-Replica (الرئيسي-النسخة) في قواعد البيانات يتضمن إعدادًا يعتمد على تكرار البيانات للحفاظ على نسخ متطابقة من قاعدة البيانات عبر عدة خوادم. إليك شرح مفصل لكيفية عمل هذا النظام:

### نظرة عامة
- **الرئيسي (الماستر)**: يتولى الخادم الرئيسي جميع العمليات الكتابية (إدخال، تحديث، حذف). إنه مصدر الحقيقة حيث تحدث التعديلات على البيانات.
- **النسخ (السلاف)**: يتولى خوادم النسخ استقبال العمليات القرائية. يتلقون التحديثات من الخادم الرئيسي للحفاظ على نسخة محدثة من البيانات.

### كيف يعمل النظام
1. **عمليات الكتابة**:
   - يُوجه جميع عمليات الكتابة إلى الخادم الرئيسي.
   - عند حدوث تعديل على البيانات، يقوم الخادم الرئيسي بتسجيل هذه التغييرات (غالبًا في سجل ثنائي).

2. **التكرار**:
   - تقوم النسخ بقراءة التغييرات بشكل مستمر أو دوري من سجل التغييرات في الخادم الرئيسي.
   - يقومون بتطبيق هذه التغييرات على نسخهم الخاصة من قاعدة البيانات، ليحافظوا على مزامنتها مع الخادم الرئيسي.

3. **عمليات القراءة**:
   - يمكن توجيه عمليات القراءة إلى أي من خوادم النسخ.
   - يمكن أن تُسهم هذه التوزيعية في عمليات القراءة في تقليل الحمل على الخادم الرئيسي وتحسين الأداء وقابلية التوسع.

### المزايا
- **توازن الحمل**: من خلال توجيه العمليات القرائية إلى خوادم النسخ، يمكن تقليل الحمل على الخادم الرئيسي بشكل كبير، مما يعزز الأداء وقابلية التوسع.
---


