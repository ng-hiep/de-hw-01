# Extraction: Online vs Offline

In the context of Data Engineering, Extraction is the process of *extracting* data from an external system, usually denoted as a *source*, to the data system managed by us. There are mainly two types of extraction: online and offline, serving the same goals with different methods and properties.

## Data Extraction

Data extraction can be either the act of crawling data from Internet websites indexed by common search engines, or official APIs available from applications or systems running remotely, or even getting the data from an on-prem filesystem. Such action of accessing data from a source is called a *connection*.

### Online Data Extraction

Online extraction involves directly connecting to the source to retrieve the needed data in real-time or near-real-time manner. This method typically requires a continuous connection to that source instead of different connections at discontinuous times, which differentiates it from offline extraction explored in the next section.

Some of the most prominent characteristics of online data extraction are:

- **Direct Connection**: Establishes a direct connection to the source with maintained continuity, allowing for immediate data retrieval.
- **Real-Time Data**: As the connection continues, data is immediately extracted as it becomes available on the source, ensuring that the most recent data is always accessible at the managed data system.
- **Immediate Availability**: Data is immediately available to other processes in the managed system after extraction, such as loading or transformation.
- **Continuous Requirement**: Often used in scenarios where data needs to be continuously updated, such as in monitoring systems or real-time analytics.

### Offline Data Extraction

In contrast with online data extraction, offline extraction involves retrieving data from the source without maintaining a continuous connection. Data is typically extracted in batches with periodic connections.

Below are some characteristics of offline data extraction:

- **Discontinuous Connection**: The extraction process does not maintain a continuous connection to the source.
- **Batch Processing**: Data is extracted in batches rather than in real-time, each of which contains information that has not been extracted from the time after the last run.
- **Scheduled Extraction**: Data extraction is scheduled at specific intervals rather than immediate availability, some of the most used intervals are daily, weekly, or monthly.

## Comparisons

### Similarities

- **Purpose**: Both methods aim to retrieve data from a source for further processing and analysis.
- **ETL/ELT Process**: Both are integral parts of the Extract, Transform, Load (ETL) or ELT process, which is essential for data integration and warehousing.
- **Data Transformation**: Both methods often involve subsequent data transformation or loading steps to prepare data before it may be usable for other users of the system.

### Differences

| Aspect                  | Online Extraction                                                                 | Offline Extraction                                                                 |
|-------------------------|-----------------------------------------------------------------------------------|-----------------------------------------------------------------------------------|
| **Connection Type**     | Requires a continuous connection to the source                                    | Does not require a continuous connection; uses periodic connections               |
| **Data Timeliness**     | Provides real-time data                                                           | Involves batch processing with potential delays                                   |
| **Resource Usage**      | More resource-intensive, requiring more computational power and bandwidth         | More resource-efficient, less demanding on computational resources                |
| **Complexity**          | More complex to implement and maintain due to the need for constant connectivity  | Easier to implement and maintain                                                  |
| **Use Cases**           | Suitable for real-time analytics and monitoring                                   | Suitable for periodic reporting and analysis                                      |
| **Data Availability**   | Data is immediately available for processing and analysis                         | Data is available after scheduled extraction intervals                            |
| **Error Handling**      | Requires robust error handling mechanisms due to continuous data flow             | Errors can be managed between extraction intervals                                |
| **Security**            | Higher risk of security issues due to continuously exposed connection                       | Lower risk as data is handled in batches with only periodic connections                                         |
| **Cost**                | Generally more expensive due to continuous resource usage                         | More cost-effective due to reduced resource requirements                          |

## Examples

### Online Data Extraction Example

**Example**: An e-commerce organization allows its users to place orders via smartphones, tablets, computers, websites, and social media. To determine user shopping behavior for the next marketing campaign, a data analyst extracts customer records like names, email addresses, purchase history, and social media behavior in real-time using a data extraction tool. This ensures that the most recent data is always available for analysis.

### Offline Data Extraction Example

**Example**: A retail company wants to generate weekly sales reports. They use an offline extraction process to extract sales data from their transactional databases in batches every Sunday night. The data is then stored in a data lake and processed on Monday morning to generate the reports. This method ensures that the extraction process does not interfere with daily operations and provides a consistent schedule for data analysis.
