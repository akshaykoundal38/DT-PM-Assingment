# Product Management Assignment: Knowledge Engineering Write-Up
**Project:** Daily Reflection Tree (The Workshop)

## 1. Design Strategy & Theme
I designed this tool using a **"Workshop" metaphor** (Craftsman vs. Apprentice). The goal was to create a minimalist, high-fidelity experience that mirrors the simplicity of medical software. 

By using metaphors instead of psychological jargon:
* **Neutrality:** Users don't feel "wrong" for being an Apprentice (External Locus) on a busy day.
* **Clarity:** It reduces the "Social Desirability Bias," where users pick the "correct" sounding answer instead of the "true" one.

## 2. Theoretical Mapping
The decision tree is strictly deterministic, mapping three specific axes:

| Axis | Internal/Growth/System | External/Fixed/Self |
| :--- | :--- | :--- |
| **Locus of Control** | **The Craftsman:** Driving the day. | **The Apprentice:** Responding to demands. |
| **Mindset** | **Improving:** Learning from friction. | **Validating:** Surviving the task list. |
| **Radius of Concern** | **The Shop:** Focused on team flow. | **The Workbench:** Focused on personal tasks. |

## 3. Controlling AI Hallucinations (Guardrails)
To ensure the AI remained a tool and not the "author," I set the following guardrails:

* **Strict Determinism:** I forced the AI to generate a branching JSON structure. I explicitly forbade the use of any natural language generation at runtime to ensure the reflection remains consistent and auditable.
* **Negative Prompting:** I instructed the AI: *"DO NOT use HR-speak, DO NOT use judgmental adjectives (e.g., 'passive', 'lazy'), and DO NOT exceed 20 words per option."*
* **Manual Logic Audit:** I disagreed with the AI's first draft which tried to merge "Locus" and "Mindset" into a single question. I manually separated them to maintain the scientific integrity of the 3-axis model.

## 4. Alignment with Guidelines
* **No-LLM at Runtime:** The final output is an interpolation of pre-written strings.
* **Knowledge Engineering:** The logic is structured so that the "Reflection" at the end is a perfect mirror of the user's specific path through the three psychological frameworks.
