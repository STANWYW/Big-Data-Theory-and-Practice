# Parquet 实践练习项目

专为 Parquet 文件格式学习设计的实践项目，通过渐进式练习帮助掌握列式存储的核心特性和最佳实践。

## 1. 项目特性

- **渐进式学习**: 从基础操作到高级特性的完整学习路径
- **性能对比**: 直观的性能测试和可视化分析
- **实用工具**: 完整的数据生成、分析和测试工具集
- **实际应用**: 贴近真实场景的练习案例

## 2. 环境要求

- Python 3.8+
- 至少 2GB 可用内存
- 500MB 可用磁盘空间

---

## 3. 快速开始

### 3.1 环境准备

```bash
# 创建虚拟环境
python3 -m venv venv

# 激活虚拟环境
source venv/bin/activate  # Linux/macOS
# 或 venv\Scripts\activate  # Windows

# 安装依赖
pip install -r requirements.txt
```

### 3.2 验证安装

```bash
python -c "import pandas, pyarrow; print('安装成功！')"
```

### 3.3 运行练习

#### 3.3.1 交互式模式（推荐）

```bash
python main.py --interactive
```

#### 3.3.2 命令行模式

```bash
# 查看帮助
python main.py --help

# 运行基础练习
python main.py --exercise basic --records 10000

# 运行压缩算法练习
python main.py --exercise compression --records 50000

# 运行查询优化练习
python main.py --exercise query --records 100000

# 运行分区存储练习
python main.py --exercise partition --records 100000

# 运行高级特性练习
python main.py --exercise advanced --records 1000

# 运行所有练习
python main.py --exercise all --records 5000
```

---

## 4. 练习内容

### 4.1 基础练习

- Parquet 文件读写操作
- 与 CSV 格式性能对比
- 文件大小和压缩效果分析
- 数据完整性验证

### 4.2 压缩算法练习

- 多种压缩算法对比 (snappy, gzip, lz4, brotli, zstd)
- 压缩比和性能权衡分析
- 可视化压缩效果

### 4.3 查询优化练习

- 投影下推 (Projection Pushdown)
- 谓词下推 (Predicate Pushdown)
- 组合优化策略
- 复杂查询性能测试

### 4.4 分区练习

- 分区表的创建和管理
- 分区裁剪 (Partition Pruning) 测试
- 多种查询场景性能对比

### 4.5 高级特性练习

- 嵌套数据结构处理
- 元数据操作和分析
- Schema 演进测试

---

## 5. 项目结构

```bash
parquet-practice-project/
├── src/parquet_practice/          # 核心代码模块
│   ├── basic_exercise.py         # 基础练习
│   ├── compression_exercise.py   # 压缩算法练习
│   ├── query_optimization_exercise.py  # 查询优化练习
│   ├── partitioning_exercise.py  # 分区练习
│   └── advanced_exercise.py      # 高级特性练习
├── examples/                     # 示例脚本
├── tests/                       # 测试文件
├── output/                      # 输出目录
├── main.py                      # 主程序入口
└── requirements.txt             # 依赖文件
```

---

## 6. 输出文件

练习结果保存在 `output/` 目录：

- `basic_exercise_results.json` - 基础练习结果
- `compression_results.json` - 压缩算法比较结果
- `query_optimization_results.json` - 查询优化结果
- `partitioning_results.json` - 分区存储结果
- `advanced_results.json` - 高级特性结果

---

## 7. 性能基准

基于 10,000 条记录的测试结果：

| 指标 | Parquet | CSV | 提升 |
|------|---------|-----|------|
| 读取时间 | 0.05s | 0.15s | 3.0x |
| 写入时间 | 0.08s | 0.12s | 1.5x |
| 文件大小 | 2.1MB | 5.8MB | 64% 压缩 |
| 内存使用 | 45MB | 78MB | 42% 节省 |

---

## 8. 故障排除

### 8.1 依赖安装问题

如果遇到 "externally-managed-environment" 错误，请使用虚拟环境：

```bash
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

### 8.2 权限问题

确保对项目目录有读写权限，特别是 `output/` 目录。

---

## 9. 开发指南

### 9.1 代码质量检查

```bash
make lint      # 代码检查
make test      # 运行测试
make format    # 代码格式化
```

### 9.2 添加新练习

1. 在 `src/parquet_practice/` 目录下创建新的练习模块
2. 继承基础类并实现必要的方法
3. 在 `main.py` 中添加新的练习选项
4. 编写相应的测试用例

---

**开始你的 Parquet 学习之旅！** 🚀
