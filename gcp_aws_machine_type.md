## Google GCE 实例类型

(请访问 [https://cloud.google.com/compute/docs/machine-resource/](https://cloud.google.com/compute/docs/machine-resource/) 查看完整且最新的信息。  这里仅提供一个概要。)

Google Compute Engine (GCE) 提供多种虚拟机 (VM) 实例类型，旨在满足不同的工作负载需求。  GCE 实例类型通常根据其用途和提供的资源进行分类。常见的类别包括：

*   **通用型:** 在计算、内存和网络之间提供平衡的资源组合。 适合各种工作负载。
    *   例如: `e2-medium`, `n1-standard-1`, `n2-standard-2`
*   **计算优化型:** 专注于提供高性能计算资源。 适合计算密集型工作负载。
    *   例如: `c2-standard-4`, `c3-standard-8`
*   **内存优化型:**  针对内存密集型应用程序进行了优化。 适合大型数据库和内存缓存。
    *   例如: `m1-megamem-96`, `m2-ultramem-208`
*   **加速器优化型:**  配备 GPU 或 TPU，加速机器学习和图形密集型任务。
    *   例如: `a2-highgpu-1g`, `t4g-small`
*   **存储优化型:** 专注于提供高性能本地存储。 适合需要高速数据访问的工作负载。
    *   通常需要配合本地SSD盘使用

每个类别下都有不同的实例类型，每种类型都有不同的 vCPU 数量、内存容量、磁盘选项和网络性能。  用户可以根据其应用程序的资源需求选择最合适的实例类型。
AWS 和 GCP 都有预定义的机器类型 (实例类型)。GCP 的特色在于，它还提供了自定义机器类型，允许用户更灵活地配置 vCPU 和内存，而 AWS 在自定义机器类型方面的灵活性相对较低。

## Amazon EC2 实例类型

(请访问 [https://aws.amazon.com/cn/ec2/instance-types/](https://aws.amazon.com/cn/ec2/instance-types/) 查看完整且最新的信息。 这里仅提供一个概要。)

Amazon Elastic Compute Cloud (EC2) 提供各种实例类型，旨在满足不同的应用程序需求。 实例类型提供不同的 CPU、内存、存储和网络容量组合，让您灵活地选择适合您工作负载的资源。  常见的 EC2 实例类型类别包括：

*   **通用型:**
    *   `M` 系列 (如 `m5.xlarge`, `m6g.large`, `m7a.xlarge`): 平衡的计算、内存和联网资源。
    *   `T` 系列 (如 `t3.micro`, `t4g.small`): 提供基准性能并可突增以应对峰值工作负载。 具有 CPU 积分机制。
*   **计算优化型:**
    *   `C` 系列 (如 `c5.xlarge`, `c6g.large`, `c7g.xlarge`): 针对计算密集型应用程序进行了优化。
*   **内存优化型:**
    *   `R` 系列 (如 `r5.xlarge`, `r6g.large`, `r7g.xlarge`): 针对内存密集型应用程序进行了优化，如大型数据库和内存缓存。
    *   `X` 系列 (如 `x2gd.xlarge`): 专为内存优化型工作负载设计，具有高内存与 vCPU 比率。
    *   `High Memory` (如 `u-32xl1`): 用于在 SAP HANA 等大型内存数据库中运行关键任务工作负载。
*   **加速型计算:**
    *   `P` 系列 (如 `p4d.24xlarge`, `p5.48xlarge`): 配备 GPU，用于机器学习、深度学习和高性能计算。
    *   `G` 系列 (如 `g4dn.xlarge`, `g5.xlarge`): 配备 GPU，用于图形密集型应用程序，如游戏和可视化。
    *   `F` 系列 (如 `f1.2xlarge`): 配备 FPGA，用于硬件加速。
*   **存储优化型:**
    *   `I` 系列 (如 `i3.xlarge`, `i4i.xlarge`, `i8g.xlarge`): 针对需要高速本地存储访问的工作负载进行了优化，例如 NoSQL 数据库和数据仓库。
    *   `D` 系列 (如 `d2.xlarge`): 提供高磁盘吞吐量，适用于大数据和数据仓库。
    *   `H` 系列 (如 `h1.xlarge`): 提供高磁盘存储容量，适用于 Hadoop 和其他数据密集型应用程序。

### EC2 实例类型命名约定

(请访问 [https://docs.aws.amazon.com/zh_cn/ec2/latest/instancetypes/instance-type-names.html](https://docs.aws.amazon.com/zh_cn/ec2/latest/instancetypes/instance-type-names.html) 查看完整且最新的信息。)

EC2 实例类型名称遵循以下格式：

**`Instance family.Instance.size`**

**示例实例类型： `c7gn.2xlarge`**

组成说明:

*   **c** (实例系列): 计算优化型实例
*   **7** (代系):  第七代实例
*   **g** (选项): 使用 AWS Graviton 处理器
*   **n** (选项):  网络优化
*   **2xlarge** (大小):  实例的大小是 2xlarge

**各部分详细解释:**

*   **实例系列:**  表示实例的用途和目标工作负载特征。
    *   `M`:  通用型
    *   `C`:  计算优化型
    *   `R`:  内存优化型
    *   `P`:  GPU 加速型
    *   `I`:  存储优化型

*   **代系:**  表示实例系列的代数，通常更高代数提供更好的性能和功能。`g` 后缀通常表示使用 AWS Graviton 处理器。

*   **大小:**  表示实例的相对大小和容量，通常与 vCPU 和内存相关。
    *   常见的大小包括: `nano`, `micro`, `small`, `medium`, `large`, `xlarge`, `2xlarge`, `4xlarge`, `8xlarge`, `12xlarge`, `16xlarge`, `24xlarge`, `32xlarge`, `metal`。
    *   `metal` 实例提供对底层硬件的直接访问。

*   **其他后缀 (选项):** 指示其他功能或特性。
    *   `d`:  本地 NVMe SSD 存储 (例如, `i3d.xlarge`)
    *   `n`:  增强的网络性能 (例如, `g4dn.xlarge`)
    *   `z`:  高频率 CPU (例如, `c5zn.xlarge`)

**示例实例解读：**

*   **`m5.xlarge`**:  M 系列（通用型），第五代，xlarge 大小。
*   **`c6g.large`**: C 系列（计算优化型），第六代，使用 Graviton 处理器，large 大小。
*   **`r7g.8xlarge`**: R 系列（内存优化型），第七代，使用 Graviton 处理器，8xlarge 大小。

了解命名约定有助于快速识别实例的特征和适用性。 请务必查阅 AWS 文档以获取特定实例类型的完整信息。
