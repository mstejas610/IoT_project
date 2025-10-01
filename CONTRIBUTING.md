# 🤝 Contributing to IoT Edge Computing Project

We welcome contributions to improve our smart city IoT edge computing implementation! This guide outlines how to contribute effectively.

## 🎯 How to Contribute

### Types of Contributions
- 🐛 **Bug fixes** in edge processing algorithms
- ✨ **New features** for IoT sensor integration
- 📝 **Documentation** improvements
- 📊 **Performance optimizations** for latency reduction
- 🧪 **Testing** and validation scripts
- 🎨 **UI/UX improvements** for monitoring dashboards

## 🚀 Getting Started

### 1. Fork and Clone
```bash
# Fork the repository on GitHub
# Then clone your fork
git clone https://github.com/YOUR_USERNAME/IoT_project.git
cd IoT_project

# Add upstream remote
git remote add upstream https://github.com/mstejas610/IoT_project.git
```

### 2. Set Up Development Environment
```bash
# Follow INSTALLATION.md for complete setup
# Install development dependencies
pip install -r requirements-dev.txt

# Install pre-commit hooks
pre-commit install
```

### 3. Create Feature Branch
```bash
# Create descriptive branch name
git checkout -b feature/edge-node-optimization
# OR
git checkout -b fix/mqtt-connection-timeout
# OR
git checkout -b docs/api-documentation
```

## 📝 Development Guidelines

### Code Style
- **Python**: Follow PEP 8 standards
- **Formatting**: Use `black` for code formatting
- **Imports**: Use `isort` for import organization
- **Type Hints**: Add type annotations for all functions
- **Docstrings**: Use Google-style docstrings

### Example Function Format:
```python
from typing import List, Optional, Dict
import logging

def process_edge_data(
    sensor_data: Dict[str, float], 
    node_id: str,
    threshold: Optional[float] = None
) -> List[Dict[str, any]]:
    """Process sensor data at edge node to reduce latency.
    
    Args:
        sensor_data: Raw sensor readings with timestamps
        node_id: Unique identifier for edge processing node
        threshold: Optional filtering threshold for anomaly detection
        
    Returns:
        List of processed data packets ready for transmission
        
    Raises:
        ValueError: If sensor_data format is invalid
    """
    logger = logging.getLogger(__name__)
    
    try:
        # Implementation here
        processed_data = []
        logger.info(f"Processed {len(sensor_data)} readings on node {node_id}")
        return processed_data
    except Exception as e:
        logger.error(f"Edge processing failed: {e}")
        raise
```

### Testing Requirements
- **Unit Tests**: Required for all new functions
- **Integration Tests**: For MQTT and database interactions
- **Performance Tests**: For latency-critical components
- **Hardware Tests**: When applicable (Raspberry Pi)

### File Organization
```
IoT_project/
├── Code/
│   ├── core/                # Core edge computing logic
│   ├── sensors/             # Sensor interface modules
│   ├── networking/          # MQTT and communication
│   └── utils/               # Utility functions
├── tests/
│   ├── unit/                # Unit tests
│   ├── integration/         # Integration tests
│   └── performance/         # Performance benchmarks
└── docs/                    # Additional documentation
```

## 🔄 Development Workflow

### 1. Before Starting
```bash
# Sync with upstream
git fetch upstream
git checkout main
git merge upstream/main
```

### 2. Make Changes
- Write code following the style guidelines
- Add tests for new functionality
- Update documentation as needed
- Test locally before committing

### 3. Commit Guidelines
Use conventional commit format:
```bash
# Format: type(scope): description
git commit -m "feat(edge): add latency optimization algorithm"
git commit -m "fix(mqtt): resolve connection timeout issues"
git commit -m "docs(api): update sensor interface documentation"
git commit -m "test(core): add unit tests for data processing"
git commit -m "perf(network): optimize MQTT message batching"
```

### Commit Types
- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation
- `test`: Testing
- `refactor`: Code refactoring
- `perf`: Performance improvement
- `chore`: Maintenance tasks

### 4. Testing Before PR
```bash
# Run all tests
python -m pytest tests/

# Check code formatting
black --check Code/
flake8 Code/

# Type checking
mypy Code/

# Run performance benchmarks
python scripts/benchmark.py
```

### 5. Submit Pull Request
- Push to your fork: `git push origin feature/your-feature-name`
- Create PR on GitHub with detailed description
- Reference any related issues
- Include screenshots for UI changes
- Wait for review from team members

## 📊 Performance Considerations

### Latency Requirements
- **Critical operations**: < 10ms response time
- **Standard operations**: < 100ms response time
- **Batch operations**: < 1s processing time

### Memory Usage
- **Edge nodes**: Keep memory usage < 512MB
- **Sensor data**: Use efficient data structures
- **Caching**: Implement LRU cache for frequently accessed data

## 🔒 Security Guidelines

- Never commit sensitive data (API keys, passwords)
- Use environment variables for configuration
- Implement proper authentication for MQTT
- Validate all sensor input data
- Use encrypted communication channels

## 📞 Issue Reporting

### Bug Reports
Include:
- Detailed description
- Steps to reproduce
- Expected vs actual behavior
- System information (OS, Python version)
- Log files (if applicable)
- Hardware setup (if relevant)

### Feature Requests
Include:
- Clear description of the feature
- Use case and benefits
- Proposed implementation approach
- Performance impact considerations

## 🔍 Review Process

1. **Automated checks** must pass (CI/CD)
2. **Code review** by at least one team member
3. **Testing** on development environment
4. **Performance validation** for critical changes
5. **Documentation update** if needed

## 🎆 Recognition

Contributors will be:
- Added to the contributors list
- Mentioned in release notes
- Credited in academic publications (if applicable)

## 📧 Questions?

- Create an issue for discussion
- Contact team members via email
- Join our project Discord server (link in README)

---

*Thank you for contributing to IoT edge computing research! 🚀*