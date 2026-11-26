# Aircraft Pitch PID Controller & Bad-Tuning Explorer

An interactive **Google Colab** engineering tool built with `ipywidgets`, `NumPy`, `Pandas`, and `Matplotlib` to simulate a closed-loop **PID controller for aircraft pitch** and demonstrate what happens when each tuning gain ($K_p$, $K_i$, or $K_d$) is set wrong.

## Overview

Pitch attitude control regulates an aircraft's nose angle toward a target pitch (`Target Pitch [deg]`) using elevator deflection[cite: 6]. This notebook lets you test both well-tuned and mis-tuned PID parameters, inspect a 2D pitch attitude view and time-series response plot, and read a cause-and-effect explanation of why the response behaves that way.

### Included Tuning Presets
- **Balanced Tune:** Fast, clean pitch tracking with minimal overshoot and near-zero steady-state error.
- **Low Kp (Sluggish):** Slow rise toward the target pitch angle due to weak proportional action.
- **High Kp (Oscillatory):** Aggressive control action causing large overshoot and oscillations.
- **Low Ki (Steady Offset):** Leaves a persistent steady-state pitch error.
- **High Ki (Windup/Unstable):** Excessive integral accumulation causing slow or growing oscillations.
- **Low Kd (Underdamped):** Low derivative damping leading to repeated bouncing/oscillations.

## Key Features

- **Interactive English UI (`ipywidgets`):** Choose a tuning preset or adjust `Target Pitch [deg]`, `Kp`, `Ki`, and `Kd` sliders directly, then update live or click **Run Pitch Simulation**.
- **2D Aircraft Pitch Attitude & Time Response:** Shows a 2D pitch attitude schematic alongside the `Pitch Angle vs. Time` response plot.
- **Metrics & Cause-and-Effect Verdict:** Reports `Final Pitch`, `Overshoot`, and `Steady-State Error`, paired with a clear explanation of why the response occurred.

## How to Run in Google Colab

1. Open a new notebook in [Google Colab](https://colab.research.google.com/).
2. Paste the aircraft pitch PID simulator code into a code cell and run it.
3. Select a tuning preset or drag the `Kp`, `Ki`, and `Kd` sliders to see how each parameter affects pitch stability and tracking.

## Engineering Notes

- Real aircraft pitch dynamics also depend on airspeed, center-of-gravity location, actuator rate/position limits, and atmospheric gusts; use this simulation as a conceptual tuning intuition tool before hardware or higher-fidelity flight-dynamics testing.
