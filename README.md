# LLVM Containers
This project automatically builds Docker images that contain LLVM development environments.

## Containers
Built containers are automatically pushed to the GitHub Container Registry and are named in the following format: `ghcr.io/cuckooexe/llvm-container-<targets>-<projects>-<runtimes>-<build_type>`. You can see how they're built in `.github/workflows/docker-publish.yml`. They only differ in the `jobs.<job_id>."Build and Push Docker image".with.build-args`, where the build arguments for the Dockerfile are defined. The build arguments are:
 - LLVM_TARGETS_TO_BUILD
 - LLVM_ENABLE_PROJECTS
 - LLVM_ENABLE_RUNTIMES
 - CMAKE_BUILD_TYPE

You can see their valid options and effects in the [LLVM CMake documentation](https://llvm.org/docs/CMake.html).