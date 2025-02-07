# Dockerfile Bug: Incorrect COPY Command Order

This repository demonstrates a common error in Dockerfiles: incorrect order of COPY commands when dealing with dependencies.

The original `Dockerfile` attempts to install dependencies before copying the application source code, leading to an error.  The solution provided fixes this by ensuring the source code is copied *before* the installation of dependencies. 

## How to Reproduce
1. Clone this repository.
2. Build the original Dockerfile: `docker build -f Dockerfile -t buggy-app .`
3. Try to run the image: `docker run buggy-app` (This will fail).
4. Build the fixed Dockerfile: `docker build -f Dockerfile.fixed -t fixed-app .`
5. Run the fixed image: `docker run fixed-app` (This will run successfully)
