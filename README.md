# LLM Guard
LLM evaluation + red teaming harness built on promptfoo, running fully local models via Ollama.

## Setup
1. Install Ollama (https://ollama.com) and pull models:
   ollama pull llama3.2
   ollama pull llama3.2:1b
2. Install deps:
   npm install

## Evals
Run the quality/correctness tests and open the dashboard:

    npx promptfoo eval
    npx promptfoo view

Save results for the custom dashboard:

    npx promptfoo eval -o output.json

## Red teaming
Quick scan while developing:

    npx promptfoo redteam run -c redteam.fast.yaml
    npx promptfoo redteam report

Thorough scan (slower):

    npx promptfoo redteam run -c redteam.full.yaml
    npx promptfoo redteam report

## Concepts
- **Evals** = is the model correct/good? Metric: pass rate.
- **Red teaming** = can the model be tricked into something harmful? Metric: attack success rate.
- **plugins** = what weakness to test. **strategies** = how to attack.