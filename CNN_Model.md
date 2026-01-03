## CNN Model Flow Diagram

```mermaid
flowchart TD
    A["Input Image (224×224×3)"] --> B["Conv2D (32 filters)"]
    B --> C["BatchNorm + ReLU"]
    C --> D["MaxPooling"]

    D --> E["Conv2D (64 filters)"]
    E --> F["BatchNorm + ReLU"]
    F --> G["MaxPooling"]

    G --> H["Conv2D (128 filters)"]
    H --> I["BatchNorm + ReLU"]
    I --> J["MaxPooling"]

    J --> K["Conv2D (256 filters)"]
    K --> L["BatchNorm + ReLU"]
    L --> M["MaxPooling"]

    M --> N["Flatten"]
    N --> O["Dense 256 + ReLU"]
    O --> P["Dropout 0.5"]
    P --> Q["Dense 128 + ReLU"]
    Q --> R["Dropout 0.3"]
    R --> S["Softmax Output (Normal / OSCC)"]
```markdown