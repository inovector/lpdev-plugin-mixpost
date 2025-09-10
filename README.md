# Mixpost Tools Plugin for lpdev

A development tools plugin for [Mixpost.app](https://mixpost.app) that automatically manages SSL configuration based on your application URL. This plugin integrates with [lpdev](https://github.com/inovector/lpdev) to streamline Mixpost development workflows.

## Features

- **Automatic SSL Configuration**: Intelligently sets `ENABLE_SSL` based on your `APP_URL`
- **Environment Management**: Syncs environment variables between app and package
- **Development-friendly**: Handles local domains (.test, .local, localhost) appropriately
- **Status Monitoring**: Check current SSL configuration status

## Installation

This plugin is designed to work with [lpdev](https://github.com/inovector/lpdev). Install with:

 ```bash
 lpdev plugin install lpdev-plugin-mixpost_tools
 ```

## Usage

### Automatic Configuration

The plugin automatically activates when:
- Setting an `APP_URL` environment variable
- Add APP_URL to the `.env` file of Mixpost package

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

Run command using:

```bash
lpdev plugin mixpost <command>
```

## Requirements

- [lpdev](https://www.npmjs.com/package/lpdev) installed on your system
- Bash shell
- Mixpost project set up

## License

[MIT License](LICENSE.md)