FROM mcr.microsoft.com/devcontainers/base:ubuntu-24.04

# ECLIPSE cloud environment for Godot GDScript and command-line testing.
RUN apt-get update \
    && DEBIAN_FRONTEND=noninteractive apt-get install -y --no-install-recommends \
       ca-certificates curl unzip python3 python3-pip python3-venv git libfontconfig1 \
    && rm -rf /var/lib/apt/lists/*

# Match the project's local Godot version; verify the downloaded archive.
ARG GODOT_VERSION=4.7.2
ARG GODOT_ZIP_SHA256=cadd3204e728a35d3f13adb7fd0d7902636b79f6b95c40c265eb73b6c35329e4
RUN set -eux; \
    curl -fL --retry 3 --retry-delay 2 \
      "https://github.com/godotengine/godot-builds/releases/download/${GODOT_VERSION}-stable/Godot_v${GODOT_VERSION}-stable_linux.x86_64.zip" \
      -o /tmp/godot.zip; \
    echo "${GODOT_ZIP_SHA256}  /tmp/godot.zip" | sha256sum -c -; \
    mkdir -p /tmp/godot-bin; \
    unzip -q /tmp/godot.zip -d /tmp/godot-bin; \
    install -m 0755 "/tmp/godot-bin/Godot_v${GODOT_VERSION}-stable_linux.x86_64" /usr/local/bin/godot; \
    rm -rf /tmp/godot.zip /tmp/godot-bin; \
    godot --headless --version
