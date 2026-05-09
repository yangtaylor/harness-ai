---
name: cpf-template
description: >
  cpf 框架（SpringBoot定制）后端编码规范模板 Skill。
  当进行后端开发或后端代码评审时使用此 Skill。
---

# cpf 框架后端规范

## Controller 模板

```java
package com.example.controller;

import org.springframework.web.bind.annotation.*;
import org.springframework.beans.factory.annotation.Autowired;

@RestController
@RequestMapping("/api/path")
public class ExampleController {

    @Autowired
    private ExampleService exampleService;

    @GetMapping("/list")
    public Result list(ExampleQuery query) {
        return Result.success(exampleService.list(query));
    }

    @GetMapping("/{id}")
    public Result detail(@PathVariable Long id) {
        return Result.success(exampleService.detail(id));
    }

    @PostMapping
    public Result save(@RequestBody ExampleDTO dto) {
        return Result.success(exampleService.save(dto));
    }

    @PutMapping("/{id}")
    public Result update(@PathVariable Long id, @RequestBody ExampleDTO dto) {
        return Result.success(exampleService.update(id, dto));
    }

    @DeleteMapping("/{id}")
    public Result delete(@PathVariable Long id) {
        return Result.success(exampleService.delete(id));
    }
}
```

## Service 模板

```java
package com.example.service;

import org.springframework.stereotype.Service;
import org.springframework.transaction.annotation.Transactional;
import org.springframework.beans.factory.annotation.Autowired;

@Service
public class ExampleService {

    @Autowired
    private ExampleMapper exampleMapper;

    @Transactional(rollbackFor = Exception.class)
    public void save(ExampleDTO dto) {
        // 业务逻辑
    }

    @Transactional(rollbackFor = Exception.class)
    public void update(Long id, ExampleDTO dto) {
        // 业务逻辑
    }
}
```

## Entity 模板

```java
package com.example.entity;

import com.baomidou.mybatisplus.annotation.*;
import java.time.LocalDateTime;

@TableName("example_table")
public class ExampleEntity {

    @TableId(type = IdType.AUTO)
    private Long id;

    private String name;

    @TableField(fill = FieldFill.INSERT)
    private LocalDateTime createTime;

    @TableField(fill = FieldFill.INSERT_UPDATE)
    private LocalDateTime updateTime;

    @TableLogic
    @TableField(fill = FieldFill.INSERT)
    private Integer isDeleted;

    // getters and setters
}
```

## Mapper 模板

```java
package com.example.mapper;

import com.baomidou.mybatisplus.core.mapper.BaseMapper;
import org.apache.ibatis.annotations.Mapper;

@Mapper
public interface ExampleMapper extends BaseMapper<ExampleEntity> {
    // 自定义 SQL
}
```

## 统一响应体

```java
package com.example.common;

public class Result<T> {
    private Integer code;
    private String message;
    private T data;

    public static <T> Result<T> success(T data) {
        Result<T> result = new Result<>();
        result.setCode(200);
        result.setMessage("success");
        result.setData(data);
        return result;
    }

    public static <T> Result<T> error(String message) {
        Result<T> result = new Result<>();
        result.setCode(500);
        result.setMessage(message);
        return result;
    }

    // getters and setters
}
```

## 编码规范检查清单

- [ ] 类名使用 PascalCase
- [ ] 方法名使用 camelCase
- [ ] 常量使用 UPPER_SNAKE_CASE
- [ ] 分层遵循 Controller → Service → Mapper → Entity
- [ ] 使用 @ControllerAdvice 统一异常处理
- [ ] @Transactional 仅在 Service 层
- [ ] 密码使用 SM3 + 随机盐值存储
- [ ] 敏感字段使用 SM4 加密存储
- [ ] API 使用 SM2 数字签名
- [ ] 单元测试覆盖率 ≥80%
