# Mixpost Plugin for lpdev

A development tools plugin for [Mixpost.app](https://mixpost.app) that automatically manages SSL configuration based on your application URL.

## Features

- **Automatic SSL Configuration**: Intelligently sets `ENABLE_SSL` based on your `APP_URL`
- **Environment Management**: Syncs environment variables between app and package
- **Development-friendly**: Handles local domains (.test, .local, localhost) appropriately
- **Status Monitoring**: Check current SSL configuration status

## Installation

This plugin is designed to work with lpdev. Install with:

 ```bash
 lpdev plugin install lpdev-plugin-mixpost
 ```

## Usage

### Automatic Configuration

The plugin automatically activates when:
- Setting an `APP_URL` environment variable
- Adding a new project with a URL

### Manual Commands

Check SSL configuration status:
```bash
lpdev plugin mixpost enable-ssl-status
```

Show help:
```bash
lpdev plugin mixpost help
```

## SSL Configuration Logic

The plugin automatically sets `ENABLE_SSL` based on your `APP_URL`:

- **Local domains** (`.test`, `.local`): Sets `ENABLE_SSL=null`
- **Localhost** (`localhost`, `127.0.0.1`, `::1`): Sets `ENABLE_SSL=null`  
- **Remote domains**: Sets `ENABLE_SSL=false`

## Hooks

This plugin responds to the following lpdev hooks:

- `on_env_set`: Triggered when environment variables are modified
- `on_project_add`: Triggered when new projects are added

## Commands

| Command | Description |
|---------|-------------|
| `enable-ssl-status` | Display current SSL configuration status |
| `help` | Show plugin usage information |

## Requirements

- lpdev development environment
- Bash shell
- Mixpost.app project structure

## Author

**Dima Botezatu**  
Email: dima@inovector.com

## License

MIT License - see LICENSE file for details.

## Repository

[https://github.com/inovector/lpdev-plugin-mixpost.git](https://github.com/inovector/lpdev-plugin-mixpost-ssl.git)