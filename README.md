# Uncommon Dockerfile Bug: Using `ubuntu:latest` and Poor `apt-get` Practices

This example demonstrates a common but subtle issue in Dockerfiles: using `ubuntu:latest` and neglecting best practices in `apt-get` commands.  Using `ubuntu:latest` lacks reproducibility, and improper `apt-get` usage leads to larger image sizes and potential build issues.

**Bug:**

The provided Dockerfile uses `ubuntu:latest`, which is non-deterministic. Each time it's built, a potentially different version of Ubuntu might be used leading to inconsistencies. It also does not clean up packages after installation.

**Solution:**

The solution provides a more robust and reproducible Dockerfile. It specifies a precise Ubuntu version (e.g., 22.04), includes `apt-get clean` to remove downloaded packages, and utilizes `-y` for automatic acceptance of prompts.

This improved Dockerfile ensures consistency and reduces the image's size.
