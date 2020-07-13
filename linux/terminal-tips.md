# Terminal Tips

**Text search in files**

```bash
$ grep -rnI {word} {directory}

# Examples
$ grep -rnI origin .
$ grep -rnI foo apps/bar/
```

**Open a text editor on a particular line**

```bash
$ vim {file} +{line}

# Examples
# Can be used in other text editors.
$ vim arquivo.py +136
```

**Execute a process in the background.**

```bash
$ {process} &

# Example
$ ./start.sh &
```

**Run background processes resistant to hangup signals**

If we only use &, when we disconnect from the terminal a hangup signal is sent, stopping all processes bound to it.

```bash
$ nohup {./process} &

# Example
$ nohup python script.py >> output.txt 2 >> error.txt &
```

Logs \(outputs and errors\) are generated automatically and we can manipulate their respective directories as in the example. When we use “&gt;” the log file is replaced every time a new log is issued when we use “&gt;&gt;” when a new log is issued it is saved to the end of the file, like an append.

**Make one command be processed by another \(pipe connection\)**

```bash
$ {first_command} | {second_command}

# Example
# Displays processes that contain the word python
$ ps aux | grep python
```

**Command chaining**

When we use `&&` the `second_command` is only executed if `first_command` was executed successfully.

```bash
{first_command} && {second_command}
{first_command} ; {second_command}
```

**Creating custom shortcuts**

```bash
$ alias {shortcut_name}="{command}"

# Example
$ alias migrate="python manage.py migrate"
$ migrate
Operations to perform:
  Apply all migrations: ...
```

**Keyboard shortcuts**

`control+A`: Go to the beginning of the line.

`control+E`: Go to the end of the line.

`control+D`: Deletes the selected character.

`control+W`: Cut the word before the cursor.

`control+U`: Cut the line before the cursor.

`control+Y`: Paste the last things cut out.

`control+R`: Search in command history.

`tab`: Autocomplete

