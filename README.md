# 🏴‍☠️Pirate Agent A2A

Pirate Agent A2A is an autonomous agent designed to simulate conversations with a pirate. 

## Features

- **Pirate-speak**: Ahoy matey! 

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
docker build --load -t pirate-agent:latest .
```

### Deploy to local Podman, Rancher or Docker desktop
```bash
docker images ls
```
Get the image id that was pushed
Now run the image (on local podman)
```
podman run --rm -it pirate-agent:latest
```

### Build and deploy to IBM Cloud container registry
In this example, agentic is your icr NAMESPACE and a2a is your REPOSITORY name.
Replace RESOURCE_GROUP with the name of the resource group where you want the container registry.
```bash
# Log docker into the IBM Clouf container registry at icr.io
ibmcloud cr login 
ibmcloud cr namespace-add -g RESOURCE_GROUP agentic
# Build the image and push it to the container registry in the 'agentic' namespace and 'a2a' repository.
docker build -f Dockerfile --push -t icr.io/agentic/a2a .

```

### Run from source code in IBM Cloud container engine

1. Navigate to Containers/Serverless/Projects
2. Create a project, eg. “A2A-play”
3. Navigate to “Applications”
4. Create application
	Name: pirate-agent-a2a
	Code repo URL: https://github.com/ccmitchellusa/pirate-agent-a2a

5. Navigate to "Optional settings"
	Image start options
		Listening port: 8000

6. Scroll back up to Code section.
7.  Select “Specify build details” > Next > Next >.
8. Select a container registry namespace
9. Select Done


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
