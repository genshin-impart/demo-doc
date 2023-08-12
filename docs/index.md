# 欢迎使用模型可视化平台

## 项目说明

1. 算法部分：基于 [PaddlePaddle](https://www.paddlepaddle.org.cn/) 深度学习框架和风力发电场官方提供的数据，设计一种利用当日 05:00 之前的数据，预测次日 00:00 至 23:45 实际功率的方法。
2. 软件部分：基于 Web 的风电功率预测系统，其中包括数据可视化、实时更新、滚动预测和响应式设计四大基础功能。在模型训练和预测过程中，可以实时查看训练进度和相关日志输出，把握模型的状态。

## 用户指南

请查阅[用户手册](./user/guide.md)

## 开发指南

请查阅[开发手册](./dev/summarize.md)

### 技术选型

#### 前端

主要技术栈为 [React](https://react.dev) 框架。

React 是由 Facebook 开发的用于构建用户界面的 JavaScript 库。它采用组件化的方式构建 UI，使开发者可以将复杂的用户界面拆分成独立的可复用组件。React 使用虚拟 DOM（Virtual DOM）来优化性能，将组件更改和 DOM 更新最小化，从而提高应用程序的性能和响应速度。

前端项目采用工程化管理，并尽可能使用现代化的工具链。

- 包管理器：使用 pnpm 替代 npm 进行依赖管理
- 开发工具：使用 Vite 以提供更快的 HMR
- 构建工具：使用 Vite 内建的 ESBuild + SWC 进行 TypeScript 编译和生成目标代码
- 项目管理：使用 lint-staged 和 commit-lint 规范代码提交
- 项目样式：在 Joy UI 和 emotion 引擎的基础上构建了自定义组件

#### 后端

主要技术栈为 [Flask](https://flask.palletsprojects.com/en/2.3.x/) 框架。

Flask 是一款轻量级的 Python Web 框架，专注于构建简单、灵活且易于扩展的 Web 应用程序。它基于 Werkzeug 工具库和 Jinja2 模板引擎，被广泛应用于快速开发 Web 应用和 API。

Flask 具有简单的核心，它提供了基本的路由、请求和响应处理功能。开发者可以根据需要选择并添加第三方扩展来增加额外的功能，这使得 Flask 具备高度可定制性。其灵活性使得开发者能够更加自由地组织代码和项目结构。除此之外，Flask 还具有内置集成单元测试、支持安全 cookie（客户端会话）等多种特性。

Flask 支持 RESTful 风格的 API 开发，可用于构建 REST API。其文档完善且社区活跃，拥有大量的资源和教程，使得学习和使用 Flask 变得相对容易。总体而言，Flask 是一个适用于小型项目或初学者的优秀选择，同时也能满足高级开发人员的需求，能够满足本项目的需求。

??? 后端子项目结构

    ```
    model-be
    ├── backend
    │   ├── api
    │   │   ├── __init__.py
    │   │   ├── model.py
    │   │   ├── mythread.py
    │   │   ├── process.py
    │   │   ├── sio.py
    │   │   └── train.py
    │   ├── app.py
    │   ├── blueprints
    │   │   ├── __init__.py
    │   │   ├── model.py
    │   │   └── user.py
    │   ├── cache
    │   ├── csv
    │   ├── extensions.py
    │   ├── fakes.py
    │   ├── logs
    │   │   └── wpf_system.log
    │   ├── models.py
    │   ├── settings.py
    │   ├── sub_entry.py
    │   └── utils
    │       ├── auth.py
    │       ├── core.py
    │       ├── file.py
    │       └── model.py
    ├── Makefile
    ├── README.md
    ├── tests
    │   ├── base.py
    │   ├── __init__.py
    │   ├── test_admin.py
    │   ├── test_auth.py
    │   ├── test_basic.py
    │   └── test_cli.py
    └── TODO.md
    ```

#### 模型

主要技术栈为 PaddlePaddle 深度学习框架和 Scikit-learn 机器学习工具库。

PaddlePaddle （飞桨）深度学习框架是百度推出的开源项目，专注于提供高效、易用的深度学习解决方案。它支持动态图和静态图的混合编程模式，既满足灵活性要求，又能实现高性能计算。飞桨的独特之处在于其对于分布式训练和高性能计算的优化，特别适合在大规模数据和模型上进行训练，应用于工业级别的深度学习任务，如图像识别、自然语言处理等。PaddlePaddle 还提供了丰富的预训练模型和模型库，方便开发者快速构建复杂的深度学习模型。本项目采用了基于飞桨深度学习框架的开源时序建模算法库 PaddleTS，实现时序数据处理、分析、建模、预测全流程。

Scikit-learn 是一个被广泛使用的 Python 机器学习库，为机器学习算法提供了丰富的工具和函数，简化了算法的应用和调整。Scikit-learn 支持多种机器学习算法，包括分类、回归、聚类、降维等，还提供了数据预处理、特征选择和模型评估等功能。该库被广泛应用于数据分析和机器学习领域，适用于从初学者到专业人士的各种应用场景。Scikit-learn 的设计注重易用性和可扩展性，提供了简洁一致的 API 接口，让用户能够迅速上手，并能根据需要轻松扩展功能。这使得 Scikit-learn 成为了 Python 生态系统中不可或缺的机器学习工具之一。

??? 模型子项目结构

    ```
    model-core
    ├── LICENSE
    ├── Makefile
    ├── modules
    │   ├── ensemble_model.py
    │   └── single_model.py
    ├── paddle_train.py
    ├── predict.py
    ├── README.md
    └── utils
        ├── feature_engineer.py
        ├── my_configs.py
        └── preprocess.py
    ```

### 项目结构

项目使用前后端分离的 C/S 模式。前端采用单页面应用（SPA）和客户端渲染（CSR）的方式；后端基于 Flask 构建，符合 RESTful API 规范。

将前端、后端、模型三个子项目组合起来即为本项目的最终架构。
