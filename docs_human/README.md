# docs_human

人工重写的文档暂存目录，用于逐步替换 AI 生成的 `docs/`。

- 本目录**不参与** MkDocs 站点构建（`mkdocs.yml` 只读 `docs/`），推送也不会触发 Pages 部署。
- 文件名请与 `docs/` 保持一致（`index.md`、`architecture.md`、`modules/*.md`），这样切换时无需改动 `mkdocs.yml` 的 nav。
- 未审校的草稿不要放进 `docs/`——不在 nav 里的页面也会被构建成可公开访问的 URL。
- 全部完成后：用本目录内容覆盖 `docs/`，核对 nav，删除本目录。
