# Changelog since 3.6.0
- Stop with a clear message on CPUs without x86-64-v2 (#22)

NumPy's wheels now require x86-64-v2, so on a CPU without it (most often a
Proxmox VM with CPU type kvm64, which hides SSSE3, SSE4.x and POPCNT) the
service died importing numpy with "NumPy was built with baseline
optimizations: (X86_V2) but your machine doesn't support: (X86_V2)".

Check the same flags NumPy does for its X86_V2 baseline before starting, and
exit with the missing features and the fix (CPU type "host") instead. The AVX
warning is unchanged. Documented under Installation.

Fixes #1.

Co-authored-by: Claude Opus 5.5 <noreply@anthropic.com> 
