# WebGuard – C++ Edition

**An Automated Web Security Assessment and Vulnerability Analysis System**

This is a C++17 command-line starter project. It performs a limited, non-invasive review of response headers for a website the operator owns or is explicitly authorized to assess.

## Current features
- HTTPS check based on the final URL
- Presence checks for common HTTP security headers
- Basic inspection of a visible Set-Cookie header
- Basic observation of CORS response headers
- Simple PASS-count score
- Saves URL, HTTP status and score to `webguard_history.csv`

## Technology
- C++17
- libcurl for HTTP requests
- CMake for building

## Build
Requirements: C++17 compiler, libcurl development package, CMake 3.15+.

```bash
cmake -S . -B build
cmake --build build
```

Run the generated `webguard` executable. Enter a URL beginning with `https://` or `http://`, then type `YES` only if you own the site or have explicit permission.

## Responsible use and limitations
Only assess websites you own or have explicit permission to assess. This tool performs basic configuration checks, not penetration testing. It uses a HEAD request, so some websites may not return all headers on HEAD responses. Cookie inspection is intentionally basic and may not fully parse multiple cookie headers. CORS cannot be judged fully from one response header. A missing header is not proof of an exploitable vulnerability.

## Project status
Starter implementation for academic development. Compile and run it in your own environment, record genuine test results, and add screenshots before claiming it is fully tested or complete.
