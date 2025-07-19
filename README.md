# Renovate Config 🔄

[![Validate renovate config](https://github.com/a11ylint/renovate-config/actions/workflows/validate-config.yml/badge.svg)](https://github.com/a11ylint/renovate-config/actions/workflows/validate-config.yml)
[![GitHub License](https://img.shields.io/github/license/a11ylint/renovate-config)](https://github.com/a11ylint/renovate-config?tab=MIT-1-ov-file#readme)

Shared Renovate configuration for **a11ylint** organization projects. 🛠️

This repository contains ready-to-use Renovate configurations to automate dependency updates management across our projects.

## Available Configurations 📋

### Default Configuration (`default`) ⚙️

The main configuration that combines all best practices:

```json
{
  "$schema": "https://docs.renovatebot.com/renovate-schema.json",
  "extends": ["github>a11ylint/renovate-config"]
}
```

**Features:**

- 🏗️ **Base config**: Uses Renovate's recommended configuration
- 🌍 **Timezone**: Europe/Paris
- 🔒 **Security alerts**: Enabled with "security" label
- 🏷️ **Labels**: PRs are labeled with "dependencies"
- ⚡ **Limits**: Maximum 2 concurrent PRs, maximum 2 PRs per hour
- 🚨 **Major updates**: Labeled "High" for easy prioritization
- 📊 **Dashboard**: Disabled to reduce noise

### NPM Configuration (`npm`) 📦

Specialized configuration for Node.js projects:

```json
{
  "$schema": "https://docs.renovatebot.com/renovate-schema.json",
  "extends": ["github>a11ylint/renovate-config:npm"]
}
```

**Features:**

- 📈 **Versioning strategy**: "bump" (increments version)
- ⏰ **Minimum age**: 3 days before update (stability)
- 🚫 **Node.js engines**: Updates disabled
- 🚫 **PeerDependencies**: Updates disabled

### GitHub Actions Configuration (`github-action`) 🎬

Configuration for GitHub Actions workflows:

```json
{
  "$schema": "https://docs.renovatebot.com/renovate-schema.json",
  "extends": ["github>a11ylint/renovate-config:github-action"]
}
```

**Features:**

- 📌 **Digest pinning**: Enabled for maximum actions security

### Onboarding Configuration (`onboarding`) 🚀

Configuration for initial Renovate integration:

```json
{
  "$schema": "https://docs.renovatebot.com/renovate-schema.json",
  "extends": ["github>a11ylint/renovate-config:onboarding"]
}
```

**Features:**

- ✅ **Onboarding enabled**: Automatic config file creation
- 📁 **Config file**: `.github/renovate.json`
- 💬 **Commit message**: "chore: configure renovate"
- 🔧 **Default config**: Automatically uses our shared config

## Usage 🚀

### Complete Configuration (Recommended) ⭐

For most projects, use the default configuration that includes all best practices:

```json
{
  "$schema": "https://docs.renovatebot.com/renovate-schema.json",
  "extends": ["github>a11ylint/renovate-config"]
}
```

### Modular Configuration 🧩

You can combine multiple configurations based on your needs:

```json
{
  "$schema": "https://docs.renovatebot.com/renovate-schema.json",
  "extends": [
    "config:recommended",
    "github>a11ylint/renovate-config:npm",
    "github>a11ylint/renovate-config:github-action"
  ]
}
```

### Customization 🎨

You can override certain parameters by adding your own rules:

```json
{
  "$schema": "https://docs.renovatebot.com/renovate-schema.json",
  "extends": ["github>a11ylint/renovate-config"],
  "schedule": ["before 4am on monday"],
  "prConcurrentLimit": 5
}
```

## Initial Setup 🏁

1. ✅ **Enable Renovate** on your GitHub repository
2. 📝 **Create the file** `.github/renovate.json` with your desired configuration
3. 🔄 **Commit the file** - Renovate will start analyzing your project

If you use the onboarding configuration, Renovate will automatically create the configuration file on its first run.

## Development 👨‍💻

### Configuration Validation ✅

```bash
npm run validate
```

### Code Formatting 🎨

```bash
npm run lint:fix
```

### Format Checking 🔍

```bash
npm run lint
```

## Contributing 🤝

Contributions are welcome! Please see the [CONTRIBUTING.md](CONTRIBUTING.md) file for more information.

## License 📄

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
