# colr: Colorful Logging for Go

[![Go Report Card](https://goreportcard.com/badge/github.com/theritikchoure/colr)](https://goreportcard.com/report/github.com/theritikchoure/colr)
[![License](https://img.shields.io/badge/License-MIT-blue.svg)](https://github.com/theritikchoure/colr/blob/main/LICENSE)
[![GitHub Release](https://img.shields.io/github/v/release/theritikchoure/colr)](https://github.com/theritikchoure/colr/releases)
[![Build Status](https://travis-ci.org/theritikchoure/colr.svg?branch=main)](https://travis-ci.org/theritikchoure/colr)
[![GoDoc](https://pkg.go.dev/badge/github.com/theritikchoure/colr)](https://pkg.go.dev/github.com/theritikchoure/colr)
[![Coverage Status](https://coveralls.io/repos/github/theritikchoure/colr/badge.svg?branch=main)](https://coveralls.io/github/theritikchoure/colr?branch=main)


`colr` is a Go package that allows you to add color and formatting to your console log messages, making it easier to distinguish different types of log entries or to add emphasis to specific messages. It provides a simple way to enhance your application's log output.

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
  - [Enabling or Disabling Color](#enabling-or-disabling-color)
  - [Log](#log)
  - [Logf](#logf)
  - [LogWithLevel](#logwithlevel)
  - [LogM](#logm)
  - [LogWithTimestamp](#logwithtimestamp)
  - [LogToFile](#logtofile)
- [Contributing](#contributing)
- [License](#license)

## Installation

To use `colr`, you need to import it in your Go code:

```go
import "github.com/theritikchoure/colr"
```

Then, install it with `go get`:

```go
go get github.com/theritikchoure/colr
```

## Usage

### Enabling or Disabling Color
By default, colorized logging is disabled. You can enable or disable it by modifying the `ColoringEnabled` variable in your code. Setting it to `true` will enable colored output, and setting it to `false` will disable it.

```go
colr.ColoringEnabled = true // Enable colorized logging
colr.ColoringEnabled = false // Disable colorized logging (default)
```

### Log
The `Log` function allows you to print log messages with specified foreground and background colors. If coloring is disabled, it will print plain text.

```go
colr.Log("This is a log message", colr.FGRED, colr.BGGREEN)
```

### Logf
Use `Logf` to format log messages and specify colors. It is similar to `fmt.Printf`.

```go
colr.Logf("User: %s logged in.", colr.FGBLUE, colr.BGWHITE, "JohnDoe")
```

### LogWithLevel
`LogWithLevel` is helpful for displaying log messages with predefined background colors corresponding to log levels such as INFO, WARNING, ERROR, and SUCCESS.

```go
colr.LogWithLevel("An error occurred", "ERROR")
```

### LogM
With `LogM`, you can log multiple messages with customized formatting options.

```go
colr.LogM([]string{"Applying", "updates..."}, colr.FGBLUE, colr.BGYELLOW, colr.BOLD, colr.UNDERLINE)
```

### LogWithTimestamp
`LogWithTimestamp` adds a timestamp to your log message. It's particularly useful for recording when an event occurred.
```go
colr.LogWithTimestamp("System restarted", colr.FGCYAN, colr.BGWHITE)
```

### LogToFile
`LogToFile` logs messages to a file in addition to standard output.

```go
colr.LogToFile("Log entry written to file", colr.FGRED, colr.BGGREEN, "log.txt")
```

## Contributing
We welcome contributions from the community! If you'd like to contribute to colr, follow these steps:

1. Fork the repository.
2. Create a new branch for your feature or bug fix.
3. Make your changes and add tests if applicable.
4. Run tests and ensure they pass.
5. Submit a pull request with a clear description of your changes.

We appreciate your help in improving colr.

## License
This project is licensed under the MIT License. See the [LICENSE](https://github.com/theritikchoure/colr/blob/main/LICENSE) file for details.