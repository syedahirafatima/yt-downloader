Garden Linux Bare Container Documentation
Overview

Garden Linux offers a range of specialized bare container images, each tailored for specific applications and designed for minimalism and security:

Bare-libc: Ideal for C/C++ applications requiring only essential C runtime libraries.

Bare-python: Equipped with Python runtime, perfect for Python-based applications.

Bare-sapmachine: Customized for sapmachine with necessary libraries and binaries.

Bare-nodejs: Includes Node.js environment, suitable for server-side JavaScript applications.

These containers are optimized as base images for Dockerfiles. Their development is streamlined by the unbase_oci
 tool, which efficiently minimizes image size by removing unnecessary components from base container images.

Unbase OCI Tool

Description: The unbase_oci tool is instrumental in the development of these "bare" container images.

Functionality:

Strips unnecessary components from base container images.

Reduces image size and potential security vulnerabilities.

Operates on OCI archives, comparing base and target images to identify and retain only necessary additions and their dependencies.

Repository Link: unbase_oci

Impact: This tool is pivotal in creating streamlined, "distroless-like" images, ensuring that the resulting containers are lean and secure.

Bare-libc

Description: A streamlined container image for applications that need only the basic C library.

Features:

Includes essential C runtime libraries.

Suited for C/C++ applications with minimal dependencies.

Enhanced security through a minimal attack surface.

Container Link: bare-libc

Usage in Dockerfile:

FROM ghcr.io/gardenlinux/gardenlinux/bare-libc:nightly
COPY hello /hello
CMD ["/hello"]

Bare-python

Description: Optimized for Python applications, this image provides the Python runtime.

Features:

Contains the Python interpreter and necessary libraries.

Ideal for Python-based applications.

Designed for improved security and efficiency.

Container Link: bare-python

Usage in Dockerfile:

FROM ghcr.io/gardenlinux/gardenlinux/bare-python:nightly
COPY hello.py /
CMD ["python3", "/hello.py"]

Bare-sapmachine

Description: Customized for SAP applications, ensuring compatibility and optimized performance.

Features:

Necessary libraries and binaries for SAP included.

Optimized for sapmachine.

Security-focused design.

Container Link: bare-sapmachine

Usage in Dockerfile:

FROM ghcr.io/gardenlinux/gardenlinux/bare-sapmachine:nightly
COPY HelloWorld.java /
RUN javac HelloWorld.java
CMD ["java", "HelloWorld"]

Bare-nodejs

Description: A container tailored for Node.js applications, providing the Node.js runtime.

Features:

Includes Node.js environment.

Suitable for server-side JavaScript applications.

Minimized footprint for enhanced security and performance.

Container Link: bare-nodejs

Usage in Dockerfile:

FROM ghcr.io/gardenlinux/gardenlinux/bare-nodejs:nightly
COPY app.js /
CMD ["node", "/app.js"]

