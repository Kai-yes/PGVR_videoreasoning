# Phys-R1: Physically Grounded Video Reasoning

<p align="center">
    <a href="https://your-project-page.github.io/">项目主页</a> | 
    <a href="https://arxiv.org/abs/xxxx.xxxx">论文原文</a> | 
    <a href="https://huggingface.co/models">模型权重</a> | 
    <a href="#dataset">数据集</a>
</p>

---

## 🌟 核心亮点

**Phys-R1** 是一个旨在提升大型多模态模型（LMMs）物理推理能力的解耦框架。

- **解耦的 Grounder-Verifier 架构**: Policy 模型 (Grounder) 生成结构化的物理参数假设，物理模拟器 (Verifier) 提供精确反馈。
- **Gaussian-Kernel GRPO**: 针对连续物理参数（质量、摩擦力、初速度）优化的强化学习算法，有效解决奖励稀疏问题。
- **潜空间动力学对齐 (Latent Dynamics Alignment)**: 确保生成的推理链与真实物理规律严格一致。
- **结构化输出**: 模型不仅给出答案，还会输出包含物理参数的 `<json>` 代码块。

---

## 📽️ 效果展示 (Demos)

| 物理碰撞预测 (Collision Prediction) | 轨迹追踪与推理 (Trajectory Reasoning) |
| :---: | :---: |
| ![Demo 1](https://via.placeholder.com/400x225?text=Video+Demo+1) | ![Demo 2](https://via.placeholder.com/400x225?text=Video+Demo+2) |
| *模型推断出绿色球体的质量并预测碰撞时间* | *模型根据摩擦力推断物体的停止位置* |

---

## 🛠️ 框架架构 (Methodology)



Phys-R1 通过将物理参数显式化，使模型从“视觉直觉”转向“原理解析”。

---

## 🚀 快速开始

### 1. 环境准备
```bash
# 克隆仓库
git clone [https://github.com/your-username/Phys-R1.git](https://github.com/your-username/Phys-R1.git)
cd Phys-R1

# 安装依赖
pip install -r requirements.txt
# 建议安装 PyBullet 或 MuJoCo 作为模拟器后端
