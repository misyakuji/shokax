---
title: Angular
icon: pen-to-square
date: 2024-08-03
category:
  - 前端
tag:
  - 框架
---

# Angular 框架知识点笔记

## 概述

Angular 是一个开源的前端框架，由 Google 维护，主要用于构建单页应用（SPA）。Angular 提供了一种结构化的方式来开发动态的 Web 应用，利用 TypeScript 作为主要编程语言，结合组件和依赖注入等概念，提供强大的工具集来简化开发过程。

## 核心概念

### 1. 模块（Modules）

- **定义**  
  模块是 Angular 应用的基本构建块。每个模块封装了一组相关的功能和组件。通过模块，开发者可以将应用分割成更小的、可重用的部分。

- **根模块**  
  每个 Angular 应用至少有一个根模块，通常是 `AppModule`。它是应用的启动点，定义了应用的根组件和引导程序。

- **特性模块**  
  特性模块用于组织和管理特定的功能区域，比如用户模块、产品模块等。

### 2. 组件（Components）

- **定义**  
  组件是 Angular 应用的基本 UI 单元，负责定义视图和处理逻辑。每个组件由一个模板（HTML）、一个样式表（CSS）和一个 TypeScript 类组成。

- **创建组件**  
  使用 Angular CLI 命令 `ng generate component <组件名>` 来生成新的组件。

- **装饰器**  
  `@Component` 装饰器用于定义组件的元数据，包括选择器、模板和样式。

### 3. 模板（Templates）

- **定义**  
  模板是 Angular 组件的视图部分，使用 HTML 和 Angular 特有的模板语法来定义界面布局。

- **数据绑定**
  - **插值表达式**：`{{ expression }}`  
    在模板中显示数据的值。
  - **属性绑定**：`[property]="expression"`  
    绑定组件属性到 DOM 元素的属性。
  - **事件绑定**：`(event)="handler($event)"`  
    绑定 DOM 事件到组件方法。
  - **双向绑定**：`[(ngModel)]="property"`  
    同步组件属性和输入元素的值。

### 4. 服务与依赖注入（Services & Dependency Injection）

- **服务**  
  服务是用于组织和共享代码的单例类，通常用于处理业务逻辑和数据访问。通过注入服务，组件可以访问和使用这些功能。

- **依赖注入**  
  Angular 的依赖注入系统允许将服务或其他依赖项注入到组件或其他服务中。使用 `@Injectable` 装饰器定义服务，并在模块中进行提供。

### 5. 路由（Routing）

- **定义**  
  路由用于在应用中导航不同的视图或组件。通过配置路由，Angular 可以根据 URL 显示不同的组件视图。

- **配置**  
  使用 `RouterModule.forRoot(routes)` 在根模块中配置路由，其中 `routes` 是路由配置数组，定义 URL 路径和组件的映射关系。

- **路由守卫**  
  路由守卫用于控制导航流程，例如认证和授权，确保用户访问受限页面前满足特定条件。

### 6. 表单（Forms）

- **模板驱动表单**  
  简单的表单，使用 Angular 的模板语法进行双向数据绑定。适合简单的表单处理。

- **响应式表单**  
  更复杂的表单，使用 `FormControl` 和 `FormGroup` 创建和管理表单模型。提供更好的可控性和灵活性。

### 7. 生命周期钩子（Lifecycle Hooks）

- **定义**  
  生命周期钩子是 Angular 提供的一组方法，用于在组件或指令的不同生命周期阶段执行特定操作。

- **常用钩子**
  - `ngOnInit()`：初始化组件或指令。
  - `ngOnChanges(changes: SimpleChanges)`：检测输入属性的变化。
  - `ngOnDestroy()`：清理工作，销毁组件或指令。

### 8. 指令（Directives）

- **定义**  
  指令用于操作 DOM 元素，改变其行为或外观。分为结构型指令和属性型指令。

- **结构型指令**  
  改变 DOM 结构，例如 `*ngIf` 和 `*ngFor`。

- **属性型指令**  
  修改元素的外观或行为，例如 `ngClass` 和 `ngStyle`。

### 9. 管道（Pipes）

- **定义**  
  管道用于格式化数据。通过管道，可以在模板中转换数据，例如格式化日期或货币。

- **常用管道**
  - `DatePipe`：格式化日期。
  - `CurrencyPipe`：格式化货币。
  - `DecimalPipe`：格式化数字。

### 10. HTTP 客户端（HttpClient）

- **定义**  
  `HttpClient` 是 Angular 提供的用于发送 HTTP 请求和处理响应的服务。

- **使用**  
  注入 `HttpClient` 服务，并使用 `get()`, `post()`, `put()`, `delete()` 等方法发起请求。

- **拦截器**  
  使用 HTTP 拦截器处理请求和响应，例如添加认证令牌或处理错误。

## 常用 Angular CLI 命令

- **创建新 Angular 应用**  
  `ng new <应用名>`  
  创建一个新的 Angular 项目。

- **生成组件**  
  `ng generate component <组件名>`  
  生成新的组件。

- **生成服务**  
  `ng generate service <服务名>`  
  生成新的服务。

- **启动开发服务器**  
  `ng serve`  
  启动本地开发服务器，并在浏览器中预览应用。

- **构建生产版本**  
  `ng build --prod`  
  构建优化过的生产版本，准备部署。

## 参考资料

- [Angular 官方文档](https://angular.io/docs)
- [Angular GitHub 仓库](https://github.com/angular/angular)
- [Angular CLI 官方文档](https://angular.io/cli)
