# mkdocs
Local Docker setup for [MKDocks](https://www.mkdocs.org/), the project documentation with markdown.

---

MkDocs is a fast, simple and downright gorgeous static site generator that's geared towards building project documentation. Documentation source files are written in Markdown, and configured with a single YAML configuration file. Start by reading the [introductory tutorial](https://www.mkdocs.org/getting-started/), then check the [User Guide](https://www.mkdocs.org/user-guide/) for more information.

- Python 3.12
- MKDocs 1.6.1 at commit timestamp

## Getting Started
This guide will assist with running your markdown project in docker.

### Requirements
- Docker
- markdown project

### Create markdown project 
- [User Guide](https://www.mkdocs.org/user-guide/), skip installation step.
- In the mkdocs.yaml, ensure you have the following configuration
```
dev_addr: "0.0.0.0:8000"
```

### Running MKDocs Docker 
1. Pull Docker image
```
docker pull ghcr.io/kourtneya/mkdocs
```
2. Run Docker image
```
docker run -p {hostPort}:8000 -v {localProjectDir}:/home mkdocs:latest
```
> In the run command mount the directory of the project on your local to the `home` directory of the container. Also, to run in detached mode just add `-d` (e.g docker run -d).
3. Navigate to MkDocs Project Url, `http://localhost:{hostPort}`
4. As you make changes to the `docs` and `mkdocs.yaml` in the local directory, the running application will be watching for those changes.