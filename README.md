# Examples

## Flowcharts

My go-to diagram that helps to visually represent the steps of a process or workflow. They make complex processes easier to understand at a glance.

### Example 1: AI Project Workflow

Simplified overview of the end-to-end process for an AI project, from initial concept to deployment and maintenance.

```mermaid
graph TD
    A[Problem Definition] --> B[Data Collection<br>& Preparation]
    B --> C[Model Development<br>& Training]
    C --> D{Model Evaluation}
    D -- Meets KPIs? --> E[Deployment to Production]
    D -- No --> C
    E --> F[Monitoring & Maintenance]
    F --> A

    style A fill:#5472b8,stroke:#222,stroke-width:2px
    style B fill:#5472b8,stroke:#222,stroke-width:2px
    style C fill:#5472b8,stroke:#222,stroke-width:2px
    style D fill:#d7993c,stroke:#222,stroke-width:2px
    style E fill:#38a169,stroke:#222,stroke-width:2px
    style F fill:#38a169,stroke:#222,stroke-width:2px
```

### Example 2: How Our AI Answers Questions with RAG

Shows how an LLM can answer questions using specific company documents to make its responses more accurate and relevant.

```mermaid
flowchart TD
  subgraph "Knowledge Indexing"
    direction LR
    A["Internal Documents<br>(PDFs, Confluence, etc.)"] --> B["Chunking & Embedding"]
    B --> C[("Vector Database")]
  end

  subgraph "Live Querying"
    direction TB
    D{{User Asks a Question}} --> E["Find Relevant Info"]
    C --> E
    E --> F["Augment Prompt"]
    D --> F
    F --> G["Generate Answer"]
    G -- LLM --> H["Answer"]
  end

  style C fill:#5472b8,stroke:#222,stroke-width:2px
  style H fill:#38a169,stroke:#222,stroke-width:2px
```

### Example 3: AI Agent for Customer Support

Workflow of an AI agent that can use "tools" to perform actions, like looking up order information or processing a return.

```mermaid
graph TD
    A["Customer asks: <br>&quot;Where is my order?&quot;"] --> B{AI Agent};
    B -- "I need to check<br>the order status." --> C{Tool Selection};
    C -- Chooses Tool --> D['lookup_order' Tool];
    D -- "Order #12345" --> E[(Database/API)];
    E -- "Status: Shipped" --> D;
    D -- Returns info to Agent --> B;
    B --> F["Agent responds:<br>&quot;Your order #12345<br>has been shipped.&quot;"];

    style B fill:#5472b8,stroke:#222,stroke-width:2px
    style F fill:#38a169,stroke:#222,stroke-width:2px
```

## Sequence Diagrams

Useful for explaining the technical architecture at a high level, showing the different components and how they interact.

### Example: LLM Inference via API

Shows how a user's request flows through the system to get a prediction from an LLM. 

```mermaid
sequenceDiagram
    participant User
    participant API_Gateway
    participant Inference_Service
    participant LLM
    User->>API_Gateway: Send Request
    API_Gateway->>Inference_Service: Forward Request
    Inference_Service->>LLM: Get Prediction
    LLM-->>Inference_Service: Prediction Response
    Inference_Service-->>API_Gateway: Return Prediction
    API_Gateway-->>User: Result
```

## Mindmaps

Helps to visually organize ideas and show relationships between them.

### Example: Potential AI Applications

This mindmap shows potential applications for AI across various departments.

```mermaid
mindmap
  AI Use Cases
      Sales
        Lead Scoring
        Sales Forecasting
      Marketing
        Personalization
        Campaign Optimization
      Customer Service
        Chatbots
        Sentiment Analysis
      Operations
        Demand Forecasting
        Inventory Management
      R&D
        Drug Discovery
        Predictive Maintenance
```
