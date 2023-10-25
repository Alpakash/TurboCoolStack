<p align="center">
  <img src="./packages/ui/public/logo.png" alt="TurboCoolStack Logo" width="200" />
</p>

<h1 align="center" style="border-bottom:0px">
  TurboCoolStack 🚀 ⚛
</h1>
 
## ⚛ Multi-Platform 📱💻 App Development Kick-Start 🚀

**TurboCoolStack** 🚀 provides a solid starting point within the Turborepo for building applications across different platforms, integrating Electron, React (CRA, Next.js), React Native (Expo - IOS, Android), and Tailwind CSS for a streamlined development process. This setup is engineered for those looking to efficiently develop desktop, web, and mobile applications with consistent quality and a streamlined workflow.

**Important**: One of the central features of **TurboCoolStack** is that almost all the applications leverage a common source of React components located in **packages/ui**. This structure promotes uniformity and efficiency in development. Additionally, all workspaces share a common Tailwind CSS configuration, ensuring a consistent design system across all platforms.

## 📁 Workspaces Overview

- **app/docs**: A web app based on Create React App with Tailwind CSS.
- **app/electronRenderer**: Utilizes Create React App with Tailwind CSS, for the Electron renderer process and desktop app UI development.
- **app/electronMain**: Handles Electron's main process, managed by Webpack, responsible for core OS-level interactions.
- **app/electronBuilder**: Oversees the application packaging stage with Electron Builder, It's tasked with compiling and assembling the final desktop application.
- **app/native**: A React Native app based on Expo with Nativewind CSS.
- **app/web**: A web app grounded on Next.js with Tailwind CSS.
- **packages/ui**: This workspace serves as a central repository for UI React components, styled with Tailwind CSS.

## ⚙️ Prerequisites

Before you proceed with the setup, ensure that your development environment meets the following requirements. This project was created with specific versions of Node and Yarn to avoid compatibility issues and leverage their latest features. Here are the versions you'll need:

- **Node.js**: Version 18.

- **Yarn**: Version 4.

By using the same versions, you’re aligning with the project's original development environment, minimizing potential issues related to version discrepancies.

## 🔧 Setup & Installation

1. Clone the repository.
2. Execute `yarn install` in the root directory to fetch all dependencies.

> 📝 I suggest using Yarn for consistency and efficiency in the development process, though NPM remains an alternative.

## 🚀 Usage

With the dependencies in place, you can dive into development:

- Run `yarn dev` in the root directory to launch the project in development mode, complete with hot reloading for real-time updates.
- Run `yarn build` in the root directory when you're ready to compile a production-ready package of your application.

> ℹ️ A basic understanding of React, TurboRepo, Next.js, Expo and Electron will enhance your development experience.

## ⚙️ Development Mode Overview

In development mode, various components of the application initialize automatically.

- **app/electronRenderer**: This part will automatically launch within an Electron window. Additionally, for easier access, it is available through your web browser at port 3001.
- **app/electronMain**: This is the designated area for configuring your Electron desktop application. It's integral to define the behavior of the app's main process here. From window creation to custom functionalities, this part is pivotal for the desktop app's performance and feature set. Make sure to configure settings tailored to your project's needs.
- **app/docs**: This workspace will automatically start in a browser window, becoming accessible at port 3002.
- **app/web**: Differing from the others, this Next.js application doesn't start automatically in the browser. It requires you to manually navigate to [http://localhost:3000/](http://localhost:3000/).
- **app/native**: One of the easiest way is to utilize the Expo Go app on your mobile device. While in development mode, ensure you are logged into the same free Expo account on both your desktop and mobile device. This synchronization will automatically display links in the Expo Go app, directing you to your current project.

## 📚 Resources

To get the most out of TurboCoolStack, you might find it helpful to familiarize yourself with the documentation of the technologies used. Here are the quick links to the official documentation:

- **TurboRepo**: [Official Documentation](https://turbo.build/repo/docs)
- **Next.js**: [Official Documentation](https://nextjs.org/docs)
- **Tailwind CSS**: [Official Documentation](https://tailwindcss.com/docs)
- **Electron**: [Official Documentation](https://www.electronjs.org/docs)
- **React Native**: [Official Documentation](https://reactnative.dev/docs/getting-started)
- **Expo**: [Official Documentation](https://docs.expo.dev)

## 📝 To-Do List

There are ongoing improvements and features in the pipeline to enhance the versatility and efficiency of **TurboCoolStack**. Here are some tasks on the roadmap:

1. **Shared Static Files Between Workspaces**: 🗂️

   - Currently, to use a single image across multiple workspaces, it's necessary to duplicate the file into each workspace's `public` folder. I'am aiming to solve the problem for static files to prevent redundancy and improve resource management. Let me know if you know how to handle it 💪.

2. **Creation of `packages/ui-native` Workspace**: 📱
   - The goal is to set up a new workspace named `packages/ui-native` and configure Nativewind within it. This enhancement will allow the `app/native` workspace to share components with `packages/ui-native`, streamlining the development process across native platforms.

Completing these tasks will contribute significantly to making **TurboCoolStack** even more efficient and developer-friendly. Any contributions or suggestions for these to-dos are welcome! 🚀

## 🛠 Troubleshooting Common Issues

Developing across different platforms and environments can sometimes lead to unexpected issues. This section aims to address some of the common problems you might encounter when working with **TurboCoolStack**.

### 🚨 Issue: Build Failure on Windows

**Problem**: 
Developers might experience a build process failure specifically on Windows systems during the file copying stage within the `apps/electronBuilder` workspace. The operation stops unexpectedly, indicating errors that are typically related to command-line instructions for copying and removing files.

**Likely Cause**: 
This problem often arises due to incompatibility between certain shell commands used in scripts within `package.json` and the Windows command line interpreter. These script commands, are set up for Unix-based systems and do not execute as expected on Windows.

**Quick Fix**:

1. Open the `package.json` file in the `apps/electronBuilder` workspace.
2. Locate the scripts.
3. Modify these commands to use their Windows equivalents. 
4. Save your changes and rerun the build process.

```json
// Example modification in package.json (adjusting for Windows compatibility)
"scripts": {
  // Modified for Windows
  "copy-main": "xcopy ..\\electronMain\\dist dist-main\\ /E /I /H /Y", 
  "copy-renderer": "xcopy ..\\electronRenderer\\build dist-renderer\\ /E /I /H /Y", 
  "copy": "yarn copy-main && yarn copy-renderer",
  "clear": "rimraf dist",
  "cleaning-up": "rimraf dist-main && rimraf dist-renderer", 
  "clean": "rimraf dist && rimraf dist-main && rimraf dist-renderer",
  "build": "yarn copy && electron-builder && yarn cleaning-up",

  // Original Unix commands
  "copy-main": "cp -R ../electronMain/dist dist-main",
  "copy-renderer": "cp -R ../electronRenderer/build dist-renderer",
  "copy": "yarn copy-main && yarn copy-renderer",
  "clear": "rm -rf dist",
  "cleaning-up": "rm -rf dist-main && rm -rf dist-renderer",
  "clean": "rm -rf dist && rm -rf dist-main && rm -rf dist-renderer",
  "build": "yarn copy && electron-builder && yarn cleaning-up",
}
```

## 📄 License

This project is licensed under the terms of the [MIT license](https://opensource.org/licenses/MIT) and is available for free.

Feel free to use and modify the codebase for your personal, company, or educational purposes. Attribution is not required, but if you find this project helpful, a reference or credit is always appreciated.

---

## ⭐ Show Your Support

If you found **TurboCoolStack** 🚀 useful, consider giving the repository a star! Your support motivates me to keep making this project even better.

Star ⭐ the repo [here](https://github.com/ja-klaudiusz/TurboCoolStack).

Thank you for being part of this journey!

---

[![Star on GitHub](https://img.shields.io/github/stars/ja-klaudiusz/TurboCoolStack.svg?style=social)](https://github.com/ja-klaudiusz/TurboCoolStack/stargazers)
