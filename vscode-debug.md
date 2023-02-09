# launch.json

### ts-node debug
```js
{
     // Use IntelliSense to learn about possible attributes.
     // Hover to view descriptions of existing attributes.
     // For more information, visit: https://go.microsoft.com/fwlink/?linkid=830387
     "version": "0.2.0",
     "configurations": [
          {
               "type": "node",
               "request": "launch",
               "name": "Launch Program",
               "skipFiles": [
                    "<node_internals>/**"
               ],
               "args": [
                    "${workspaceRoot}/src/cli.ts"
               ],
               "runtimeArgs": [
                    "--nolazy",
                    "-r",
                    "ts-node/register"
               ],
               "cwd": "${workspaceRoot}/src",
               "sourceMaps": true,
               "protocol": "inspector",
               "console": "integratedTerminal",
               "internalConsoleOptions": "neverOpen"
          }
     ]
}
```
