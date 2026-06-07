# Container Image Supply Chain Security

## Week 1: Hardened Base Image

### Problem
Organizations deploy container images without understanding vulnerabilities inside them.

### Solution
Use distroless base images to minimize attack surface.

### What We Built
- Hardened Dockerfile using `gcr.io/distroless/base-debian12:nonroot`
- Image size: 20MB (vs Ubuntu 77MB+)
- Vulnerability scan: 0 CRITICAL, 0 HIGH vulnerabilities

### Quick Start
```bash
docker build -t my-hardened-app:v1 app/
trivy image my-hardened-app:v1
```

### Results
See [trivy-report.txt](docs/trivy-report.txt) for full scan output.

### Key Findings
- **0 CRITICAL vulnerabilities** - excellent baseline
- **0 HIGH vulnerabilities** - secure
- 4 MEDIUM, 8 LOW - acceptable for a minimal base image
- No shell, no package manager = smaller attack surface

### Next Week
- Image signing with Cosign
- GitHub Actions CI/CD pipeline
- Admission controller validation in Kubernetes
