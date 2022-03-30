# S3 and Lambda

## Content Delivery Network (CDN)

CDN is a geographically distributed group of servers that work together to provide fast delivery of Internet content. CDNs work through servers nearest to the website visitor respond to the request

## AWS Lambda

What is AWS Lambda? AWS Lambda is a serverless computing service provided by Amazon Web Services (AWS). Users of AWS Lambda create functions, self-contained applications written in one of the supported languages and runtimes, and upload them to AWS Lambda, which executes those functions in an efficient and flexible manner.

The Lambda functions can perform any kind of computing task, from serving web pages and processing streams of data to calling APIs and integrating with other AWS services.

The concept of “serverless” computing refers to not needing to maintain your own servers to run these functions. AWS Lambda is a fully managed service that takes care of all the infrastructure for you. And so “serverless” doesn’t mean that there are no servers involved: it just means that the servers, the operating systems, the network layer and the rest of the infrastructure have already been taken care of, so that you can focus on writing application code.

How does AWS Lambda work? Each Lambda function runs in its own container. When a function is created, Lambda packages it into a new container and then executes that container on a multi-tenant cluster of machines managed by AWS. Before the functions start running, each function’s container is allocated its necessary RAM and CPU capacity. Once the functions finish running, the RAM allocated at the beginning is multiplied by the amount of time the function spent running. The customers then get charged based on the allocated memory and the amount of run time the function took to complete.

The entire infrastructure layer of AWS Lambda is managed by AWS. Customers don’t get much visibility into how the system operates, but they also don’t need to worry about updating the underlying machines, avoiding network contention, and so on—AWS takes care of this itself.

And since the service is fully managed, using AWS Lambda can save you time on operational tasks. When there is no infrastructure to maintain, you can spend more time working on the application code—even though this also means you give up the flexibility of operating your own infrastructure.

One of the distinctive architectural properties of AWS Lambda is that many instances of the same function, or of different functions from the same AWS account, can be executed concurrently. Moreover, the concurrency can vary according to the time of day or the day of the week, and such variation makes no difference to Lambda—you only get charged for the compute your functions use. This makes AWS Lambda a good fit for deploying highly scalable cloud computing solutions.

## AWS S3

Amazon S3: Object storage built to retrieve any amount of data from anywhere.

### How AWS S3 works?

Amazon S3 is an object storage service with industry-leading scalability, data availability, security, and performance. Customers of all sizes and sectors can store and protect nearly any amount of data for use cases including data lakes, cloud-native apps, and mobile apps. You can optimize expenses, organize data, and establish fine-tuned access restrictions to suit specific business, organizational, and compliance requirements with cost-effective storage classes and easy-to-use management tools.

## Resources

[AWS Lambda](https://aws.amazon.com/lambda)
