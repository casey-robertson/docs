## pulumi plugin ls

List plugins

### Synopsis


List plugins

```
pulumi plugin ls [flags]
```

### Options

```
  -h, --help      help for ls
  -p, --project   List only the plugins used by the current project
```

### Options inherited from parent commands

```
  -C, --cwd string                   Run pulumi as if it had been started in another directory
      --disable-integrity-checking   Disable integrity checking of checkpoint files
  -e, --emoji                        Enable emojis in the output (default true)
      --logflow                      Flow log settings to child processes (like plugins)
      --logtostderr                  Log to stderr instead of to files
      --profiling string             Emit CPU and memory profiles and an execution trace to '[filename].[pid].{cpu,mem,trace}', respectively
      --tracing string               Emit tracing to a Zipkin-compatible tracing endpoint
  -v, --verbose int                  Enable verbose logging (e.g., v=3); anything >3 is very verbose
```

### SEE ALSO
* [pulumi plugin](pulumi_plugin.md)	 - Manage language and resource provider plugins

###### Auto generated by spf13/cobra on 11-May-2018