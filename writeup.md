# **PID Controller**
---

**PID Control Project**

The goals / steps of this project are the following:
* Describe the effect each of the P, I, D components had in your implementation.
* Describe how the final hyperparameters were chosen.

## Rubric Points
###Here I will consider the [rubric points](https://review.udacity.com/#!/rubrics/824/view) individually and describe how I addressed each point in my implementation.  

---
### Compilation

#### 1. Your code should compile.

My code compiles without errors with `cmake` and `make`.


### Implementation

#### 1. The PID procedure follows what was taught in the lessons.

Based on the lecture, I implemented `Init`, `UpdateError` and `TotalError` methods of PID class. I tuned hyperparameters of PID class with the order of P, D and I components considering their influences on steering.


### Reflection

#### 1. Describe the effect each of the P, I, D components had in your implementation.

| component  | effect       |
|:----------:|:------------:|
| P          | Steer in proportion to Cross Track Error|
| D          | Prevent car overshooting             |
| I          | Reduce systematic bias             |

#### 2. Describe how the final hyperparameters were chosen.

I tuned them manually with the order of P, D and I component.

If P is high (e.g., 0.5), the vehicle oscillates fast. When it meets the sharp turn, it goes off the track fast.
If P is low (e.g., 0.005), the vehicle oscialltes slow. When the vehicle goes off the track, it doest not adjust fast on the track.

If D is high (e.g., 10.0), it does not help to reduce CTE fast.
If D is low (e.g., 1.0), it does not help much to avoid overshooting.

If I is high (e.g., 0.001), the vehicle goes off the track fast. The systematic bias is overestimated in this case.

My final choice is P=0.1, D=4.5, and I=0.0001.

### Simulation

#### 1. The vehicle must successfully drive a lap around the track.

The vehicle drives around the track safely.
