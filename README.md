<div align="center">
  <h1>trix helm charts</h1>
  <p><strong>Helm charts for deploying Trix to Kubernetes</strong></p>

  <p>
    <a href="https://github.com/trixsec-dev/helmcharts/releases"><img src="https://img.shields.io/github/v/release/trixsec-dev/helmcharts?include_prereleases" alt="Release"></a>
    <a href="LICENSE"><img src="https://img.shields.io/github/license/trixsec-dev/helmcharts" alt="License"></a>
  </p>
</div>

---

## Available Charts

| Chart | Description |
|-------|-------------|
| [trix](./trix) | Trix Agent - Kubernetes security monitoring with vulnerability tracking |

## Usage

```bash
helm repo add trix https://trixsec-dev.github.io/helmcharts
helm repo update
helm install trix trix/trix -n trix-system --create-namespace
```

## Configuration

See [trix/README.md](./trix/README.md) for all configuration options.

### Quick Start

```yaml
# values.yaml
postgresql:
  enabled: true

notifications:
  slack:
    enabled: true
    webhookUrl: "https://hooks.slack.com/services/..."
    minSeverity: "HIGH"
```

```bash
helm install trix trix/trix -n trix-system --create-namespace -f values.yaml
```

## Related Projects

- [trix](https://github.com/trixsec-dev/trix) - CLI tool for querying Kubernetes security findings
- [trix-agent](https://github.com/trixsec-dev/trix-agent) - In-cluster agent for continuous monitoring

## License

Apache 2.0 - See [LICENSE](LICENSE) for details.
