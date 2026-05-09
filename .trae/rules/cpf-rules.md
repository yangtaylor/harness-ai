# 后端编码&业务开发规范 (cpf框架)

## 命名规范
- 类名: PascalCase
- 方法名: camelCase
- 常量: UPPER_SNAKE_CASE

## 分层规范
- Controller → Service → Mapper → Entity
- 使用 `@ControllerAdvice` 统一异常处理
- `@Transactional` 仅在 Service 层

## 安全规范
- 密码存储: SM3 + 随机盐值
- 敏感字段: SM4 加密存储
- API 签名: SM2 数字签名
