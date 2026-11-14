---
title: "Theme 08: Spatiotemporal World Models and Real-Time Simulation"
theme_id: "spatiotemporal-world-models-and-real-time-simulation"
kind: theme-deep-dive
phase: archive
talks: 2
claims: 11
---

# Spatiotemporal World Models and Real-Time Simulation

Scaling laws extend beyond turn-based text to continuous video and action streams, turning pixels-to-actions policies and next-frame predictors into real-time world simulators that internalize physics, control robots, and replace static 3D engines with interactive visual interfaces.

General Intuition and Runway pushed AI engineering past autoregressive text into continuous space and time. General Intuition argued that real-time agents must observe while acting, leveraging Medal's gameplay pipeline—scaling toward three billion videos a year and 1.5 trillion monthly controller actions—because high-APM game controllers share the exact action space of low-DOF robot teleoperation and plug neatly as reactive control layers beneath frontier LLM planners. Runway bet on compute scaling laws for next-frame video prediction, demonstrating that models trained at scale internalize geometry, gravity, occlusion, and object permanence directly from pixels—unlocking action-conditioned robotics simulators, engine-free World Interface Models with no Unity or Blender mesh underneath, interactive Continuum video portals, and visual scratchpads where coding agents simulate spatial designs alongside code. Their sharpest technical disagreement sits on supervision: General Intuition contended that explicit controller action labels transfer far better to real-time control than passive video-only latent inference because subtle inputs like aircraft rudder adjustments leave almost no trace in raw pixel frames.

## Observing while acting: gameplay controllers as the universal robotics interface

- **Pim de Witte (Frontier Models for Acting in Space and Time, 00:06:01)**: Medal's gameplay recorder is scaling from one billion to three billion uploaded videos annually, generating over 1.5 trillion action-labeled inputs per month and matching frontier robotics training volume in half a day.
  > “Medal at the moment sees about a billion videos uploaded per year. This year, we're on track for three billion, which lead to over a trillion and a half actions taken per month.”

- **Pim de Witte (Frontier Models for Acting in Space and Time, 00:07:53)**: High-APM gameplay trajectories provide far denser simultaneous multi-key supervision than sparse human teleoperation recordings, bringing high-frequency control tasks like drone micro-adjustment within reach.
  > “You don't want to start with tell operations because the human moves take a lot less actions. It has a lot less information, so you want a model that can predict really high APM.”

- **Pim de Witte (Frontier Models for Acting in Space and Time, 00:10:31)**: In production architectures, real-time pixel-to-action models serve as a fast reactive control layer plugged beneath a frontier LLM orchestrator such as Gemini that handles long-horizon planning.
  > “we still expect you to use an orchestrator model, so you may use something like Gemini or Astro in order to do long-term planning and everything, and you'll be able to plug these into your workloads.”

- **Pim de Witte (Frontier Models for Acting in Space and Time, 00:00:09)**: Autoregressive, turn-based LLMs struggle with spatial-temporal control because real-time physical and virtual agents must continuously observe incoming sensory frames while simultaneously executing actions.
  > “Olaf can, unlike LLMs, which auto-regressively predict tokens, constantly, part of that behavior is that it's constantly observing as it is acting.”

## Scaling next-frame video prediction into interactive World Interface Models

- **Cristóbal Valenzuela (Everything will be Simulated, 00:02:30)**: Predicting sequential frames at scale forces video models to internalize real-world geometry, gravity, occlusion, and object permanence directly from pixel data without hand-coded physics laws.
  > “You're learning about physics. You're learning about object permanence. You're learning about gravity, you're learning about occlusion. You're learning about movements. You're learning about how the objects work in the real world.”

- **Cristóbal Valenzuela (Everything will be Simulated, 00:02:30)**: Runway bets that compute scaling laws hold for next-frame video prediction just as they do for language models, yielding emergent visual realism that humans can no longer distinguish from real footage.
  > “I think we believe in scaling loss, not only applied for language models, but also for video, and this has been true.”

- **Cristóbal Valenzuela (Everything will be Simulated, 00:07:00)**: Conditioning real-time frame prediction on interventions at arbitrary steps turns offline video models into branching counterfactual world simulators capable of serving as reasoning brains for embodied robots.
  > “You take a frame, you predict next frame, then X, then X, then X, but then it can act at any point in time, in that prediction, which means I can simulate any possible divergence or action in that world.”

- **Cristóbal Valenzuela (Everything will be Simulated, 00:08:29)**: World interface models trained on UI clicks and user actions can manipulate objects and viewpoints inside a single 2D image in real time without any underlying 3D mesh or game engine.
  > “Now everything you just saw here has no physical 3D representation. There's no Unity. There's no Unreal. There's no Blender.”

- **Cristóbal Valenzuela (Everything will be Simulated, 00:10:12)**: Runway's Continuum research prototype treats a real-time world model as an operating system layer that turns structured web text into persistent, interactive video portals whose behavior adapts to clicks, queries, and window resizing.
  > “We call this a portal, and the portal is a real-time video. It's fully interactive and fully based on the content you're experiencing reading through.”

- **Cristóbal Valenzuela (Everything will be Simulated, 00:13:49)**: Connecting a coding agent to Continuum gives it an interactive visual scratchpad to simulate spatial designs alongside code, letting humans inspect and steer the agent's imagination directly rather than through text alone.
  > “So imagine you ask your coding agent to create a 3D model for your bike, and instead of the model trying to just think through that via code, the model can spin a version of Continuum to think through the problem visually.”

## Where text planners meet continuous visual scratchpads and real-time control

- **Cristóbal Valenzuela (Everything will be Simulated, 00:02:30)**: Predicting sequential frames at scale forces video models to internalize real-world geometry, gravity, occlusion, and object permanence directly from pixel data without hand-coded physics laws.
  > “You're learning about physics. You're learning about object permanence. You're learning about gravity, you're learning about occlusion. You're learning about movements. You're learning about how the objects work in the real world.”

- **Cristóbal Valenzuela (Everything will be Simulated, 00:02:30)**: Runway bets that compute scaling laws hold for next-frame video prediction just as they do for language models, yielding emergent visual realism that humans can no longer distinguish from real footage.
  > “I think we believe in scaling loss, not only applied for language models, but also for video, and this has been true.”

