# AbstractAI LLM Inference Router

AbstractAI is a versatile inference router designed to facilitate seamless integration and utilization of both local and online Language Learning Models (LLMs). With AbstractAI, you can effortlessly switch between different LLMs based on your requirements for price, performance, and latency.

## Features

Currently, the following features are planned and under development:

- **RouterLLM**: A robust system to route inference requests to the most suitable LLM based on predefined criteria.
- **Local LLM Support**: Integration with local LLMs using `llama.cpp`.
- **Online LLM Support**: Integration with various online LLMs through APIs.
- **Dynamic Model Selection**: Ability to choose between models based on cost, performance, and latency.
- **Chain of Thoughts and Mixture of Agents**: Advanced techniques for enhancing inference quality.
- **Prompt Management**: Efficient handling and management of prompts.

## Getting Started

### Prerequisites

- Docker installed on your system.
- API keys for online LLMs (e.g., OpenAI, GPT-3).

### Installation

1. Clone the repository:

```sh
git clone https://github.com/yourusername/AbstractAI.git
cd AbstractAI
```

2. Build and run the Docker container:

```sh
docker-compose up --build
```

### Configuration

1. **RouterLLM Configuration**:
   - Configure `RouterLLM` to route requests to the desired LLM based on price, performance, and latency.
   - Example configuration file (`config.yaml`):

```yaml
routerllm:
  selection_criteria: 
    - price
    - performance
    - latency
  models:
    local:
      llama:
        path: "/path/to/llama/model"
    online:
      openai:
        api_key: "YOUR_OPENAI_API_KEY"
        model: "gpt-3.5-turbo"
      other_online_llm:
        api_key: "YOUR_OTHER_LLM_API_KEY"
        model: "model_name"
```

2. **Prompt Management**:
   - Define prompts and manage them efficiently within the `prompts/` directory.

## Usage

1. **Running Inference**:
   - Once the Docker container is running, you can make inference requests to the AbstractAI router.

```sh
curl -X POST http://localhost:8000/inference \
     -H "Content-Type: application/json" \
     -d '{"prompt": "Your prompt here"}'
```

2. **Chain of Thoughts and Mixture of Agents**:
   - Utilize advanced techniques to enhance the quality of the responses.

### Example Usage

```python
import requests

url = "http://localhost:8000/inference"
data = {
    "prompt": "Explain the theory of relativity in simple terms."
}
response = requests.post(url, json=data)
print(response.json())
```

## Development

### Implementing RouterLLM

- **RouterLLM**: Implement logic to route requests based on user-defined criteria such as cost, performance, and latency.
- **Online LLM Integration**: Add support for new online LLMs by extending the API integration layer.

### Adding New Features

- Implement new selection criteria for RouterLLM.
- Enhance prompt management and storage mechanisms.
- Improve the user interface for configuring and managing models.

## Contributing

We welcome contributions! Please follow the standard GitHub flow for contributing:

1. Fork the repository.
2. Create a new branch (`git checkout -b feature-branch`).
3. Commit your changes (`git commit -am 'Add some feature'`).
4. Push to the branch (`git push origin feature-branch`).
5. Create a new Pull Request.

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.

## Acknowledgements

We would like to thank the contributors and the open-source community for their support and contributions to this project.

---

For more information, feel free to contact the project maintainer at [your-email@example.com].

Enjoy using AbstractAI!
