---
sidebar_position: 2
---

# Setup Development Environment

### Description

To begin, we should ensure that we've set up an IDE (Integrated Development Environment) to develop with.

### VSCode

The IDE that I will use is VSCode. If you also use VSCode then what you will see, will more closely match what I show in the videos.

If you don't have VSCode already installed, then you can install it from https://code.visualstudio.com.

Also, it is useful, but not essential, to be able to start VSCode from the command line.

We can check it is available from the command line by typing

```
code -v
```

The response should indicate a version number, plus several other bits of information.

### Node.js

We also need Node.js, which includes NPM, since we will be using the npm and npx commands.

To check if Node.js is already installed, open a cmd/terminal/shell prompt and type,

```
node -v
```

You should get a response indicating a version number.

E.g.,

```
v18.14.0
```

Your version should be equal to or higher than v18.0.0.

We can also check the version of NPM,

```
npm -v
```

You want to see no error, but instead a version number equal to, or higher than v8.0.0.

E.g.,

```
9.8.1
```

If either of those two commands returned an error indicating that they were unrecognized, or the versions numbers were lower than required, then you can install the latest LTS (long term support) version of Node.js from https://nodejs.org/en/

Git
You may also want to use Git, but it is not essential yet.

You can check if Git is already installed. It usually is, by default on Linux and macOS.

```
git --version
```

You want to see a version number higher than 2.0.0, and no error indicating that the command was unrecognized.

You can install Git for Windows from https://gitforwindows.org.

If you are using macOS or Linux, then visit https://git-scm.com/downloads.

### Troubleshooting

Error : ENOENT: no such file or directory, lstat
When running npx commands, you may get an error stating that it cannot find lstat.

Open a command/bash/powershell prompt and run

```
npm install -g npm
```
