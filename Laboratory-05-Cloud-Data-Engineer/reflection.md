# Mission Reflection

This laboratory activity helped me understand the differences between cloud storage technologies and how MinIO can be used to provide object storage. I learned that object storage is suitable for applications that need to store millions of photos because it stores data as individual objects with metadata and unique identifiers. Unlike traditional block storage, which divides data into blocks, object storage is designed to manage large amounts of unstructured information.

Using Docker made the deployment of MinIO easier because I could start the server using a single command instead of manually installing and configuring a complete operating system. Docker also allowed me to configure the required ports and login credentials through command options and environment variables. This made the deployment process easier to repeat.

I also learned that a bucket is a logical container used to organize objects in an object storage system. In this activity, I created a bucket named `client-photos` and uploaded a sample file to demonstrate that the storage server was working.

Large enterprise companies can protect their data through techniques such as replication, redundancy, backups, and storing copies across different physical devices or locations. These methods can help maintain data availability if a physical server fails. However, organizations must also configure and test their protection systems properly.

Finally, this activity helped me become more familiar with the Linux command line. I practiced executing Docker commands, checking whether a container was running, and using a web console to manage storage. Although I initially needed guidance, completing the steps helped me understand how command-line tools can be used to deploy and manage cloud services. My GitHub portfolio is also becoming more organized as I add technical documentation and screenshots of my laboratory work.
