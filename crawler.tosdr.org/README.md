# Crawler Docker



## Run 

```bash
docker run -p 80:80 -e API_KEY=YOUR_API_KEY jbackpcat/crawler.tosdr.org:latest
```

## Configuration

You can use various environment variables to configure the crawler

| Variable       | Description                                                                      | Type    | Default                              |
|----------------|----------------------------------------------------------------------------------|---------|--------------------------------------|
| HTTP_PORT      | The HTTP Port to bind to                                                         | integer | 80                                   |
| HTTP_BIND      | The IP to bind to                                                                | string  | 0.0.0.0                              |
| API_KEY        | Your ToS;DR API Key. REQUIRED                                                    | string  | NULL                                 |
| IGNORE_ROBOTS  | Ignore the robots.txt?                                                           | boolean | false                                |
| FORBIDDEN_MIME | List of mimetypes the crawler should not crawl. Comma separated.                 | string  | application/octet-stream             |
| ALLOWED_MIME   | If set, the crawler will only crawl content types defined here. Comma separated. | string  | text/plain,text/html,application/pdf |
