<p align="center">
  <img src="./packages/ui/public/logo.png" alt="TurboCoolStack Logo" width="200" />
</p>

<h1 align="center" style="border-bottom:0px">
  TurboCoolStack 🚀
</h1>
 
## Multi-Platform App Development Kick-Start 🚀

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

## 🔧 Setup & Installation

1. Clone the repository.
2. Execute `yarn install` in the root directory to fetch all dependencies.

> 📝 I suggest using Yarn for consistency and efficiency in the development process, though NPM remains an alternative.

## 🚀 Usage

With the dependencies in place, you can dive into development:

- Run `yarn dev` in the root directory to launch the project in development mode, complete with hot reloading for real-time updates.
- Run `yarn build` in the root directory when you're ready to compile a production-ready package of your application.

> ℹ️ A basic understanding of React, TurboRepo, Next.js, Expo and Electron will enhance your development experience.

## Development Mode Overview

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
