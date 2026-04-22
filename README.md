# Droplet Collision Analysis (Pre-Collision Dynamics)

This computational script analyzes **pre-collision droplet dynamics** from high-speed binary images to compute:

- Droplet velocities
- Relative velocity
- Weber number (We)
- Impact parameter (B)
- Droplet diameter
- Size mismatch error

The script processes image sequences where two droplets approach and collide, focusing on **frames before collision occurs**.

---

## Overview

The workflow:

1. Read processed (binary) droplet images
2. Detect when collision starts (two → one droplet)
3. Track droplet positions before collision
4. Compute velocities and relative motion
5. Calculate Weber number and impact parameter
6. Export results to Excel

---

## Input Data

### Image Source

The script reads processed binary images from:

```matlab
PROCESS/bouncing/timeX/add1/*.tif
