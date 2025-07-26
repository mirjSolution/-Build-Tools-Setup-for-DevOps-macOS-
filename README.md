# 🛠️ Build Tools Setup for DevOps (macOS)

This guide outlines the installation and setup of essential **build tools** and editors required for working with **Java** and **JavaScript** applications as part of your DevOps workflow.

---

## 🚀 Tools Overview

### Code Editor

- **IntelliJ IDEA (Community Edition)** – Powerful IDE for Java, JavaScript, and more.

### Package Manager

- **Homebrew** – macOS package manager for installing tools efficiently.

### Java Build Tools

- **Java (OpenJDK 17)** – Required runtime and development kit for Java applications.
- **Maven** – Java build tool for dependency management and creating artifacts (JAR/WAR).
- **Gradle** – Alternative build tool offering flexible configuration and faster builds.

### JavaScript Build Tools

- **Node.js** – JavaScript runtime for building scalable applications.
- **NPM** – Package manager for JavaScript dependencies.

---

## 💻 Installation Steps (macOS)

![IntelliJ IDEA](Images/intellij.gif)

1. **Install IntelliJ IDEA**

- Update your system

```bash
sudo apt update && sudo apt upgrade -y
```

- Install Snapd (if not already installed)
  - Snap is a package manager that makes it easy to install software like IntelliJ on Ubuntu.

```bash
sudo apt install snapd -y
```

- Install IntelliJ IDEA Community Edition
  - Use Snap to install IntelliJ IDEA Community Edition.

```bash
sudo snap install intellij-idea-community --classic
```

- After installation, launch IntelliJ from the application menu or by typing the following command in the terminal:

```bash
intellij-idea-community
```

2. **Install Homebrew**

![Brew](Images/brew.gif)

```bash
sudo apt install build-essential curl file git -y
```

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

3. **Install Git**

```bash
brew install git
```

![Git install](Images/installgit.png)

**_note!!!_** if you received error "command not found"

- Add Homebrew to zsh Profile

```bash
echo 'eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"' >> ~/.zshrc
source ~/.zshrc
```

![Brew Error](Images/brewnotfound1.png)

4. **Install Java (OpenJDK 17)**

```bash
brew install openjdk@17
```

![InstallJDK](Images/installjdk.png)

Add Java to zsh Profile

```bash
echo 'export PATH="/home/linuxbrew/.linuxbrew/opt/openjdk@17/bin:$PATH"' >> ~/.zshrc
echo 'export JAVA_HOME="/home/linuxbrew/.linuxbrew/opt/openjdk@17"' >> ~/.zshrc
source ~/.zshrc
```

Verify java works

```bash
java --version
```

![Java](Images/Java.png)

5. **Install Maven**

```bash
brew install --ignore-dependencies maven
```

Add maven to PATH

```bash
echo 'export PATH="/home/linuxbrew/.linuxbrew/opt/maven/bin:$PATH"' >> ~/.zshrc
echo 'export MAVEN_HOME="/home/linuxbrew/.linuxbrew/opt/maven"' >> ~/.zshrc
source ~/.zshrc
```

Verify maven working

```bash
mvn --version
```

![Maven](Images/maven.png)

6. **Install Gradle**

```bash
brew install gradle
```

![Gradle](Images/gradle.png)

Add gradle to PATH

```bash
echo 'export PATH="/home/linuxbrew/.linuxbrew/opt/gradle/bin:$PATH"' >> ~/.zshrc
source ~/.zshrc
```

Verify gradle is working

```bash
gradle --version
```

![verify gradle](Images/verifygradle.png)

7. **Install Node.js and NPM**

```bash
brew install node
```

---

## ✅ Project Setup in IntelliJ

- Open cloned projects in IntelliJ.
- IntelliJ will auto-detect Maven/Gradle and download dependencies.
- Configure Java SDK under `File > Project Structure`.
- Run and build projects using IDE or terminal:
  - **Maven Build**: `mvn package`
  - **Gradle Build**: `gradle build`
  - **Node App Start**: `npm start` (inside project folder)

---

## 🧉 Key Takeaway

Understanding and setting up build tools is **essential for DevOps engineers** to package applications, manage dependencies, and support CI/CD workflows.

---

🧑‍💻 _Created by Rico John Dato-on_
🔗 [LinkedIn](https://www.linkedin.com/in/rico-john-dato-on) • [Portfolio](https://ricodatoon.netlify.app)
