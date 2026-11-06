# Cloud Run contract lab

Intentionally broken local Docker starter. No Google Cloud account, billing, credentials or cloud deployment needed. Local rehearsal is not actual Cloud Run deployment evidence.

## Requirements

Docker running, Git, curl, text editor. Windows: Git Bash, then `export MSYS_NO_PATHCONV=1` in each terminal.

## Start

```bash
docker build -q -t contract-api:lab .
docker run -d --name contract-api -e PORT=8080 -p 127.0.0.1:18080:8080 contract-api:lab
sleep 2
curl -i --max-time 3 http://localhost:18080/health
docker logs contract-api
```

Host port 18080 must be free. If retrying, remove only this lab container: `docker rm -f contract-api`.

## Three tasks

1. Diagnose why a running process cannot receive forwarded traffic. Fix the listening interface in `app.py`. Rebuild/recreate and verify HTTP response.
2. Test the same image with supplied `PORT=9090` and corresponding target mapping. Diagnose failure, make the app honor the setting, rebuild, then prove the same final image works at both 9090 and 8080 without rebuilding between runs.
3. Correct all seven claims in `deployment-notes.md`. Explain what local evidence can and cannot prove. No real cloud resources.

Keep Dockerfile and response fields unchanged. Commit each task separately. Submission requirements and marks are in your assignment page.
