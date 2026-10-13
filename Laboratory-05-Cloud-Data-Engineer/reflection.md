# Reflection

In this laboratory activity, I learned about the different types of cloud storage and how they are used in real-world applications. Block Storage is commonly used for virtual machine disks and databases, while File Storage organizes files into folders. Object Storage is more suitable for applications that need to store a large number of photos, videos, and other unstructured data.

Object Storage is a good choice for storing millions of photos because each photo can be stored as an individual object inside a bucket. This makes the files easier to organize and manage as the application grows. Compared with using a traditional hard drive, a cloud object storage service can provide a more scalable way to handle large amounts of uploaded images.

Using Docker made deploying MinIO easier because I could start the storage server with a single command instead of manually installing and configuring every component. I also learned how to use environment variables to configure the administrator username and password. Mapping ports 9000 and 9001 allowed the storage API and web console to be accessed through the playground environment.

A bucket is a container used to organize objects in cloud storage. In this activity, the `client-photos` bucket represents a place where a photo-sharing application could store uploaded images. Creating the bucket and uploading a sample file helped me understand how object storage works in practice.

Large companies protect their stored data by using backups, replication, redundancy, access controls, and monitoring. These methods can help reduce the risk of losing data when a physical server fails. However, the exact protection depends on how the storage system is configured.

Finally, this activity helped me become more familiar with the Linux command line. Running Docker commands and checking the status of a container helped me understand how to manage a service in a cloud environment. I still need more practice, but I feel more confident following technical instructions and troubleshooting basic problems. This experience will be useful as I continue learning cloud computing and infrastructure management.
