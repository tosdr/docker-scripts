# NAME:		jbackpcat/tosdr-crisp
# VERSION: DEVELOPMENT
# IMPORTANT: Build from Repository Root!
FROM debian:buster-slim

# Accept Environment Variables, set defaults


# Expose Ports
EXPOSE 80


ENV HTTP_PORT "80"
ENV HTTP_BIND "0.0.0.0"
ENV API_KEY ""
ENV IGNORE_ROBOTS "false"
ENV FORBIDDEN_MIME "application/octet-stream"
ENV ALLOWED_MIME "text/plain,text/html,application/pdf"

# Add our Scripts

ADD crawler.tosdr.org/start.sh /start.sh
RUN chmod +x /start.sh

# Bootstrap the image
RUN apt-get update && \ 
	apt-get install -y curl && \ 
	curl -fsSL https://deb.nodesource.com/setup_14.x | bash - && \
	apt-get install -y nodejs build-essential git chromium
	
RUN git clone https://github.com/tosdr/crawler.tosdr.org.git /opt/crawler


RUN cd /opt/crawler && npm install



CMD /start.sh
