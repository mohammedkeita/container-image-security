# Hardened base image using distroless
# Distroless removes shell, package managers, and extra binaries
# Result: ~20MB, minimal CVEs, smaller attack surface

FROM gcr.io/distroless/base-debian12:nonroot

# Labels
LABEL maintainer="your-email@example.com"
LABEL description="Hardened container image - minimal surface area"

# This image contains:
# - libc (C standard library)
# - ca-certificates (for HTTPS)
# - /etc/passwd (user data)
# - Nothing else

# The 'nonroot' variant means the container runs as user 'nonroot' (UID 65532)
# NOT as root, which is a security best practice

# If you had an application, it would go here:
# COPY --from=builder /app/myapp /app/myapp
# ENTRYPOINT ["/app/myapp"]

# For now, the image just has the base - that's enough to understand the concept
