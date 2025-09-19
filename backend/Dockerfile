# Use Alpine Linux for small image size
FROM alpine:latest

# Install necessary packages
RUN apk add --no-cache ca-certificates

# Create app directory
WORKDIR /app

# Copy PocketBase binary
COPY pocketbase /app/pocketbase
RUN chmod +x /app/pocketbase

# Copy data directory (optional - for initial setup)
COPY pb_data /app/pb_data

# Create volume for persistent data
VOLUME ["/app/pb_data"]

# Expose port
EXPOSE 8090

# Health check
HEALTHCHECK --interval=30s --timeout=3s --start-period=5s --retries=3 \
  CMD wget --no-verbose --tries=1 --spider http://localhost:8090/api/health || exit 1

# Run PocketBase
CMD ["./pocketbase", "serve", "--http=0.0.0.0:8090"]
