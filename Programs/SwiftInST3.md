##Adding Swift Build System

- Open Sublime Text 3
- Go To `Preferences > Browse Packages...`
- Add a file named `Swift.sublime-build` inside `Packages` directory.
- Copy the following script in `Swift.sublime-build` file.

```
{
 	"shell_cmd": "xcrun swift $file",
 	"file_regex": "^(..[^:]*):([0-9]+):?([0-9]+)?:? (.*)$",
 	"working_dir": "${file_path}",
 	"selector": "source.swift",
}
```
- Go to `Preferences > Key Bindings-User` and add the following script to it.

```
{
	"keys": ["super+b"], 
	"command": "build",
	"context": [
		{ "key": "selector", "operator": "equal", "operand": "source.swift" }
	], 
	"args": {
		"build_system": "Packages/Swift.sublime-build",
		"variant": "Build"
	}
}
```
> You are ready to run Swift scripts from ST3 now.


##Testing the Swift Build System

- Create a file `A.swift` containing a single line `println("Hello, Swift!")`.
- Press `command + b` and you'll be able to see the output.
- If you are unable to see the output, go to `Tools > Build Systems` and change it from `Automatic` to `Swift`, and you should be able to run Swift in ST3.