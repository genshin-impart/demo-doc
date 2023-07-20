# 欢迎使用模型可视化平台

## 项目说明

1. 算法部分：基于 [PaddlePaddle](https://www.paddlepaddle.org.cn/) 深度学习框架和龙源风电官方提供的数据，设计一种利用当日 05:00 之前的数据，预测次日 00:00 至 23:45 实际功率的方法。
2. 软件部分：基于 Web 的风电功率预测系统，其中包括数据可视化、实时更新、滚动预测和响应式设计四大基础功能。在模型训练和预测过程中，可以实时查看训练进度和相关日志输出，把握模型的状态。

## 用户指南

请查阅[用户手册](./user/guide.md)

## 开发指南

请查阅[开发手册](./dev/summarize.md)

### 技术选型

- 前端

主要技术栈为 React 框架……

```

```

- 后端

主要技术栈为 [Flask](https://flask.palletsprojects.com/en/2.3.x/) 框架。

Flask 是一款轻量级的 Python Web 框架，专注于构建简单、灵活且易于扩展的 Web 应用程序。它基于 Werkzeug 工具库和 Jinja2 模板引擎，被广泛应用于快速开发 Web 应用和 API。

Flask 具有简单的核心，它提供了基本的路由、请求和响应处理功能。开发者可以根据需要选择并添加第三方扩展来增加额外的功能，这使得 Flask 具备高度可定制性。其灵活性使得开发者能够更加自由地组织代码和项目结构。除此之外，Flask 还具有内置集成单元测试、支持安全 cookie（客户端会话）等多种特性。

Flask 支持 RESTful 风格的 API 开发，可用于构建 REST API。其文档完善且社区活跃，拥有大量的资源和教程，使得学习和使用 Flask 变得相对容易。总体而言，Flask 是一个适用于小型项目或初学者的优秀选择，同时也能满足高级开发人员的需求，能够满足本项目的需求。

后端整体结构图如下所示。

```

```

- 模型

主要技术栈为 PaddlePaddle 深度学习框架和 Scikit-learn 机器学习工具库。

PaddlePaddle （飞桨）深度学习框架是百度推出的开源项目，专注于提供高效、易用的深度学习解决方案。它支持动态图和静态图的混合编程模式，既满足灵活性要求，又能实现高性能计算。飞桨的独特之处在于其对于分布式训练和高性能计算的优化，特别适合在大规模数据和模型上进行训练，应用于工业级别的深度学习任务，如图像识别、自然语言处理等。PaddlePaddle 还提供了丰富的预训练模型和模型库，方便开发者快速构建复杂的深度学习模型。本项目采用了基于飞桨深度学习框架的开源时序建模算法库 PaddleTS，实现时序数据处理、分析、建模、预测全流程。

Scikit-learn 是一个被广泛使用的 Python 机器学习库，为机器学习算法提供了丰富的工具和函数，简化了算法的应用和调整。Scikit-learn 支持多种机器学习算法，包括分类、回归、聚类、降维等，还提供了数据预处理、特征选择和模型评估等功能。该库被广泛应用于数据分析和机器学习领域，适用于从初学者到专业人士的各种应用场景。Scikit-learn 的设计注重易用性和可扩展性，提供了简洁一致的 API 接口，让用户能够迅速上手，并能根据需要轻松扩展功能。这使得 Scikit-learn 成为了 Python 生态系统中不可或缺的机器学习工具之一。

模型整体结构图如下所示。

```

```

### 项目结构

```

```