FROM node:22-alpine

WORKDIR /app

# Install dependencies
COPY package*.json ./
RUN npm install

# Copy application code
COPY . .

# Supply public URL during build for Next.js static generation
ARG NEXT_PUBLIC_API_URL
ENV NEXT_PUBLIC_API_URL=$NEXT_PUBLIC_API_URL

# Build the Next.js application
RUN npm run build

# Expose frontend port (Railway ignores this and uses its own PORT variable)
ENV PORT=3000
ENV HOSTNAME="0.0.0.0"
EXPOSE 3000

# Start the application, strictly locking to port 3000 to match Railway Proxy Target Port
CMD ["npm", "start", "--", "-p", "3000"]
