## ResNet50 Model Flow Diagram

```mermaid
flowchart TD
    A["Input Image (224×224×3)"] --> B["Initial Conv + MaxPooling"]

    B --> C["Residual Block Group 1<br/>(Conv Blocks + Skip Connections)"]
    C --> D["Residual Block Group 2<br/>(Conv Blocks + Skip Connections)"]
    D --> E["Residual Block Group 3<br/>(Conv Blocks + Skip Connections)"]
    E --> F["Residual Block Group 4<br/>(Conv Blocks + Skip Connections)"]

    F --> G["Global Average Pooling"]
    G --> H["Dense 256 + ReLU"]
    H --> I["Dropout 0.5"]
    I --> J["Dense 64 + ReLU"]
    J --> K["Dropout 0.3"]
    K --> L["Softmax Output (Normal / OSCC)"]