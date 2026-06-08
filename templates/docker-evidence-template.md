# Docker Evidence – Lab 04

## Team

- Team name:
- Service:
- Image tag:

## 1. Build evidence

Command:

```bash
docker build -t <image-name>:<tag> .
```

(base) D:\Baitap\Dịch vụ kết nối và CN nền tảng\lab4-Tran-Thanh-Binh-3825>docker build -t fit4110/camera-stream:lab04 .
[+] Building 10.0s (17/17) FINISHED                                             docker:desktop-linux
 => [internal] load build definition from Dockerfile                                            0.1s
 => => transferring dockerfile: 1.11kB                                                          0.0s
 => resolve image config for docker-image://docker.io/docker/dockerfile:1.7 

## 2. Run evidence

Command:

```bash
docker run --rm -p 8000:8000 --env-file .env.example <image-name>:<tag>
```

(base) D:\Baitap\Dịch vụ kết nối và CN nền tảng\lab4-Tran-Thanh-Binh-3825>docker run --rm --name fit4110-camera-lab04 -p 8000:8000 --env-file .env.example fit4110/camera-stream:lab04
INFO:     Started server process [7]
INFO:     Waiting for application startup.
INFO:     Application startup complete.
INFO:     Uvicorn running on http://0.0.0.0:8000 (Press CTRL+C to quit)
INFO:     127.0.0.1:36958 - "GET /health HTTP/1.1" 200 OK

## 3. Healthcheck evidence

Command:

```bash
curl http://localhost:8000/health
```

Result:

```json
{
  "status": "ok"
}
```

## 4. Newman evidence

Command:

```bash
npm run test:local
```

Report path:

```text
reports/newman-lab04-local.html
reports/newman-lab04-local.xml
```

## 5. Notes

- Known limitation:
- Next step for Lab 05:
