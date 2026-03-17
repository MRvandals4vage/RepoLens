FROM node:20-bookworm-slim

# Install git (for simple-git) and build tools (for tree-sitter native addons)
RUN apt-get update && apt-get install -y --no-install-recommends git python3 make g++ ca-certificates && rm -rf /var/lib/apt/lists/*

WORKDIR /app

# Install dependencies (--legacy-peer-deps: tree-sitter-java peer expects ^0.21 but we use 0.25)
# Set JOBS=1 to limit C++ compilation max workers, preventing OOM / Exit Code 254 on Railway
COPY package*.json ./
ENV JOBS=1
RUN npm install --legacy-peer-deps --no-audit --no-fund

# Copy application code
COPY . .

# Expose backend port
EXPOSE ${PORT:-5001}

# Start the server
CMD ["node", "index.js"]
