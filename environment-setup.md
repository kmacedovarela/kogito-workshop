# 2. Environment Setup

In this step you will prepare the environment that you wil use throughout the rest of the modules. You will:

-   Create a base folder to be used during the enablement labs;
-   Install Visual Studio Code IDE;
    -   Configure VScode command line tools;
    -   Install VSCode Language Support for Java;
    -   Install Red Hat Business Automation Bundle in VSCode;
-   Install GraalVM *(Optional)*;

## 2.1. Creating the base folder for the labs

In these labs, the commands will consider the directory `~/enablement ` as the base directory to clone GitHub repos or create new projects. 

1. To create a new folder named `enablement` using your terminal you can use the following command (Linux/OSX):

   ```
   $ mkdir ~/enablement && cd ~/enablement
   ```

## 2.2. Installing Visual Studio Code IDE

To install Visual Studio Code, navigate to the [VSCode website](https://code.visualstudio.com/), and click the blue *Download* button to download the IDE for your operating system.

![]({%  image_path/vscode-download-page.png %}){:width="600px"}

Follow the standard installation instructions.

*TIP: If you do not want to get automatic updates, you can set the Update: Mode setting from default to none . To modify the update mode, go to File &gt; Preferences &gt; Settings (macOS: Code &gt; Preferences &gt; Settings), search for update mode and change the setting to none.*

### 2.2.1. Configuring VSCode to run via Command Line

This step will allow you to start VSCode using your terminal using the command `code`. 

Open VSCode, and look for the `Command Pallet` option (it can also be opened pressing ctrl+shift+p or cmd+shift+p):

![VSCode Command Pallet]({%  image_path/vscode-command-pallet.png %}){:width="600px"}

Type `code` and select the option `Shell Command: install 'code' command in PATH`:

![VSCode Install Code Command]({%  image_path/vscode-install-code-cmd.png %}){:width="600px"}

When you click the option above, VSCode will configure your operational system so that you can run the `code` command in your terminal to open VSCode.

### 2.2.2. Installing VSCode Plugins 

It is possible to install plugins in VScode in two different ways: 

* by searching in the VSCode Marketplace website and installing it from there, or
* by opening the extensions in the VSCode IDE, searching and installing it. 

We need to install two extensions to work the labs: **Language Support for Java by Red Hat** and **Red Hat Business Automation Bundle**. 

Choose one of the two alternatives below and install both extensions.

#### 2.2.2.1. Option 1: Installing via VSCode Marketplace

In VSCode marketplace, you can find the plugins at: 

* [Java Support by Red Hat](https://marketplace.visualstudio.com/items?itemName=redhat.java) 
* [Red Hat Business Automation Bundle](https://marketplace.visualstudio.com/items?itemName=redhat.vscode-extension-red-hat-business-automation-bundle)

Open the page for each extension and click the green install button on each of the extensions to install it.

#### 2.2.2.2. Option 2: Installing directly through VSCode 

It is also possible to install the plugin directly from within VSCode. Navigate to *Preferences → Extensions*.

![VSCode Preferences Extensions]({%  image_path/vscode-preferences-extensions.png %}){:width="600px"}

In the search box, search for *language support for java*. The Red Hat extension should be on the top of the list. Select the extension and click on the *Install* button. 

![VSCode Red Hat Java Extension]({%  image_path/vscode-redhat-java-extension.png %}){:width="600px"}

In the search box, search for *Business Automation Bundle*, and select it. Click the install button.

![VSCode Red Hat Business Automation Bundle Extension]({%  image_path/vscode-redhat-business-automation-extension.png %}){:width="600px"}

Your IDE is now ready to start working with Kogito applications.

### 2.3. Install GraalVM ( *Optional* )

GraalVM is a Java VM and JDK based on HotSpot/OpenJDK, implemented in Java. It supports additional programming languages and execution modes, like ahead-of-time compilation of Java applications for fast startup and low memory footprint.

Most of the exercises in our Kogito lab can be done on OpenJDK or Oracle Hotspot. Although if you want to try compiling the application into a *native executable*,  you will need GraalVM.

Download GraalVM Community 20.1.0 Java 11 (`graalvm-ce-java11`) from [the following website](https://www.graalvm.org/downloads/) for your operating system, and follow the [installation instructions](https://www.graalvm.org/docs/getting-started/#install-graalvm) for your operating system.

You don’t need the `ruby`, `r`, `python` and `wasm` packages. You only need the `native-image` package.

Getting Started with GraalVM:

-   MacOS: <https://www.graalvm.org/docs/getting-started/macos>

-   Linux: <https://www.graalvm.org/docs/getting-started/linux>

-   Windows: <https://www.graalvm.org/docs/getting-started/windows>

If you find any "permission denied" errors while running the `setx` command, try opening your terminal (command line) as an admin user by right clicking the command shell icon, and selecting `run as administrator`.

If running on Windows, make sure GraalVM is the last Java configured on your PATH environment variable

# Congratulations!

We’ve setup the environment to run our Kogito Labs.
