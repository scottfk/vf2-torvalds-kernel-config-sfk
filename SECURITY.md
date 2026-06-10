# Security

This project is a kernel `.config` file, not a software package. It has no executable
code, no dependencies, and no release cycle of its own.

If a security fix lands in the upstream kernel, I'll pick it up the next time I build
against a new tag. There's nothing to report here and nothing to patch independently.

If you've spotted a config option that has known security implications — something
enabled that shouldn't be, or a hardening option worth adding — feel free to open a
plain GitHub issue. No special disclosure process needed.
