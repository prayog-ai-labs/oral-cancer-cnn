## VGG16 Model Flow Diagram

```mermaid
flowchart TD
    A["Input Image (224×224×3)"] --> B["VGG16 Convolution Block 1<br/>(Conv + ReLU ×2)"]
    B --> C["MaxPooling"]

    C --> D["VGG16 Convolution Block 2<br/>(Conv + ReLU ×2)"]
    D --> E["MaxPooling"]

    E --> F["VGG16 Convolution Block 3<br/>(Conv + ReLU ×3)"]
    F --> G["MaxPooling"]

    G --> H["VGG16 Convolution Block 4<br/>(Conv + ReLU ×3)"]
    H --> I["MaxPooling"]

    I --> J["Flatten"]
    J --> K["Dense 256 + ReLU"]
    K --> L["Dropout 0.5"]
    L --> M["Dense 128 + ReLU"]
    M --> N["Dropout 0.3"]
    N --> O["Softmax Output (Normal / OSCC)"]