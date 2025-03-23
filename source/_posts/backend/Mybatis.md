---
title: Mybatis
icon: pen-to-square
date: 2024-08-03
category:
  - 后端
tag:
  - 持久层框架
---

# MyBatis

MyBatis 是一个流行的持久层框架，用于简化 Java 应用程序与数据库之间的交互。它通过提供映射 SQL 语句到 Java 对象的功能，简化了数据访问的操作。以下是 MyBatis 的一些基础和重要知识点：

## 1. 什么是 MyBatis？

MyBatis 是一个开源的持久层框架，允许 Java 对象与数据库之间进行映射。与传统的 JDBC 相比，MyBatis 提供了更加灵活和易于管理的方式来执行 SQL 语句和处理结果集。

## 2. 核心特性

### 2.1 SQL 映射

- **映射 XML**：MyBatis 使用 XML 文件来定义 SQL 语句，并将这些 SQL 语句映射到 Java 方法。XML 文件中包含 `<mapper>` 元素，其中定义了 SQL 语句和映射规则。
- **注解方式**：除了 XML 配置，MyBatis 也支持使用注解在 Java 接口中定义 SQL 语句，简化了配置过程。

### 2.2 动态 SQL

- **动态 SQL 生成**：MyBatis 支持根据条件动态生成 SQL 语句。这可以通过 XML 配置中的 `<if>`、`<choose>`、`<foreach>` 等标签实现，根据不同条件生成不同的 SQL 语句。

### 2.3 映射关系

- **一对一**：支持一对一的对象映射。例如，用户和用户详情之间的关系可以通过一对一映射来实现。
- **一对多**：支持一对多的对象映射。例如，一个部门下有多个员工，可以通过一对多映射来实现。
- **多对多**：支持多对多的对象映射。例如，学生和课程之间的多对多关系可以通过多对多映射来实现。

### 2.4 缓存机制

- **一级缓存**：默认启用的会话级缓存，生命周期与 SqlSession 相同。它缓存同一 SqlSession 内的查询结果，减少数据库访问次数。
- **二级缓存**：可配置的全局缓存，跨多个 SqlSession 缓存查询结果。二级缓存需要在配置文件中启用，并为每个 Mapper 文件配置。

## 3. 主要组件

### 3.1 SqlSessionFactory

- **作用**：创建 SqlSession 的工厂，负责配置和管理数据库连接。通常通过读取配置文件（如 `mybatis-config.xml`）来初始化 SqlSessionFactory。

### 3.2 SqlSession

- **作用**：执行 SQL 语句的主要接口，支持增、删、改、查操作。SqlSession 提供了对数据库操作的基本支持，并支持事务管理和缓存。

### 3.3 Mapper

- **Mapper 接口**：定义数据访问方法，通过接口与 XML 文件或注解进行映射。Mapper 接口方法通常对应 SQL 语句，简化了数据访问操作的定义。

### 3.4 Configuration

- **Configuration 类**：用于配置 MyBatis 的各种设置，如全局设置、数据源配置、事务管理器等。Configuration 类是 MyBatis 的核心配置类。

## 4. 配置文件

### 4.1 MyBatis 配置文件

- **`mybatis-config.xml`**：主配置文件，包含 MyBatis 的全局配置和插件设置。配置项包括：
  - 数据源配置
  - 事务管理
  - 缓存设置
  - 全局设置（如驼峰命名规则）

### 4.2 Mapper 配置文件

- **`Mapper.xml`**：定义 SQL 语句和映射规则。每个 Mapper 文件对应一个 Mapper 接口，包含 SQL 语句和映射配置。例如：
  - `select` 查询
  - `insert`、`update`、`delete` 操作
  - 动态 SQL 生成

## 5. 使用 MyBatis

### 5.1 配置数据源和 MyBatis

- **数据源配置**：在 `mybatis-config.xml` 文件中配置数据源。MyBatis 支持多种数据源，如 HikariCP 和 Druid。

### 5.2 创建 Mapper 接口和 XML 文件

- **Mapper 接口**：定义数据访问方法。例如，定义一个获取用户信息的方法。
- **Mapper XML 文件**：提供 SQL 语句和映射规则。例如，定义获取用户信息的 SQL 查询语句。

### 5.3 执行操作

- **获取 SqlSessionFactory**：通过配置文件创建 SqlSessionFactory 实例。
- **获取 SqlSession**：通过 SqlSessionFactory 创建 SqlSession 实例。
- **执行 SQL 操作**：使用 SqlSession 执行 CRUD 操作，如查询、插入、更新和删除。

## 6. 总结

MyBatis 提供了一个灵活和强大的机制来简化 Java 对象和数据库之间的映射。通过使用 XML 配置或注解，MyBatis 允许开发者自定义 SQL 语句，并有效管理数据访问操作。了解 MyBatis 的核心组件、特性和配置方法，将帮助你更高效地处理数据库操作。
