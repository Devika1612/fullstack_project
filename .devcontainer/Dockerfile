# Base image
FROM mcr.microsoft.com/vscode/devcontainers/base:ubuntu-22.04

# Install necessary tools and dependencies
RUN apt-get update && apt-get install -y \
    wget \
    libxext6 \
    libxrender1 \
    libxtst6 \
    libgtk-3-0 \
    unzip \
    && rm -rf /var/lib/apt/lists/*

# Install Oracle SQL Developer 19
RUN wget -q https://download.oracle.com/sql-developer/sql-developer-19.x.x.noarch.rpm -O /tmp/sql-developer.rpm && \
    apt-get install -y alien && \
    alien -i /tmp/sql-developer.rpm && \
    rm -f /tmp/sql-developer.rpm && \
    apt-get remove -y alien

# Add SQL Developer to PATH
ENV PATH="/opt/sqldeveloper/bin:$PATH"
