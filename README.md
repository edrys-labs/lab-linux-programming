# Lab-Linux: Programming

Laboratory configuration for sharing the linux terminal with multiple preinstalled compilers.
By combining the terminal with an editor, the user can write, compile, and run the code in the same environment.

__Used Modules:__

- [module-editor](https://github.com/edrys-labs/module-editor): Simple minimal and configurable code editor.
- [module-markdown-it](https://github.com/edrys-labs/module-markdown-it): Markdown viewer used for documentation. 
- [module-pyxtermjs](https://github.com/edrys-labs/module-pyxtermjs): Terminal Server, this requires a running local server to be able to run the code.

After importing one of the predefined configuration listed below, you have to open a station and start the pyxtermjs server, running on localhost.

The easiest way to do this, is by installing docker and running the following command:

```bash
docker run -it -p 5000:5000 crosslab/edrys_pyxtermjs_development:latest
```

This will download the pyxtermjs terminal-server from docker-hub and run it in a secure environment.

Otherwise, you can install the server locally by following the instructions in the [module-pyxtermjs](https://github.com/edrys-labs/module-pyxtermjs).

### C Programming with `gcc`


[`https://raw.githubusercontent.com/edrys-labs/lab-linux/main/laboratory/c.yaml`](https://raw.githubusercontent.com/edrys-labs/lab-linux/main/laboratory/c.yaml)

[`https://raw.githubusercontent.com/edrys-labs/lab-linux/main/laboratory/c.json`](https://raw.githubusercontent.com/edrys-labs/lab-linux/main/laboratory/c.json)

## C++ Programming with `g++`

[`https://raw.githubusercontent.com/edrys-labs/lab-linux/main/laboratory/cpp.yaml`](https://raw.githubusercontent.com/edrys-labs/lab-linux/main/laboratory/cpp.yaml)

[`https://raw.githubusercontent.com/edrys-labs/lab-linux/main/laboratory/cpp.json`](https://raw.githubusercontent.com/edrys-labs/lab-linux/main/laboratory/cpp.json)

## Haskell Programming with `ghc`

[`https://raw.githubusercontent.com/edrys-labs/lab-linux/main/laboratory/haskell.yaml`](https://raw.githubusercontent.com/edrys-labs/lab-linux/main/laboratory/haskell.yaml)

[`https://raw.githubusercontent.com/edrys-labs/lab-linux/main/laboratory/haskell.json`](https://raw.githubusercontent.com/edrys-labs/lab-linux/main/laboratory/haskell.json)


### Java Programming with `javac`

[`https://raw.githubusercontent.com/edrys-labs/lab-linux/main/laboratory/java.yaml`](https://raw.githubusercontent.com/edrys-labs/lab-linux/main/laboratory/java.yaml)

[`https://raw.githubusercontent.com/edrys-labs/lab-linux/main/laboratory/java.json`](https://raw.githubusercontent.com/edrys-labs/lab-linux/main/laboratory/java.json)


### Lua Programming with `lua`

[`https://raw.githubusercontent.com/edrys-labs/lab-linux/main/laboratory/lua.yaml`](https://raw.githubusercontent.com/edrys-labs/lab-linux/main/laboratory/lua.yaml)

[`https://raw.githubusercontent.com/edrys-labs/lab-linux/main/laboratory/lua.json`](https://raw.githubusercontent.com/edrys-labs/lab-linux/main/laboratory/lua.json)

### Python Programming with `python`

[`https://raw.githubusercontent.com/edrys-labs/lab-linux/main/laboratory/python.yaml`](https://raw.githubusercontent.com/edrys-labs/lab-linux/main/laboratory/python.yaml)

[`https://raw.githubusercontent.com/edrys-labs/lab-linux/main/laboratory/python.json`](https://raw.githubusercontent.com/edrys-labs/lab-linux/main/laboratory/python.json)


## Additional Programming Languages

There is currently also support for the following programming languages:

- `clojure`
- `g++`
- `golang`
- `mono`
- `nodejs`
- `r`
- `rustc`

You can either install other languages on your local machine or extend the dockerfile from:

https://github.com/edrys-labs/module-pyxtermjs/blob/master/docker/development/Dockerfile

You will have to update the `script` entry in the classroom configuration to match your build/compile steps.

``` yaml
- url: https://edrys-labs.github.io/module-pyxtermjs/index.html
    config: ''
    studentConfig: ''
    teacherConfig: ''
    stationConfig:
      server: http://localhost:5000/pty
      execute: execute
      script: |-
        echo $CODE | base64 --decode > main.py
        python3 main.py
      enable:
        teacher: true
        student: true
    showInCustom: station
    width: full
    height: medium
```

that's it ... happy coding! 🚀
