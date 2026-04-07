# Debate Crew

Welcome to the Debate Crew project, powered by [crewAI](https://crewai.com). This project automates multi-agent debate simulations where AI agents argue for and against motions, with a judge deciding the winner based on argument quality.

## Project Overview

The Debate Crew consists of:
- **Debater Agent**: Presents compelling arguments both for and against a given motion
- **Judge Agent**: Evaluates arguments objectively and decides which side is more convincing

The system generates three output files:
- `output/propose.md` - Arguments in favor of the motion
- `output/oppose.md` - Arguments against the motion
- `output/decide.md` - Judge's decision and reasoning

## Installation

Ensure you have Python >=3.10 <3.14 installed on your system. This project uses [UV](https://docs.astral.sh/uv/) for dependency management and package handling.

First, if you haven't already, install uv:

```bash
pip install uv
```

Next, navigate to your project directory and install the dependencies:

```bash
crewai install
```

### Configuration

**Add your `OLLAMA_BASE_URL` or LLM configuration into the `.env` file** (the project uses `ollama/gemma3:4b` by default)

To customize the debate:
- Modify `src/debate/config/agents.yaml` to change agent roles, goals, and LLM models
- Modify `src/debate/config/tasks.yaml` to define debate tasks and outputs
- Modify `src/debate/crew.py` to add custom logic or tools
- Modify `src/debate/main.py` to set custom debate motions and inputs

## Running the Project

To start a debate, run:

```bash
crewai run
```

You'll be prompted to enter a debate motion. The crew will then:
1. Generate an argument supporting the motion
2. Generate an argument opposing the motion
3. Have the judge evaluate both arguments and decide the winner

Output files are saved to the `output/` directory.

## Understanding Your Crew

The Debate Crew demonstrates agent collaboration where:
- Multiple agents work on related tasks with a common input (the motion)
- Task outputs can feed into subsequent tasks for evaluation
- Agents operate independently but within a coordinated workflow
- The judge's decision is based purely on argument quality, not pre-existing bias


