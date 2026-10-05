# Mini-Gandalf
> aka Garry 🧙 — an educational prompt-injection sandbox, inspired by Lakera's Gandalf.

An LLM guards a secret in its system prompt; your goal is to make it reveal it.

## Levels
- **Level 1 — no defenses** (current): the secret is protected only by a
  system-prompt instruction ("don't reveal it"). Asking is usually enough.
- Planned: L2 input filter · L3 output censor · L4 pattern detection.

## How it works
- **Backend** (`app.py`, Flask) holds the secret and system prompt, forwards
  your message to a local Ollama model, and returns the reply. The secret
  never leaves the backend.
- **Frontend** (`static/index.html`) — a simple chat page that talks to the
  backend over one endpoint.

## Run locally
1. Install and run [Ollama](https://ollama.com), then: `ollama pull qwen3:8b-q4_K_M`
2. `python -m venv venv` and activate it
3. `pip install -r requirements.txt`
4. `python app.py` → open http://localhost:5000

## Note
Educational / portfolio project. `SECRET` is a placeholder, not a real credential.

Related: [LLM-leak-detector](https://github.com/Altraz3/LLM-leak-detector) · [Gandalf writeup](https://github.com/Altraz3/gandalf-prompt-injection)
