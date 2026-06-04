
Containerization is a lightweight form of virtualization that packages an application and all its dependencies (libraries, binaries, config files, etc.) into a single unit called a container. This ensures the application runs consistently across different environments — from development to production.

- It is a lightweight virtualization technology alternative to hypervisor virtualization.
- Any application can be bundled in a container can run without any worries about dependencies, libraries and binaries.
- So, containers are designed to run on physical servers, virtual machines and any cloud instances.
- Also container was designed to solve modern problems and application management issues. so it is not a replacement for virtualization, but it’s complementary to it.

Container:
A container is a lightweight, isolated environment that runs an application along with everything it needs like libraries and dependencies without depending on the host system. It uses the host operating system's kernel but keeps the app's files separate.

Key points about containers:
- They run in their own space but share the host OS kernel.
- They are created from container images.
- They start quickly, use fewer resources, and are more portable than virtual machines (VMs).

📌 Think of a container as a small, self-contained box that runs your app like a mini-sandbox without the heavy setup of a full operating system like a VM.

Container Engine = CLI / tool users interact with to build, run, and manage containers. e.g., Docker CLI, Podman CLI.(User-facing tool that orchestrates everything.)
Container Runtime = Low-level tool responsible for creating and running containers using Linux kernel features(namespaces, cgroups, seccomp, etc..) e.g., runc, cri-o, containerd.


Container Engine
What it does:

Provides a CLI or API interface.
Pulls container images.
Builds new images.
Runs and manages containers.
Talks to the runtime to actually execute the container.
📌 Examples: Podman , Docker, CRI-O (used in OpenShift — container runtime interface only)


Container Runtime
What it does:

Actually starts the container process.
Uses kernel features like namespaces, cgroups, seccomp, and SELinux.
Enforces isolation and resource control.
📌 Examples: runc (used by Podman and Docker) , crun (faster, written in C, default in newer Podman) , containerd (used in Docker and Kubernetes) , CRI-O (used in OpenShift)

📌 Podman uses runc or crun under the hood, while OpenShift uses CRI-O, which in turn also uses runc or crun.

#############################################################################################