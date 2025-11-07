# Kustomize 清单仓库

本目录示例用于单独管理 Kubernetes 部署清单，推荐作为独立 Git 仓库维护。

## 结构

```
kustomize-manifests/
├── base
│   ├── deployment.yaml
│   ├── kustomization.yaml
│   └── service.yaml
└── overlays
    └── dev
        └── kustomization.yaml
```

- `base/`：通用资源定义。
- `overlays/dev/`：开发环境覆盖，主要用于覆盖镜像标签。

将该目录初始化为独立仓库后，可以在 GitHub Actions 中响应应用仓库的 `repository_dispatch` 事件，自动更新 `overlays/dev/kustomization.yaml` 的镜像标签并创建 PR。

# kustomize-manifests-demo
