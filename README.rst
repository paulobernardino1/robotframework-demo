# 🤖 Robot Framework + SeleniumLibrary
## Simple and Efficient Web Test Automation

Robot Framework is a generic open source test automation framework and SeleniumLibrary is one of the many test libraries that can be utilized with it. This demo demonstrates how they can be employed together for web testing, presenting the basic Robot Framework test data syntax, test execution, and log/report generation.

---

## 📋 Overview

This project showcases how to use **Robot Framework** together with **SeleniumLibrary** to automate web application testing. Robot Framework is a generic open source test automation framework, while SeleniumLibrary is one of its many specialized libraries.

### ✨ What you'll find here:
- 🎯 Basic Robot Framework syntax
- 🚀 Practical test execution
- 📊 Log and report generation
- 🌐 Testing across different browsers

---

## 📦 Obtaining the Demo Package

### Option 1: Direct Download
```bash
# Download repository
https://github.com/robotframework/WebDemo/archive/master.zip
```

### Option 2: Clone via Git
```bash
# Clone repository
git clone https://github.com/robotframework/WebDemo.git
```

🗂️ **Project structure:**
```
WebDemo/
├── demoapp/          # Demo application
└── login_tests/      # Test cases
```

> 💡 **Tip:** You can view [sample test cases](https://github.com/robotframework/WebDemo/tree/master/login_tests) and [generated results](http://robotframework.org/WebDemo/report.html) online without downloading the project.

---

## 🎯 Demo Application

The demo application is a very simple login page:

- ✅ **Valid login:** username `demo` + password `mode` → welcome page
- ❌ **Invalid login:** any other combination → error page

The application needs to be running while executing automated tests.

---

## 🧪 Test Cases

All test files are located in the `login_tests/` directory:

### 📄 Test Files

| File | Description |
|------|-------------|
| **[valid_login.robot](https://github.com/robotframework/WebDemo/blob/master/login_tests/valid_login.robot)** | 🟢 Test suite with a single test for valid login using keywords from resource file |
| **[invalid_login.robot](https://github.com/robotframework/WebDemo/blob/master/login_tests/invalid_login.robot)** | 🔴 Data-driven test suite for invalid login scenarios using Test Template |
| **[gherkin_login.robot](https://github.com/robotframework/WebDemo/blob/master/login_tests/gherkin_login.robot)** | 🥒 Gherkin-style test (Given-When-Then) functionally identical to valid_login.robot |
| **[resource.robot](https://github.com/robotframework/WebDemo/blob/master/login_tests/resource.robot)** | 🔧 Resource file with reusable keywords and variables creating domain-specific language |

The system-specific keywords in the resource file form our own domain-specific language, utilizing keywords provided by the imported SeleniumLibrary.

---

## 📊 Generated Results

After test execution, you obtain HTML format reports and logs:

- 📈 **[report.html](http://robotframework.org/WebDemo/report.html)** - Executive test summary
- 📝 **[log.html](http://robotframework.org/WebDemo/log.html)** - Detailed execution log

---

## 🚀 Executing the Demo

### 📋 Prerequisites

Make sure you have installed:
- 🐍 **Python** 3.6+
- 🤖 **Robot Framework**
- 🌐 **SeleniumLibrary**

### ⚡ Quick Installation

```bash
# Install all dependencies
pip install -r requirements.txt
```

For detailed installation instructions, see:
- [Robot Framework installation instructions](https://github.com/robotframework/robotframework/blob/master/INSTALL.rst)
- [SeleniumLibrary installation instructions](https://github.com/robotframework/SeleniumLibrary#installation)

### 🖥️ Launching Demo Application

#### Method 1: Double-click
Navigate to `demoapp/server.py` and execute

#### Method 2: Command line
```bash
python demoapp/server.py
```

🌐 **Application will be available at:** `http://localhost:7272`

**Test credentials:** `demo` / `mode`

**To terminate:**
- If launched by double-clicking: close the window
- If launched from command line: use `Ctrl-C`

### 🎮 Executing Tests

#### Run entire test suite:
```bash
robot login_tests
```

#### Run specific test file:
```bash
robot login_tests/valid_login.robot
```

#### Run specific test with debug logging:
```bash
robot --test InvalidUserName --loglevel DEBUG login_tests
```

#### Get complete help:
```bash
robot --help
```

> **Note:** If using Robot Framework 2.9 or earlier, use `pybot` command instead of `robot`.

---

## 🌐 Testing with Different Browsers

The browser is controlled by the `${BROWSER}` variable defined in `resource.robot`. 

**Firefox** is the default, but you can easily override it:

```bash
# Google Chrome
robot --variable BROWSER:Chrome login_tests

# Internet Explorer
robot --variable BROWSER:IE login_tests

# Microsoft Edge
robot --variable BROWSER:Edge login_tests
```

Consult [SeleniumLibrary documentation](https://github.com/robotframework/SeleniumLibrary) for all supported browsers.

---

## 📚 Additional Resources

- 📖 **[Robot Framework User Guide](http://robotframework.org/robotframework/#user-guide)** - Complete documentation
- 🔍 **[SeleniumLibrary Docs](https://github.com/robotframework/SeleniumLibrary)** - Supported browsers and features
- 🏠 **[Robot Framework](http://robotframework.org)** - Official website
- 📦 **[pip](http://pip-installer.org)** - Package manager

---

## 💡 Next Steps

1. 🔧 Run the demo locally
2. 📝 Analyze existing test cases
3. 🎨 Create your own tests
4. 🚀 Integrate with your CI/CD pipeline

---

<div align="center">

**Made with ❤️ using Robot Framework**

[⭐ Star on GitHub](https://github.com/robotframework/WebDemo) | [📖 Documentation](http://robotframework.org/robotframework/#user-guide) | [🐛 Report Issues](https://github.com/robotframework/WebDemo/issues)

</div>
