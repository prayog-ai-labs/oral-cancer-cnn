flowchart TD
    A[Input Image<br/>(224×224×3)] --> B[Conv2D<br/>32 Filters]
    B --> C[BatchNorm + ReLU]
    C --> D[MaxPooling]

    D --> E[Conv2D<br/>64 Filters]
    E --> F[BatchNorm + ReLU]
    F --> G[MaxPooling]

    G --> H[Conv2D<br/>128 Filters]
    H --> I[BatchNorm + ReLU]
    I --> J[MaxPooling]

    J --> K[Conv2D<br/>256 Filters]
    K --> L[BatchNorm + ReLU]
    L --> M[MaxPooling]

    M --> N[Flatten]
    N --> O[Dense 256<br/>ReLU]
    O --> P[Dropout 0.5]
    P --> Q[Dense 128<br/>ReLU]
    Q --> R[Dropout 0.3]
    R --> S[Softmax Output<br/>(Normal / OSCC)]
