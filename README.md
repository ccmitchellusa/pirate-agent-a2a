# Pirate Agent A2A

Pirate Agent A2A is an autonomous agent framework designed to simulate pirate-themed decision-making and task execution. This project leverages AI to create agents capable of navigating challenges, managing resources, and interacting with their environment in a pirate-inspired context.

## Features

- **Autonomous Decision-Making**: Agents make decisions based on predefined goals and environmental inputs.
- **Resource Management**: Simulates treasure hunting, ship maintenance, and crew management.
- **Environment Interaction**: Agents interact with dynamic environments, including islands, ships, and other agents.
- **Customizable Scenarios**: Easily configure scenarios to test different pirate-themed strategies.

## Installation & Setup

1. Clone the repository:
```bash
git clone https://github.com/yourusername/pirate-agent-a2a.git
cd pirate-agent-a2a
```
2. Install dependencies:
```bash
uv sync --reinstall
```
alternatively:
```bash
pip install -r requirements.txt
```

## Containerization

### Build

```bash
docker build -f Containerfile -t pirate-agent:a2a -o "type=local,dest=./out/pirate-agent" .
```

### Deploy to local Podman, Rancher or Docker desktop
```bash
podman run --rm -i pirate-agent:a2a
```

### Build and deploy to IBM Cloud container registry
In this example, agentic is your icr NAMESPACE and a2a is your REPOSITORY name.
Replace RESOURCE_GROUP with the name of the resource group where you want the container registry.
```bash
# Log docker into the IBM Clouf container registry at icr.io
ibmcloud cr login 
ibmcloud cr namespace-add -g RESOURCE_GROUP agentic
# Build the image and push it to the container registry in the 'agentic' namespace and 'a2a' repository.
docker build -f Containerfile --push -t icr.io/agentic/a2a .

```

## Usage

Start the agent:
```bash
./run.sh
```

## Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository.
2. Create a new branch for your feature or bug fix.
3. Submit a pull request with a detailed description of your changes.

## License

This project is licensed under the [MIT License](LICENSE).

## Acknowledgments

Special thanks to Chris Hayuk and the open-source community for providing tools and inspiration for this project.
