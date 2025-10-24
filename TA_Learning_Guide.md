# PiccoloFoME引擎 - 技术美术学习指南

## 📖 项目概述

PiccoloFoME是一个基于Vulkan的现代游戏引擎项目，适合技术美术（TA）学习现代游戏引擎架构和渲染技术。本指南专门为美术向的技术美术设计，重点关注与TA工作最相关的引擎模块。

## 🎯 学习目标

- 掌握现代游戏引擎的核心架构
- 深入理解渲染管线和技术
- 学习特效系统和粒子技术
- 掌握动画系统和工具开发
- 提升程序能力和技术理解

## 📚 学习路径

### 🚀 第一阶段：基础认知（1-2周）

#### 1.1 引擎架构理解

**重点文件：**
```
📁 核心文件：
├── engine/source/editor/source/main.cpp          # 程序入口
├── engine/source/runtime/engine.h                # 引擎核心
├── engine/source/runtime/function/global/         # 全局上下文
└── engine/source/runtime/function/framework/      # 框架层
```

**学习目标：**
- 理解引擎的整体架构
- 掌握组件系统（ECS）的基本概念
- 熟悉编辑器的基本操作

**实践任务：**
- 运行引擎，熟悉编辑器界面
- 理解引擎启动流程
- 学习组件系统的基本概念

#### 1.2 资源系统入门

**重点文件：**
```
📁 资源系统：
├── engine/source/runtime/resource/res_type/data/material.h
├── engine/source/runtime/function/framework/component/mesh/
└── engine/source/runtime/function/render/render_resource.h
```

**学习目标：**
- 理解资源加载流程
- 掌握材质系统基础
- 熟悉编辑器中的资源面板

**实践任务：**
- 修改材质属性（颜色、纹理路径）
- 理解资源序列化机制
- 学习资源管理策略

### 🎨 第二阶段：渲染管线深入（2-3周）

#### 2.1 着色器系统

**重点文件：**
```
📁 着色器系统：
├── engine/shader/glsl/                    # 着色器源码
│   ├── mesh.vert/frag                    # 基础网格着色器
│   ├── particlebillboard.vert/frag       # 粒子着色器
│   ├── skybox.vert/frag                  # 天空盒着色器
│   └── deferred_lighting.vert/frag       # 延迟光照着色器
├── engine/source/runtime/function/render/passes/
└── engine/source/runtime/function/render/interface/
```

**学习重点：**
- **材质系统**：理解PBR材质管线
- **着色器编写**：从简单到复杂的着色器修改
- **渲染Pass**：理解前向渲染和延迟渲染

**实践项目：**
1. 修改现有着色器，添加自定义效果
2. 创建简单的材质着色器
3. 实现基础的纹理混合效果

#### 2.2 光照系统

**重点文件：**
```
📁 光照系统：
├── engine/source/runtime/function/render/passes/directional_light_pass.h
├── engine/source/runtime/function/render/passes/point_light_pass.h
├── engine/source/runtime/function/render/light.h
└── engine/shader/glsl/mesh_directional_light_shadow.vert/frag
```

**学习目标：**
- 理解方向光和点光源的实现
- 掌握阴影贴图技术
- 学习光照计算在着色器中的应用

**实践项目：**
1. 实现自定义光照模型
2. 优化阴影质量
3. 创建动态光照效果

### ✨ 第三阶段：特效系统（3-4周）

#### 3.1 粒子系统深入

**重点文件：**
```
📁 粒子系统：
├── engine/source/runtime/function/particle/particle_manager.h
├── engine/source/runtime/function/render/passes/particle_pass.h
├── engine/source/runtime/function/framework/component/particle/
└── engine/shader/glsl/particle_*.comp    # 粒子计算着色器
```

**学习重点：**
- **GPU粒子系统**：理解现代粒子系统的实现
- **计算着色器**：学习GPU计算在粒子中的应用
- **粒子生命周期**：掌握粒子的发射、更新、渲染流程

**实践项目：**
1. 创建自定义粒子效果（火焰、烟雾、爆炸）
2. 实现粒子与场景的交互（碰撞检测）
3. 优化粒子系统的性能

#### 3.2 后处理效果

**重点文件：**
```
📁 后处理系统：
├── engine/source/runtime/function/render/passes/fxaa_pass.h
├── engine/source/runtime/function/render/passes/tone_mapping_pass.h
├── engine/source/runtime/function/render/passes/color_grading_pass.h
└── engine/shader/glsl/fxaa.frag
```

**学习目标：**
- 理解后处理管线
- 实现自定义后处理效果
- 掌握屏幕空间技术

**实践项目：**
1. 实现自定义后处理效果
2. 优化抗锯齿算法
3. 创建色彩分级工具

### 🎭 第四阶段：动画系统（2-3周）

#### 4.1 骨骼动画

**重点文件：**
```
📁 动画系统：
├── engine/source/runtime/function/animation/
├── engine/source/runtime/function/framework/component/animation/
└── engine/source/runtime/resource/res_type/data/skeleton_data.h
```

**学习重点：**
- 骨骼动画的数据结构
- 动画混合和状态机
- 动画与渲染的集成

**实践项目：**
1. 实现简单的动画混合
2. 创建动画状态机
3. 优化动画性能

### 🛠️ 第五阶段：高级技术（4-6周）

#### 5.1 自定义渲染效果
- 实现自定义渲染Pass
- 集成第三方渲染技术
- 性能优化和调试

#### 5.2 工具开发
- 开发自定义编辑器工具
- 实现资源导入管道
- 创建自动化工具

## 🎯 TA专用技能树

### 核心技能分布

```
渲染管线 (40%)
├── 着色器编程
├── 材质系统
├── 光照模型
└── 后处理效果

特效系统 (30%)
├── 粒子系统
├── 计算着色器
├── 物理模拟
└── 性能优化

工具开发 (20%)
├── 编辑器扩展
├── 资源管道
├── 自动化工具
└── 调试工具

动画系统 (10%)
├── 骨骼动画
├── 动画混合
└── 状态机
```

## 📋 实践项目建议

### 初级项目
1. **材质编辑器**：创建可视化材质编辑工具
2. **简单特效**：实现基础的粒子效果
3. **着色器实验**：修改现有着色器，观察效果变化

### 中级项目
1. **特效库**：建立个人特效资源库
2. **后处理工具**：开发自定义后处理效果
3. **动画工具**：创建动画编辑工具

### 高级项目
1. **渲染优化**：实现渲染性能优化方案
2. **工具链开发**：建立完整的资源处理管道
3. **引擎扩展**：为引擎添加新功能

## 📚 学习资源

### 必读文档
1. **Vulkan教程**：学习现代图形API
2. **PBR材质理论**：理解物理渲染
3. **GPU编程指南**：掌握计算着色器
4. **游戏引擎架构**：理解引擎设计原理

### 推荐书籍
- 《Real-Time Rendering》
- 《GPU Gems》系列
- 《Game Engine Architecture》
- 《Physically Based Rendering》

### 在线资源
- [Vulkan Tutorial](https://vulkan-tutorial.com/)
- [LearnOpenGL](https://learnopengl.com/)
- [GPU Programming Guide](https://developer.nvidia.com/gpu-programming-guide)

## 💡 学习建议

### 学习方法
1. **循序渐进**：不要急于求成，每个阶段都要扎实掌握
2. **实践为主**：多动手修改代码，观察效果变化
3. **记录学习**：建立学习笔记，记录重要概念和技巧
4. **社区交流**：参与引擎社区讨论，获取帮助和灵感

### 调试技巧
1. **使用调试器**：学会使用Visual Studio调试器
2. **日志系统**：利用引擎的日志系统进行调试
3. **性能分析**：使用GPU性能分析工具
4. **代码审查**：定期回顾和优化代码

### 常见问题
1. **编译错误**：仔细阅读错误信息，检查依赖关系
2. **渲染问题**：检查着色器语法和资源路径
3. **性能问题**：使用性能分析工具定位瓶颈
4. **内存问题**：注意资源管理和内存泄漏

## 🎯 学习里程碑

### 第1个月
- [ ] 理解引擎基本架构
- [ ] 能够修改简单材质
- [ ] 掌握基础着色器语法

### 第2个月
- [ ] 实现自定义着色器效果
- [ ] 理解渲染管线流程
- [ ] 掌握光照系统原理

### 第3个月
- [ ] 创建复杂粒子效果
- [ ] 实现后处理效果
- [ ] 优化渲染性能

### 第4个月
- [ ] 掌握动画系统
- [ ] 开发自定义工具
- [ ] 完成综合项目

## 📞 获取帮助

### 社区资源
- GitHub Issues：报告bug和获取帮助
- 技术论坛：参与技术讨论
- 文档贡献：帮助完善文档

### 学习交流
- 建立学习小组
- 定期技术分享
- 参与开源贡献

---

**记住：学习游戏引擎是一个长期过程，保持耐心和持续学习的心态是最重要的！**

*最后更新：2024年*
