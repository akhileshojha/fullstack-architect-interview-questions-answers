Certainly! Here are some MongoDB interview questions along with their answers:

### Basic Questions

1. **What is MongoDB?**
   - **Answer**: MongoDB is a NoSQL, document-oriented database designed for high performance, high availability, and easy scalability. It stores data in flexible, JSON-like documents, meaning fields can vary from document to document and data structure can be changed over time.

2. **What are the key features of MongoDB?**
   - **Answer**: Key features of MongoDB include:
     - **Flexible Schema**: Documents can have different structures.
     - **Indexing**: Supports various types of indexing for efficient query execution.
     - **Replication**: Provides high availability through replica sets.
     - **Sharding**: Allows horizontal scaling by distributing data across multiple machines.
     - **Aggregation Framework**: For advanced data processing and transformation.
     - **File Storage**: GridFS for storing large files.

3. **What is a document in MongoDB?**
   - **Answer**: A document in MongoDB is a data structure composed of field and value pairs. Documents are similar to JSON objects and are the basic unit of data in MongoDB.

4. **What is a collection in MongoDB?**
   - **Answer**: A collection is a group of MongoDB documents. Collections are similar to tables in relational databases. Documents within a collection can have different fields.

5. **What is a replica set in MongoDB?**
   - **Answer**: A replica set in MongoDB is a group of MongoDB instances that maintain the same data set. It provides redundancy and high availability by automatically failing over to a secondary replica if the primary replica fails.

6. **What is sharding in MongoDB?**
   - **Answer**: Sharding is a method for distributing data across multiple machines. MongoDB uses sharding to support deployments with large data sets and high-throughput operations by distributing data across multiple shards.

7. **What are indexes in MongoDB?**
   - **Answer**: Indexes in MongoDB are special data structures that store a small portion of the data set in an easy-to-traverse form. They improve the speed of data retrieval operations but require additional storage and can affect write performance.

8. **What is the difference between a primary and secondary replica in MongoDB?**
   - **Answer**: In a replica set, the primary replica is the node that receives all write operations. The secondary replicas replicate the primary's data and can serve read operations if configured. If the primary fails, one of the secondaries is promoted to primary.

9. **Explain the Aggregation Framework in MongoDB.**
   - **Answer**: The Aggregation Framework in MongoDB is a powerful tool for performing data aggregation operations such as filtering, grouping, and transforming data. It uses an aggregation pipeline, where documents pass through a sequence of stages that perform various operations.

10. **What is GridFS in MongoDB?**
    - **Answer**: GridFS is a specification for storing and retrieving large files in MongoDB. It splits files into smaller chunks and stores each chunk as a separate document. GridFS is used for storing files that exceed the BSON-document size limit of 16 MB.

### Intermediate Questions

11. **What is the BSON format in MongoDB?**
    - **Answer**: BSON (Binary JSON) is a binary representation of JSON-like documents. BSON extends the JSON model to provide additional data types and to be efficient for encoding and decoding within different programming languages.

12. **How does MongoDB ensure data consistency?**
    - **Answer**: MongoDB ensures data consistency through replica sets. Write operations are performed on the primary replica and replicated to secondary replicas. Additionally, MongoDB supports ACID transactions for multi-document operations, ensuring data consistency.

13. **What are the different types of indexes in MongoDB?**
    - **Answer**: MongoDB supports several types of indexes, including:
      - **Single Field Index**: Index on a single field.
      - **Compound Index**: Index on multiple fields.
      - **Multikey Index**: Index for arrays, indexing each element of the array.
      - **Geospatial Index**: Index for geospatial queries.
      - **Text Index**: Index for text search.
      - **Hashed Index**: Index for hashed values of the field.

14. **How does MongoDB handle transactions?**
    - **Answer**: MongoDB supports multi-document ACID transactions, allowing multiple operations to be executed in a transaction with all-or-nothing guarantees. Transactions provide atomicity, consistency, isolation, and durability across multiple documents and collections.

15. **Explain the difference between `find()` and `findOne()` in MongoDB.**
    - **Answer**: The `find()` method retrieves all documents that match the query criteria, returning a cursor to iterate over the result set. The `findOne()` method retrieves a single document that matches the query criteria, returning the first document found.

16. **What is a capped collection in MongoDB?**
    - **Answer**: A capped collection is a fixed-size collection that maintains insertion order. When the specified size limit is reached, the oldest documents are automatically overwritten by the newest documents. Capped collections are useful for maintaining recent log data.

17. **How do you create a text index in MongoDB?**
    - **Answer**: A text index can be created using the `createIndex()` method with the `text` option:
      ```javascript
      db.collection.createIndex({ field: "text" });
      ```
      This enables text search capabilities on the specified field.

18. **What are the benefits of using MongoDB Atlas?**
    - **Answer**: MongoDB Atlas is a fully managed cloud database service that provides benefits such as:
      - Automated backups and restores
      - Easy scalability
      - High availability with automated failover
      - Advanced security features
      - Performance monitoring and optimization tools
      - Integrated support for global clusters

19. **What is the purpose of the `$lookup` aggregation stage?**
    - **Answer**: The `$lookup` aggregation stage allows you to perform a left outer join with another collection. It adds a new array field to each document in the input collection, containing matching documents from the joined collection:
      ```javascript
      db.collection.aggregate([
        {
          $lookup: {
            from: "otherCollection",
            localField: "localField",
            foreignField: "foreignField",
            as: "joinedField"
          }
        }
      ]);
      ```

20. **How does MongoDB handle large data sets?**
    - **Answer**: MongoDB handles large data sets using sharding, which distributes data across multiple machines. Each shard contains a subset of the data, and the cluster as a whole can handle large data volumes and high-throughput operations by horizontally scaling.

### Advanced Questions

21. **Explain the concept of horizontal scaling in MongoDB.**
    - **Answer**: Horizontal scaling, or sharding, involves partitioning data across multiple servers or shards. Each shard holds a subset of the data, and MongoDB distributes queries and operations across shards. This allows for handling larger data sets and higher loads by adding more machines to the cluster.

22. **What is the purpose of the `$unwind` aggregation stage?**
    - **Answer**: The `$unwind` aggregation stage deconstructs an array field from the input documents to output a document for each element in the array. This is useful for processing arrays within documents:
      ```javascript
      db.collection.aggregate([
        { $unwind: "$arrayField" }
      ]);
      ```

23. **What is the difference between `$match` and `$filter` in MongoDB aggregation?**
    - **Answer**: `$match` is an aggregation stage that filters documents based on specified criteria. `$filter` is an aggregation operator that is used within the `$project` stage to filter elements of an array field:
      ```javascript
      // Using $match
      db.collection.aggregate([
        { $match: { status: "active" } }
      ]);

      // Using $filter within $project
      db.collection.aggregate([
        {
          $project: {
            filteredArray: {
              $filter: {
                input: "$arrayField",
                as: "item",
                cond: { $eq: ["$$item.status", "active"] }
              }
            }
          }
        }
      ]);
      ```

24. **How do you perform a geospatial query in MongoDB?**
    - **Answer**: To perform geospatial queries, you need to create a geospatial index and use geospatial query operators such as `$near`, `$geoWithin`, and `$geoIntersects`:
      ```javascript
      // Creating a geospatial index
      db.collection.createIndex({ location: "2dsphere" });

      // Performing a geospatial query
      db.collection.find({
        location: {
          $near: {
            $geometry: {
              type: "Point",
              coordinates: [longitude, latitude]
            },
            $maxDistance: 1000
          }
        }
      });
      ```

25. **What is the `$merge` aggregation stage used for?**
    - **Answer**: The `$merge` aggregation stage writes the results of the aggregation pipeline to a specified collection. It can be used to merge, replace, or update documents in the target collection:
      ```javascript
      db.collection.aggregate([
        { $group: { _id: "$field", total: { $sum: "$value" } } },
        { $merge: { into: "targetCollection", whenMatched: "merge", whenNotMatched: "insert" } }
      ]);
      ```

Sure, here are more MongoDB interview questions and answers starting from number 26:

### Advanced Questions (continued)

26. **Explain the purpose of the WiredTiger storage engine in MongoDB.**
    - **Answer**: WiredTiger is the default storage engine in MongoDB since version 3.2. It offers significant improvements over the previous MMAPv1 storage engine, including:
      - Document-level concurrency control for better write performance.
      - Data compression to reduce storage footprint.
      - Support for various indexing options and configurations.
      - Enhanced memory and cache management.

27. **What are MongoDB transactions, and how do you use them?**
    - **Answer**: MongoDB transactions provide ACID (Atomicity, Consistency, Isolation, Durability) guarantees for multiple document operations. They allow multiple operations on multiple documents (even across multiple collections) to be executed in a transaction. Use the `startSession()` method to begin a session and `withTransaction()` to execute operations within a transaction:
      ```javascript
      const session = client.startSession();
      session.startTransaction();

      try {
        const col1 = db.collection('collection1');
        const col2 = db.collection('collection2');

        await col1.insertOne({ field: 'value' }, { session });
        await col2.insertOne({ field: 'value' }, { session });

        await session.commitTransaction();
      } catch (error) {
        await session.abortTransaction();
      } finally {
        session.endSession();
      }
      ```

28. **What is the Aggregation Pipeline in MongoDB?**
    - **Answer**: The Aggregation Pipeline is a framework for data aggregation, modeled as a data processing pipeline. Documents enter a multi-stage pipeline that transforms them into aggregated results. Stages can filter, sort, group, reshape, and modify documents as they pass through the pipeline.

29. **How do you perform a map-reduce operation in MongoDB?**
    - **Answer**: Map-reduce is a data processing paradigm for condensing large volumes of data into useful aggregated results. Use the `mapReduce()` method to perform map-reduce operations:
      ```javascript
      db.collection.mapReduce(
        function() { emit(this.category, 1); }, // Map function
        function(key, values) { return Array.sum(values); }, // Reduce function
        {
          out: "map_reduce_result" // Output collection
        }
      );
      ```

30. **What is the `bulkWrite` operation in MongoDB?**
    - **Answer**: The `bulkWrite` operation allows you to perform multiple write operations in a single batch, improving performance for bulk operations. It supports insert, update, delete, and replace operations:
      ```javascript
      db.collection.bulkWrite([
        { insertOne: { document: { field: "value" } } },
        { updateOne: { filter: { field: "value" }, update: { $set: { field: "newValue" } } } },
        { deleteOne: { filter: { field: "oldValue" } } }
      ]);
      ```

31. **How does MongoDB handle backup and restore operations?**
    - **Answer**: MongoDB supports several methods for backup and restore operations:
      - **Mongodump and Mongorestore**: Utilities for creating binary backups and restoring data from them.
      - **File System Snapshots**: Consistent backups using file system snapshot tools like LVM or EBS snapshots.
      - **MongoDB Atlas**: Provides automated backup and point-in-time restore capabilities.
      - **Oplog Backup**: Continuously backs up the oplog for replica sets.

32. **What is the oplog in MongoDB?**
    - **Answer**: The oplog (operations log) is a special capped collection that records all changes to the data in a replica set. Each replica set member uses the oplog to replicate changes from the primary to secondaries, ensuring data consistency across the replica set.

33. **Explain MongoDB's support for time-to-live (TTL) indexes.**
    - **Answer**: TTL indexes are special indexes that automatically delete documents from a collection after a specified period. They are useful for expiring data, such as session information or logs. Create a TTL index using the `expireAfterSeconds` option:
      ```javascript
      db.collection.createIndex({ createdAt: 1 }, { expireAfterSeconds: 3600 });
      ```

34. **What is the difference between the `find()` and `aggregate()` methods in MongoDB?**
    - **Answer**: The `find()` method retrieves documents based on query criteria, returning documents as they are stored. The `aggregate()` method processes documents through an aggregation pipeline, allowing for more complex transformations, filtering, and data manipulations.

35. **What are the different types of relationships in MongoDB, and how do you model them?**
    - **Answer**: In MongoDB, you can model relationships using:
      - **Embedded Documents**: Store related data in the same document for one-to-one or one-to-many relationships.
      - **References**: Store related data in separate documents and use references (ObjectId) for one-to-many or many-to-many relationships.

36. **How does MongoDB handle concurrency?**
    - **Answer**: MongoDB handles concurrency using a multi-granularity locking system, including:
      - **Document-Level Locking**: Locks at the document level for most operations.
      - **Collection-Level and Database-Level Locks**: Used for certain administrative operations.
      - **Optimistic Concurrency Control**: For transactions, using a mechanism to detect and resolve conflicts.

37. **Explain the `changeStream` feature in MongoDB.**
    - **Answer**: Change streams allow applications to access real-time data changes in a collection, database, or deployment. They are useful for building reactive applications. Use the `watch()` method to create a change stream:
      ```javascript
      const changeStream = db.collection.watch();
      changeStream.on('change', change => {
        console.log(change);
      });
      ```

38. **What is MongoDB Compass?**
    - **Answer**: MongoDB Compass is a graphical user interface (GUI) for MongoDB that allows users to visually explore their data, run queries, visualize and optimize query performance, manage indexes, and perform various administrative tasks.

39. **How do you perform text search in MongoDB?**
    - **Answer**: To perform text search, create a text index on the fields you want to search, and use the `$text` query operator:
      ```javascript
      db.collection.createIndex({ field: "text" });
      db.collection.find({ $text: { $search: "search term" } });
      ```

40. **What is the `$project` stage in the aggregation pipeline?**
    - **Answer**: The `$project` stage reshapes each document in the aggregation pipeline. It can add, remove, or rename fields and create computed values:
      ```javascript
      db.collection.aggregate([
        { $project: { field1: 1, newField: { $concat: ["$field2", " ", "$field3"] } } }
      ]);
      ```

41. **Explain the purpose of the `$group` stage in the aggregation pipeline.**
    - **Answer**: The `$group` stage groups documents by a specified key and can perform operations on each group, such as sum, average, count, etc. It outputs one document per group:
      ```javascript
      db.collection.aggregate([
        { $group: { _id: "$category", total: { $sum: "$amount" } } }
      ]);
      ```

42. **What are the differences between MongoDB and MySQL?**
    - **Answer**: Key differences between MongoDB and MySQL include:
      - **Data Model**: MongoDB is document-oriented, storing data in flexible JSON-like documents, whereas MySQL is a relational database using tables with fixed schemas.
      - **Schema**: MongoDB has a dynamic schema, allowing for more flexibility. MySQL uses a predefined schema.
      - **Scaling**: MongoDB supports horizontal scaling (sharding), while MySQL typically scales vertically.
      - **Query Language**: MongoDB uses a rich, dynamic query language based on JSON. MySQL uses SQL.
      - **Transactions**: Both support transactions, but MongoDB's transaction support is relatively newer.

43. **What is the `explain` method in MongoDB?**
    - **Answer**: The `explain` method provides information on how MongoDB executes a query. It helps in understanding query performance and optimizing indexes. Use it with a query to get execution statistics:
      ```javascript
      db.collection.find({ field: "value" }).explain("executionStats");
      ```

44. **How do you handle schema validation in MongoDB?**
    - **Answer**: Schema validation in MongoDB is handled using JSON Schema. You can define validation rules when creating a collection:
      ```javascript
      db.createCollection("myCollection", {
        validator: {
          $jsonSchema: {
            bsonType: "object",
            required: ["name", "age"],
            properties: {
              name: {
                bsonType: "string",
                description: "must be a string and is required"
              },
              age: {
                bsonType: "int",
                minimum: 0,
                description: "must be an integer and is required"
              }
            }
          }
        }
      });
      ```

Sure, here are more MongoDB interview questions and answers starting from number 45:

### Advanced Questions (continued)

45. **Explain the `$redact` stage in the aggregation pipeline.**
    - **Answer**: The `$redact` stage allows you to filter the content of documents at any level of the document hierarchy. It can be used to restrict the content of documents based on certain conditions. The `$redact` stage evaluates documents and returns parts of the document based on a specified expression:
      ```javascript
      db.collection.aggregate([
        {
          $redact: {
            $cond: {
              if: { $eq: ["$status", "A"] },
              then: "$$KEEP",
              else: "$$PRUNE"
            }
          }
        }
      ]);
      ```
      In this example, documents with the status "A" will be kept, while others will be pruned.

46. **What is the purpose of the `$graphLookup` stage?**
    - **Answer**: The `$graphLookup` stage performs a recursive search on a collection, allowing you to look up documents by traversing a graph structure. It is useful for querying hierarchical data, such as organizational charts or tree structures:
      ```javascript
      db.collection.aggregate([
        {
          $graphLookup: {
            from: "employees",
            startWith: "$managerId",
            connectFromField: "managerId",
            connectToField: "employeeId",
            as: "reportingHierarchy"
          }
        }
      ]);
      ```

47. **What are MongoDB's ACID properties?**
    - **Answer**: MongoDB provides ACID properties for transactions:
      - **Atomicity**: Ensures that all operations within a transaction are completed successfully. If any operation fails, the transaction is aborted.
      - **Consistency**: Ensures that the database remains in a consistent state before and after the transaction.
      - **Isolation**: Ensures that transactions are isolated from each other until they are completed.
      - **Durability**: Ensures that once a transaction is committed, the changes are permanent, even in the case of a system failure.

48. **How do you use the `$merge` stage in the aggregation pipeline?**
    - **Answer**: The `$merge` stage writes the results of the aggregation pipeline to a specified collection, either merging the documents with existing ones or inserting new documents. It is useful for creating materialized views:
      ```javascript
      db.collection.aggregate([
        { $group: { _id: "$category", total: { $sum: "$amount" } } },
        { $merge: { into: "summary", whenMatched: "merge", whenNotMatched: "insert" } }
      ]);
      ```

49. **What is the `$facet` stage in the aggregation pipeline?**
    - **Answer**: The `$facet` stage allows you to create multi-faceted aggregations by processing multiple aggregation pipelines within a single stage. Each sub-pipeline operates independently on the same set of input documents and produces a separate result set:
      ```javascript
      db.collection.aggregate([
        {
          $facet: {
            priceSummary: [{ $group: { _id: null, avgPrice: { $avg: "$price" } } }],
            categorySummary: [{ $group: { _id: "$category", count: { $sum: 1 } } }]
          }
        }
      ]);
      ```

50. **What is the `$bucket` stage in the aggregation pipeline?**
    - **Answer**: The `$bucket` stage categorizes incoming documents into a specified number of groups, or buckets, based on a given expression. It is useful for histogram-style grouping:
      ```javascript
      db.collection.aggregate([
        {
          $bucket: {
            groupBy: "$price",
            boundaries: [0, 50, 100, 200],
            default: "Other",
            output: {
              count: { $sum: 1 },
              averagePrice: { $avg: "$price" }
            }
          }
        }
      ]);
      ```

51. **Explain the `$bucketAuto` stage in the aggregation pipeline.**
    - **Answer**: The `$bucketAuto` stage automatically categorizes documents into a specified number of equal-sized buckets based on a given expression. It optimizes the bucket boundaries to distribute the documents evenly:
      ```javascript
      db.collection.aggregate([
        {
          $bucketAuto: {
            groupBy: "$price",
            buckets: 5,
            output: {
              count: { $sum: 1 },
              averagePrice: { $avg: "$price" }
            }
          }
        }
      ]);
      ```

52. **How does MongoDB ensure high availability?**
    - **Answer**: MongoDB ensures high availability through replica sets. A replica set consists of a primary node and one or more secondary nodes. The primary handles all write operations, while the secondaries replicate the data. If the primary fails, an automatic failover process elects a new primary from the secondaries, ensuring continuous availability.

53. **What is a capped collection in MongoDB, and when would you use it?**
    - **Answer**: A capped collection is a fixed-size collection that maintains insertion order and automatically overwrites the oldest documents when it reaches its size limit. Capped collections are useful for use cases like logging, where you need to maintain only the most recent data:
      ```javascript
      db.createCollection("myCappedCollection", { capped: true, size: 5242880, max: 5000 });
      ```

54. **How do you handle schema migrations in MongoDB?**
    - **Answer**: Schema migrations in MongoDB can be handled using various strategies:
      - **Using Mongoose (for Node.js)**: Mongoose provides schema definitions and migration scripts can be written to update the schema.
      - **Custom Scripts**: Write custom scripts to update documents to the new schema format.
      - **MongoDB Migration Tools**: Use tools like MongoBooster or third-party libraries designed for schema migrations.

55. **What are the benefits and drawbacks of using MongoDB?**
    - **Answer**:
      - **Benefits**:
        - Flexible schema design.
        - High performance and scalability.
        - Rich query language and powerful aggregation framework.
        - Built-in replication and sharding for high availability and scalability.
      - **Drawbacks**:
        - Potentially larger storage requirements due to denormalization.
        - Limited support for multi-document transactions (before version 4.0).
        - Learning curve for those accustomed to relational databases.

56. **How do you optimize query performance in MongoDB?**
    - **Answer**: To optimize query performance in MongoDB:
      - Use indexes appropriately to speed up query execution.
      - Avoid large document sizes and deep nesting.
      - Use projection to return only necessary fields.
      - Analyze query performance using the `explain` method.
      - Optimize schema design based on query patterns.
      - Use aggregation pipelines for complex data processing.

57. **What is the difference between `aggregate()` and `mapReduce()`?**
    - **Answer**: Both `aggregate()` and `mapReduce()` are used for data aggregation:
      - `aggregate()` uses an aggregation pipeline, which is more efficient, easier to use, and preferred for most aggregation tasks.
      - `mapReduce()` allows for custom JavaScript functions for map and reduce operations, providing more flexibility but at the cost of performance.

58. **What are the benefits of using MongoDB Atlas?**
    - **Answer**: MongoDB Atlas provides a fully managed cloud database service with benefits such as:
      - Automated backups and point-in-time recovery.
      - Global distribution and multi-cloud support.
      - Advanced security features (encryption, access controls).
      - Performance monitoring and optimization tools.
      - Auto-scaling and serverless options.

59. **Explain MongoDB's support for geospatial data.**
    - **Answer**: MongoDB supports geospatial data through geospatial indexes (`2d` and `2dsphere`) and query operators (`$near`, `$geoWithin`, `$geoIntersects`). These features allow for efficient storage, indexing, and querying of geographic data, enabling applications to perform location-based searches and calculations.

60. **What is the purpose of the `oplog` in a replica set?**
    - **Answer**: The `oplog` (operations log) is a special capped collection in a replica set that records all changes to the data. It is used by secondary nodes to replicate changes from the primary node, ensuring data consistency across the replica set.

### Expert Questions

61. **How do you handle write conflicts in MongoDB transactions?**
    - **Answer**: Write conflicts in MongoDB transactions occur when multiple transactions attempt to write to the same document simultaneously. MongoDB uses an optimistic concurrency control mechanism. If a write conflict occurs, the affected transaction is aborted and needs to be retried. Applications should implement retry logic for handling such conflicts.

62. **What is the `bsonType` keyword in MongoDB schema validation?**
    - **Answer**: The `bsonType` keyword is used in MongoDB schema validation to specify the expected BSON data type for a field. It ensures that documents conform to the defined schema:
      ```javascript
      {
        validator: {
          $jsonSchema: {
            bsonType: "object",
            required: ["name", "age"],
            properties: {
              name: { bsonType: "string" },
              age: { bsonType: "int", minimum: 0 }
            }
          }
        }
      }
      ```

Sure, here are more MongoDB interview questions and answers starting from number 63:

### Expert Questions (continued)

63. **How does MongoDB handle indexing for large collections?**
    - **Answer**: For large collections, MongoDB handles indexing using several strategies to ensure performance and efficiency:
      - **Index Building**: MongoDB builds indexes in the background by default, which allows the database to remain operational during the indexing process.
      - **Sharding**: When using sharding, MongoDB distributes the data across multiple shards, and indexes are built on each shard independently.
      - **Indexing Best Practices**: Creating indexes during low-usage periods, using compound indexes, and limiting the number of indexes to what is necessary for query performance can help manage large collections effectively.

64. **What is the purpose of the `$lookup` stage in the aggregation pipeline?**
    - **Answer**: The `$lookup` stage performs left outer joins with other collections. It allows you to combine data from different collections into a single result set:
      ```javascript
      db.orders.aggregate([
        {
          $lookup: {
            from: "customers",
            localField: "customerId",
            foreignField: "_id",
            as: "customerDetails"
          }
        }
      ]);
      ```

65. **Explain the concept of MongoDB's horizontal scaling (sharding).**
    - **Answer**: Sharding is MongoDB's method for horizontal scaling. It distributes data across multiple servers (shards) to handle larger datasets and higher throughput. A shard is a subset of the data, and each shard is a replica set for high availability. MongoDB uses a shard key to determine the distribution of data across shards.

66. **How does MongoDB handle replication lag?**
    - **Answer**: Replication lag occurs when secondary nodes fall behind the primary in applying oplog entries. MongoDB handles replication lag through:
      - **Oplog Size**: Ensuring the oplog is large enough to retain operations until secondaries can catch up.
      - **Monitoring and Alerts**: Using monitoring tools to detect and alert on replication lag.
      - **Read Preferences**: Configuring read preferences to use the primary or nearest secondary to mitigate the impact of lag on read operations.

67. **What is a partial index, and when would you use it?**
    - **Answer**: A partial index is an index built on a subset of documents in a collection based on a filter expression. It is useful for optimizing queries that only target a specific subset of documents:
      ```javascript
      db.collection.createIndex(
        { field: 1 },
        { partialFilterExpression: { status: "active" } }
      );
      ```

68. **Explain how MongoDB's GridFS works.**
    - **Answer**: GridFS is a specification for storing and retrieving large files in MongoDB. It splits files into smaller chunks and stores each chunk as a separate document in a `chunks` collection. Metadata about the file is stored in a `files` collection. This allows for efficient storage and retrieval of large files:
      ```javascript
      const bucket = new mongoose.mongo.GridFSBucket(db, {
        bucketName: 'filesBucket'
      });
      ```

69. **How do you handle backup and restore operations in a sharded cluster?**
    - **Answer**: For a sharded cluster, backup and restore operations involve:
      - **Backup**: Using the `mongodump` tool on each shard and the config servers. Alternatively, taking file system snapshots of the underlying storage for each shard.
      - **Restore**: Using the `mongorestore` tool to restore each shard and the config servers. Ensure the data is restored in a consistent state across all shards and config servers.

70. **What are hidden members in a replica set, and when would you use them?**
    - **Answer**: Hidden members are replica set members that do not participate in elections or serve read operations. They are used for specific purposes such as backups, analytics, or reporting:
      ```javascript
      rs.add({ host: "hidden_member:27017", priority: 0, hidden: true });
      ```

71. **What is the difference between `$push` and `$addToSet` operators?**
    - **Answer**: The `$push` operator appends a value to an array, while the `$addToSet` operator adds a value to an array only if it does not already exist (prevents duplicates):
      ```javascript
      db.collection.updateOne({ _id: 1 }, { $push: { values: 10 } });
      db.collection.updateOne({ _id: 1 }, { $addToSet: { values: 10 } });
      ```

72. **Explain the `collation` feature in MongoDB.**
    - **Answer**: Collation allows for specifying language-specific rules for string comparison, such as case sensitivity and accent marks. It is used for creating indexes and queries that consider these rules:
      ```javascript
      db.collection.createIndex({ name: 1 }, { collation: { locale: "en", strength: 2 } });
      db.collection.find({ name: "john" }).collation({ locale: "en", strength: 2 });
      ```

73. **How do you use the `$text` operator in MongoDB?**
    - **Answer**: The `$text` operator performs text search on fields indexed with a text index. It supports searching for words and phrases:
      ```javascript
      db.collection.createIndex({ content: "text" });
      db.collection.find({ $text: { $search: "search term" } });
      ```

74. **What is a retryable write, and how does MongoDB implement it?**
    - **Answer**: Retryable writes ensure that write operations can be retried safely without the risk of duplicate operations. MongoDB implements this by using unique operation IDs and tracking the progress of operations to prevent duplicate writes in case of failures.

75. **What are the different methods of performing data migration in MongoDB?**
    - **Answer**: Data migration in MongoDB can be performed using:
      - **Mongodump and Mongorestore**: For exporting and importing data.
      - **File System Snapshots**: For consistent, point-in-time backups and restores.
      - **Custom Scripts**: For transforming and migrating data between collections or databases.
      - **Third-Party Tools**: Tools like `mongoimport`/`mongoexport` or ETL tools designed for data migration.

76. **Explain the `$arrayElemAt` operator in MongoDB.**
    - **Answer**: The `$arrayElemAt` operator returns the element at a specified array index. It is useful for accessing specific elements within an array:
      ```javascript
      db.collection.aggregate([
        { $project: { element: { $arrayElemAt: ["$arrayField", 2] } } }
      ]);
      ```

77. **What is the purpose of the `$reduce` operator in MongoDB?**
    - **Answer**: The `$reduce` operator applies an expression to each element in an array and accumulates the results into a single value. It is useful for performing aggregation operations on array elements:
      ```javascript
      db.collection.aggregate([
        {
          $project: {
            total: {
              $reduce: {
                input: "$prices",
                initialValue: 0,
                in: { $add: ["$$value", "$$this"] }
              }
            }
          }
        }
      ]);
      ```

78. **How does MongoDB handle full-text search?**
    - **Answer**: MongoDB handles full-text search using text indexes and the `$text` query operator. Text indexes can be created on string fields, and the `$text` operator is used to search for terms and phrases within these fields. Full-text search supports stemming, stop words, and relevance scoring.

79. **Explain the concept of `geohash` in MongoDB.**
    - **Answer**: Geohash is a method of encoding geographic coordinates into a string, which allows for efficient indexing and querying of spatial data. In MongoDB, geohashes are used in geospatial indexes to enable fast location-based searches.

80. **What are some common use cases for MongoDB's `TTL` indexes?**
    - **Answer**: TTL (Time-to-Live) indexes are used for automatically expiring documents after a specified period. Common use cases include:
      - **Session Expiry**: Automatically deleting expired user sessions.
      - **Temporary Data**: Removing temporary or transient data, such as cache entries.
      - **Logging and Auditing**: Keeping logs or audit records for a limited time before automatic deletion.

81. **How do you handle multi-document transactions in MongoDB?**
    - **Answer**: Multi-document transactions in MongoDB provide ACID guarantees and allow multiple operations on multiple documents to be executed in a transaction. Transactions are initiated using sessions and the `startTransaction` method:
      ```javascript
      const session = client.startSession();
      session.startTransaction();

      try {
        db.collection1.insertOne({ _id: 1, value: "A" }, { session });
        db.collection2.insertOne({ _id: 1, value: "B" }, { session });

        session.commitTransaction();
      } catch (error) {
        session.abortTransaction();
      } finally {
        session.endSession();
      }
      ```

Sure, here are more MongoDB interview questions and answers starting from number 82:

### Expert Questions (continued)

82. **What is the `maxTimeMS` option in MongoDB queries?**
    - **Answer**: The `maxTimeMS` option specifies a time limit in milliseconds for a query to execute. If the query exceeds this time, it will be aborted to prevent long-running operations from impacting the system's performance:
      ```javascript
      db.collection.find({}).maxTimeMS(1000);
      ```

83. **Explain the `$mergeObjects` operator in MongoDB.**
    - **Answer**: The `$mergeObjects` operator combines multiple documents into a single document. It merges fields from the provided documents, with later documents' fields overwriting earlier ones in case of conflicts:
      ```javascript
      db.collection.aggregate([
        {
          $project: {
            mergedDoc: {
              $mergeObjects: ["$doc1", "$doc2"]
            }
          }
        }
      ]);
      ```

84. **What is the purpose of the `capped` option in a collection, and how do you use it?**
    - **Answer**: The `capped` option creates a fixed-size collection that maintains insertion order and automatically overwrites the oldest documents when it reaches its size limit. Capped collections are ideal for use cases such as logging where only the most recent data is needed:
      ```javascript
      db.createCollection("log", { capped: true, size: 5242880, max: 5000 });
      ```

85. **Describe the `$arrayToObject` operator and its use case.**
    - **Answer**: The `$arrayToObject` operator converts an array of key-value pairs into a single document. It is useful for transforming arrays into objects for easier manipulation and querying:
      ```javascript
      db.collection.aggregate([
        {
          $project: {
            obj: {
              $arrayToObject: "$arrayField"
            }
          }
        }
      ]);
      ```

86. **What is the `$type` operator, and how can it be used in queries?**
    - **Answer**: The `$type` operator matches documents where the value of a field is of a specified BSON type. It can be used to query documents based on the data type of their fields:
      ```javascript
      db.collection.find({ field: { $type: "string" } });
      ```

87. **Explain the difference between `$pull` and `$pullAll` operators in MongoDB.**
    - **Answer**: Both operators remove elements from an array, but they differ in how they specify the elements to remove:
      - **`$pull`**: Removes elements that match a specified condition:
        ```javascript
        db.collection.updateOne({ _id: 1 }, { $pull: { arrayField: { score: 8 } } });
        ```
      - **`$pullAll`**: Removes all instances of specified values from an array:
        ```javascript
        db.collection.updateOne({ _id: 1 }, { $pullAll: { arrayField: [5, 6, 7] } });
        ```

88. **What is the purpose of the `changeStream` feature in MongoDB?**
    - **Answer**: Change streams allow applications to listen for real-time changes to data in a collection, database, or an entire deployment. This is useful for building applications that need to react to changes, such as real-time analytics, notifications, and synchronization:
      ```javascript
      const changeStream = db.collection.watch();
      changeStream.on("change", (change) => {
        console.log("Change detected:", change);
      });
      ```

89. **How do you create a compound index, and when would you use it?**
    - **Answer**: A compound index indexes multiple fields within a collection. It is used when queries need to filter or sort by multiple fields:
      ```javascript
      db.collection.createIndex({ field1: 1, field2: -1 });
      ```

90. **What is the `$sample` stage in the aggregation pipeline, and how is it used?**
    - **Answer**: The `$sample` stage randomly selects a specified number of documents from the input documents. It is useful for operations like generating random samples or test datasets:
      ```javascript
      db.collection.aggregate([{ $sample: { size: 10 } }]);
      ```

91. **Explain how you can enforce data validation rules in MongoDB.**
    - **Answer**: Data validation in MongoDB can be enforced using JSON Schema validation. You define rules for each field, and MongoDB ensures that documents adhere to these rules before insertion or update:
      ```javascript
      db.createCollection("users", {
        validator: {
          $jsonSchema: {
            bsonType: "object",
            required: ["name", "age"],
            properties: {
              name: {
                bsonType: "string",
                description: "must be a string and is required"
              },
              age: {
                bsonType: "int",
                minimum: 0,
                description: "must be an integer greater than or equal to 0"
              }
            }
          }
        }
      });
      ```

92. **What is the purpose of the `$filter` operator in MongoDB?**
    - **Answer**: The `$filter` operator selects a subset of an array to return based on a specified condition. It is useful for filtering array elements within documents:
      ```javascript
      db.collection.aggregate([
        {
          $project: {
            filteredArray: {
              $filter: {
                input: "$arrayField",
                as: "item",
                cond: { $gt: ["$$item.score", 5] }
              }
            }
          }
        }
      ]);
      ```

93. **Describe the `$indexStats` stage in the aggregation pipeline.**
    - **Answer**: The `$indexStats` stage provides statistics about the usage of indexes for a collection. It helps in understanding how indexes are being used and identifying unused or underutilized indexes:
      ```javascript
      db.collection.aggregate([{ $indexStats: {} }]);
      ```

94. **How does MongoDB handle text search and indexing for multilingual content?**
    - **Answer**: MongoDB supports multilingual text search through text indexes with specified collation and language options. You can create text indexes that respect different language rules and query them accordingly:
      ```javascript
      db.collection.createIndex({ content: "text" }, { default_language: "english" });
      db.collection.find({ $text: { $search: "example" } });
      ```

95. **What is the `$allElementsTrue` operator, and how is it used?**
    - **Answer**: The `$allElementsTrue` operator checks if all elements of an array evaluate to true. It is used in aggregation pipelines to validate conditions on arrays:
      ```javascript
      db.collection.aggregate([
        {
          $project: {
            allTrue: { $allElementsTrue: ["$arrayField"] }
          }
        }
      ]);
      ```

96. **Explain the `balancer` in MongoDB sharding.**
    - **Answer**: The balancer in MongoDB sharding is a background process that ensures an even distribution of data across shards. It moves chunks of data between shards to balance the storage and query load. The balancer can be manually controlled using the `sh.startBalancer()` and `sh.stopBalancer()` commands.

97. **How do you use the `$range` operator in MongoDB?**
    - **Answer**: The `$range` operator generates an array containing a sequence of numbers. It is useful for creating arrays with a specific range of values:
      ```javascript
      db.collection.aggregate([
        {
          $project: {
            rangeArray: { $range: [0, 10, 2] }
          }
        }
      ]);
      ```

98. **What is the `$regexFind` operator in MongoDB?**
    - **Answer**: The `$regexFind` operator applies a regular expression (regex) to a string field and returns information about the first match found. It is used for pattern matching within strings:
      ```javascript
      db.collection.aggregate([
        {
          $project: {
            regexMatch: {
              $regexFind: {
                input: "$stringField",
                regex: /pattern/
              }
            }
          }
        }
      ]);
      ```

99. **Explain the `$indexOfArray` operator and provide an example.**
    - **Answer**: The `$indexOfArray` operator searches an array for the occurrence of a specified value and returns the array index (zero-based) of the first occurrence. If the value is not found, it returns `-1`:
      ```javascript
      db.collection.aggregate([
        {
          $project: {
            index: { $indexOfArray: ["$arrayField", "value"] }
          }
        }
      ]);
      ```

100. **What is the `$isNumber` operator in MongoDB, and how can it be used?**
    - **Answer**: The `$isNumber` operator checks if a specified expression resolves to a numeric value. It is useful for validating and filtering numeric data within documents:
      ```javascript
      db.collection.aggregate([
        {
          $project: {
            isNumeric: { $isNumber: "$field" }
          }
        }
      ]);
      ```

These questions and answers should help in preparing for advanced MongoDB interviews.