FROM amd64/alpine:3.17

RUN apk add --no-cache \
        ca-certificates \
        \
        # .NET dependencies
        krb5-libs \
        libgcc \
        libintl \
        libssl3 \
        libstdc++ \
        zlib \
        icu-libs \
        icu-data-full \
        libgdiplus \
        libmagic
RUN apk add --no-cache msttcorefonts-installer fontconfig && update-ms-fonts && fc-cache -f        
RUN rm -rf /var/lib/apt/lists/*
ENV \
    # Configure web servers to bind to port 80 when present
    ASPNETCORE_URLS=http://+:80 \
    # Enable detection of running in a container
    DOTNET_RUNNING_IN_CONTAINER=true
