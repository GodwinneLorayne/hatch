# Custom environment

-----

This is a custom class in a given Python file that inherits from the [EnvironmentInterface](reference.md#hatch.env.plugin.interface.EnvironmentInterface).

## Configuration

The environment collector plugin name is `custom`.

```toml config-example
[tool.hatch.env.default]
type = "custom"
```

## Options

| Option | Default | Description |
| --- | --- | --- |
| `path` | `hatch_plugins.py` | The path of the Python file |

## Example

```python tab="hatch_plugins.py"
    from hatch.env.plugin.interface import EnvironmentInterface


    class CustomEnvironment(EnvironmentInterface):
        ...
```

If multiple subclasses are found, you must define a function named `get_environment` that returns the desired environment.

!!! note
    Any defined [PLUGIN_NAME](reference.md#hatch.env.plugin.interface.EnvironmentInterface.PLUGIN_NAME) is ignored and will always be `custom`.
