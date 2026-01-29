# Unity_URP_Learning

Unity URP (Universal Render Pipeline) 渲染学习与实践项目，涵盖多种渲染技术的实现与优化。

## 📋 项目概述

本项目是一个综合性的 Unity URP 渲染技术学习仓库，包含以下核心技术的实现：
- **后处理效果** (Post Processing)
- **RenderFeature 管线拓展** (Custom Render Features)
- **PBR 渲染** (Physically Based Rendering)
- **NPR 渲染** (Non-Photorealistic Rendering / 卡通渲染)
- **体积渲染** (Volume Rendering / 体积云)
- **ComputeShader** (GPU 计算)
- **GPU 草渲染** (GPU Grass Rendering)
- **VFX 特效** (Visual Effects)
- **8级级联阴影** (8-level Cascaded Shadow Maps)

## 🔧 环境要求

| 配置项 | 版本 |
|--------|------|
| Unity Editor | 2022.3.17f1c1 |
| Universal Render Pipeline | 14.0.9 |
| Visual Effect Graph | 14.0.9 |
| Cinemachine | 2.9.7 |
| TextMeshPro | 3.0.6 |
| Timeline | 1.7.6 |

## 📁 项目结构

```
Unity_URP_Learning/
├── Assets/
│   ├── Products/                    # 核心功能模块
│   │   ├── ASEFunc/                 # ASE Shader 功能函数库
│   │   ├── Billboard_SG/            # ShaderGraph Billboard 实现
│   │   ├── ComputeShader/           # ComputeShader 示例
│   │   │   ├── ComputeShaderGrass/  # GPU 草渲染
│   │   │   └── ComputeShaderTest/   # ComputeShader 测试
│   │   ├── NPR/                     # NPR 卡通渲染
│   │   ├── OcclusionVision/         # 遮挡透视效果
│   │   ├── PBR/                     # PBR 渲染实现
│   │   ├── RenderFeature/           # 自定义 RenderFeature
│   │   ├── ScreenDisPlay/           # 屏幕显示效果
│   │   ├── Shadow8CSM/              # 8级级联阴影 (待优化)
│   │   ├── TextMeshProGlitch/       # TextMeshPro 故障艺术效果
│   │   ├── VolumeCloud/             # 体积云渲染 (开发中)
│   │   ├── WaterEat/                # 水面效果
│   │   └── 视差/                    # 视差效果 (Parallax)
│   ├── Arts/                        # 艺术资源 (天空盒等)
│   ├── Scenes/                      # 示例场景
│   └── Settings/                    # URP 渲染设置
├── Packages/                        # URP 核心包 (本地修改版)
└── ProjectSettings/                 # Unity 项目设置
```

## 🎨 功能模块详解

### 1. PBR 渲染 (Physically Based Rendering)
- 自定义 PBR Shader 实现
- 完整的 BRDF 光照模型
- 支持金属度、粗糙度等标准 PBR 属性
- 场景: `Assets/Products/PBR/PBR.unity`

### 2. NPR 卡通渲染 (Non-Photorealistic Rendering)
- SRP 合批优化
- NPR 融合部分 PBR 效果
- 屏幕空间刘海在脸上的投影
- 屏幕空间背景板投影
- 2D SDF 滚动背景实现
- TextMeshPro 故障艺术修改
- 场景: `Assets/Products/NPR/NPR.unity`

### 3. GPU 草渲染 (ComputeShader Grass)
- 基于 ComputeShader 的大规模草渲染
- GPU 视锥剔除 (Frustum Culling)
- 多个版本迭代优化
- 场景: `Assets/Products/ComputeShader/ComputeShaderGrass/`

### 4. 自定义 RenderFeature
- **CustomRTRenderPassFeature** - 自定义渲染纹理
- **GrabColorRenderPassFeature** - 抓取颜色缓冲
- **SSDepthMaskPassFeature** - 屏幕空间深度遮罩
- **SSHSRenderPassFeature** - 屏幕空间效果
- **SSOutLinePassFeature** - 屏幕空间描边
- 场景: `Assets/Products/RenderFeature/RenderFerture.unity`

### 5. 8级级联阴影 (Shadow 8 CSM)
- 扩展 Unity 默认的 4 级 CSM 到 8 级
- 提供更精细的阴影距离控制
- ⚠️ 状态: 待优化
- 场景: `Assets/Products/Shadow8CSM(ToBeOptimized)/Shadow8CSM.unity`

### 6. 体积云渲染 (Volume Cloud)
- 基于光线步进的体积云渲染
- Perlin-Worley 噪声生成
- SDF 网格支持
- 🚧 状态: 开发中
- 场景: `Assets/Products/VolumeCloud(Working)/VolumeCloud.unity`

### 7. 遮挡透视效果 (Occlusion Vision)
- 被遮挡物体的透视显示方案
- 包含设计文档说明
- 场景: `Assets/Products/OcclusionVision/OcclusionVision.unity`

### 8. 其他效果
- **ScreenDisPlay** - 屏幕显示动画效果
- **TextMeshProGlitch** - 文字故障艺术效果
- **WaterEat** - 水面交互效果
- **视差效果** - Fate/Grand Order、游戏王风格卡片视差效果
- **Billboard** - ShaderGraph Billboard 实现

## 🚀 使用说明

1. 使用 Unity 2022.3.17f1c1 或更高版本打开项目
2. 确保 URP 包已正确加载
3. 在 `Assets/Products/` 下选择对应模块的场景文件运行

## ⚠️ 注意事项

- 本项目包含对 URP 核心包的本地修改（位于 `Packages/` 目录）
- 8级级联阴影功能仍在优化中
- 体积云功能仍在开发中
- 部分功能可能需要特定的硬件支持

## 📚 学习资源

本项目涵盖的技术可以参考以下学习方向：
- Unity URP 官方文档
- HLSL Shader 编程
- ComputeShader 并行计算
- 实时渲染算法与优化

## 📄 License

本项目仅供学习交流使用。
