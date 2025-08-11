# Examples

## 1. AI Project Lifecycle

This diagram provides a simplified overview of the end-to-end process for an AI project, from initial concept to deployment and maintenance.

```mermaid
graph TD
    A[Problem Definition] --> B[Data Collection<br>& Preparation]
    B --> C[Model Development<br>& Training]
    C --> D{Model Evaluation}
    D -- Meets KPIs? --> E[Deployment to Production]
    D -- No --> C
    E --> F[Monitoring & Maintenance]
    F --> A
```

## 2. How Our AI Answers Questions with RAG

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
```

## 3. Predicting Customer Churn

This flowchart shows the process for a model that predicts which customers are at risk of leaving (churning). It highlights the data sources and the final business outcome.

```mermaid
graph TD
    subgraph "Data Sources"
        A[Customer Demographics]
        B[Purchase History]
        C[Support Tickets]
        D[Website Activity]
    end

    subgraph "AI Pipeline"
        E["Feature Engineering<br>(Create customer profile)"]
        F["Machine Learning Model<br>(Predicts churn probability)"]
    end

    subgraph "Business Action"
        G{High Churn Risk Customers}
        H["Retention Campaign<br>(e.g., Discounts, Outreach)"]
    end

    A & B & C & D --> E;
    E --> F;
    F --> G;
    G --> H;
```

## 4. AI-Powered Sales Forecasting

This diagram illustrates how different data streams are combined and processed by an AI model to produce a more accurate sales forecast.

```mermaid
graph LR
    subgraph "Input Data"
        A[Historical Sales Data]
        B[Marketing Campaign Data]
        C[Economic Indicators]
        D[CRM Data]
    end

    subgraph "Forecasting Engine"
        E(Data Aggregation <br>& Cleaning) --> F(AI Forecasting Model);
    end

    subgraph "Output"
        G[Quarterly Sales Forecast]
        H[Demand Planning Insights]
    end

    A & B & C & D --> E;
    F --> G;
    F --> H;
```

## 5. AI Agent for Customer Support

This shows the workflow of an AI agent that can do more than just chat. It can use "tools" to perform actions, like looking up order information or processing a return.

```mermaid
graph TD
    A["Customer asks: <br>&quot;Where is my order?&quot;"] --> B{AI Agent};
    B -- "I need to check<br>the order status." --> C{Tool Selection};
    C -- Chooses Tool --> D['lookup_order' Tool];
    D -- "Order #12345" --> E[(Database/API)];
    E -- "Status: Shipped" --> D;
    D -- Returns info to Agent --> B;
    B --> F["Agent responds:<br>&quot;Your order #12345<br>has been shipped.&quot;"];
```
