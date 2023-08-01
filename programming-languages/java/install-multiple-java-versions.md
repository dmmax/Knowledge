# Install multiple Java versions

## Preconditions

* you're running on macOS
* [brew](https://brew.sh/) is installed 

## Step 1: Instal JDK(s)
Search for available JDKs
```shell
brew search --formulae openjdk.java
```
install a required version, e.g.
```shell
brew install openjdk@8
brew install openjdk@11
```

## Step 2: Make JDK searchable
For the system, Java wrappers to find this JDK, symlink it with. 
Instead of `openjdk@8` use your version.
```shell
sudo ln -sfn /usr/local/opt/openjdk@8/libexec/openjdk.jdk /Library/Java/JavaVirtualMachines/openjdk-8.jdk
```

## Step 3: Add Java paths to environment variables

Add to the end of your file which is used to be running by default when the shell session is started. 
E.g. to the `~/.bashrc` or `~/.zshrc`

```shell
# Defining Java home
export JAVA_8_HOME=$(/usr/libexec/java_home -v1.8)
export JAVA_11_HOME=$(/usr/libexec/java_home -v11)
export JAVA_17_HOME=$(/usr/libexec/java_home -v17)

alias java8='export JAVA_HOME=$JAVA_8_HOME'
alias java11='export JAVA_HOME=$JAVA_11_HOME'
alias java17='export JAVA_HOME=$JAVA_17_HOME'

#default java17
export JAVA_HOME=$JAVA_17_HOME
```

## Step 4: Conclusion and example of usage

Now by default, you will have Java 17 available
```shell
java --version
openjdk 17.0.8 2023-07-18
OpenJDK Runtime Environment Homebrew (build 17.0.8+0)
OpenJDK 64-Bit Server VM Homebrew (build 17.0.8+0, mixed mode, sharing)
```

and to switch to other versions, you can simply call `java8` or `java11`

```shell
java11
java --version
openjdk 11.0.20 2023-07-18
OpenJDK Runtime Environment Homebrew (build 11.0.20+0)
OpenJDK 64-Bit Server VM Homebrew (build 11.0.20+0, mixed mode)
```

## Links
* [Stackoverflow: Mac OS X and multiple Java versions](https://stackoverflow.com/questions/26252591/mac-os-x-and-multiple-java-versions)
* [Medium: Installing & switching between multiple JDK on macOS](https://medium.com/@manvendrapsingh/installing-many-jdk-versions-on-macos-dfc177bc8c2b)
