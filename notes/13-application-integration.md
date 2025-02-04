# Application Integration

# Simple Queue Service (SQS)

Decouples application components using message queues for asynchronous communication

- Key way to decouple components
- Producer sends to the queue; consumer polls from the queue
- If order of processing matters, use a FIFO queue
- If duplicates cannot be tolerated, use a FIFO queue
- Visibility timeout is the length of time that a message is "invincible" when it's being processed; may need to lengthen this time if messages are being processed more than once
- Auto scaling is possible by setting up a CloudWatch alarm (using a custom metric to calculate length of queue) that scales EC2 instances in an auto scaling group
- Long polling will wait 20 seconds to poll an empty queue (saving costs and extraneous polls)

- Types
    - Standard: Unlimited throughput, at-least-once delivery, possible duplication
    - FIFO: Message order is preserved, exactly-once processing, limited throughput (300 TPS by default)
- Dead-Letter Queues (DLQ): Capture messages that fail processing multiple times
- Message Retention: 1 minute to 14 days (default 4 days)
- Visibility Timeout: Time a message is hidden after being received (default 30s, max 12 hours)
- Polling
	- Long: Reduces empty responses by waiting up to 20s for a message
	- Short: Immediate response, may return empty results
- Security: IAM policies for access control, SSE (Server-Side Encryption) for encryption
  
# Simple Notification Service (SNS)

Publish/subscribe messaging for event-driven architectures

- Send notifications by email, text, HTTP, Lambda
- "Pub-Sub" model where a publisher publishes to a SNS topic, and subscribers subscribe to receive notifications

- Publishers: send messages to SNS topics
- Subscribers: SQS, Lambda, HTTP/HTTPS, email, SMS receive messages
- Message Fan-Out: Distribute a single message to multiple subscribers
- Delivery Retry Policies: Exponential backoff for failed HTTP/S notifications
- FIFO Topics: Guarantee order and exactly-once message delivery (used with FIFO SQS)
- Security: Encryption at rest (SSE), VPC endpoint support, IAM policies

# EventBridge

Event bus service for integrating AWS services and third-party applications

- Some features were formally called CloudWatch Events
- Used to build event-driven architectures (also a "pub-sub" model)
    - Subscribers set rules about what to receive
    - Schemas defined up front
    - Publishers can be third parties (e.g., Shopify, Zendesk)
    - Events can be scheduled

- Event Buses
    - Default: Receieves AWS service events automatically
    - Custom: For custom applications or SaaS integrations
- Event Routing: Uses rules to send events to multiple targets (Lambda, Step Functions, SQS, etc.)
- Event Schema Registry: Helps store and manage event structures
- Event Replay: Replays past events for debugging or reprocessing
- Differecnces from SNS
    - SNS uses a push model (real-time notifications)
    - EventBridge uses rules-based event filtering and routing

# Step Functions

Orchestrate workflows with stateful execution

- Provides a visual designer to orchestrate Lambda functions and other serverless services

- Workflow Types
    - Standard Workflows: Durable, supports retries and long-running processes
    - Express Workflows: Fast, cost-effective, for high-volume short-duration tasks
- State Machine Execution: Uses JSON-based Amazon States Language (ASL)
- Integration with AWS Services: Lambda, SQS, SNS, EventBridge, DynamoDB, etc
- Parallel & Conditional Execution: Enables branching and decision-making within workflows
- Error Handling: Automatic retries, catch/finally blocks

