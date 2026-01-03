## InceptionResNetV2 Model Flow Diagram

```mermaid
flowchart TD
    A["Input Image (224×224×3)"] --> B["Stem Convolution Layers"]

    B --> C["Inception-ResNet-A Blocks<br/>(Multi-scale + Residual)"]
    C --> D["Reduction-A Block"]

    D --> E["Inception-ResNet-B Blocks"]
    E --> F["Reduction-B Block"]

    F --> G["Inception-ResNet-C Blocks"]

    G --> H["Global Average Pooling"]
    H --> I["Dense 256 + ReLU"]
    I --> J["Dropout 0.5"]
    J --> K["Dense 64 + ReLU"]
    K --> L["Dropout 0.3"]
    L --> M["Softmax Output (Normal / OSCC)"]