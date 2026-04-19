# dify AI Agent 协作指南
# 适用：所有AI Agent，优先级低于宪法

## 1. 开发环境
- 语言：Go >= 1.25.0
- Web框架：Gin (github.com/gin-gin/gin)
- ORM：GORM (gorm.io/gorm)
- 本地运行：go run ./cmd/server/main.go
- 依赖安装：go get <package_path>

## 2. 测试与质量
- 全量测试：make test / go test -v ./...
- 单包测试：go test -v ./internal/handlers
- 覆盖率：make coverage
- 代码检查：make lint (golangci-lint)

## 3. Git & PR 流程
- Commit：严格遵循Conventional Commits
- 分支：feature/<功能名>
- PR标题：[PROJ-123] type(scope): 描述
- 提审前：必须通过测试+lint

## 4. 架构与代码规范
- 项目结构：遵循Go官方标准布局，核心逻辑在internal/
- 错误处理：强制fmt.Errorf("上下文: %w", err)
- 日志：强制使用log/slog结构化日志
- 接口：消费者定义，小接口优先

## 5. AI 协作规则
- 新功能：先读代码→提计划→确认后编码
- 测试：优先表格驱动测试
- 并发代码：必须标注安全措施
- 复杂代码：必须附带核心逻辑解释