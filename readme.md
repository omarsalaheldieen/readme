# 🎥 **Caster**
Welcome to Caster! Caster is a user-friendly WPF application built with C# and .NET Framework 4.8. Designed for capturing users’ reactions to videos, Caster simplifies the process of recording, saving, and sharing reaction videos. Whether you're conducting research or creating engaging content, Caster is here to make your workflow seamless and efficient.


## 📚 Table of Contents

1. [Features](#-features)  
2. [Dependencies](#-dependencies)  
3. [How It Works](#-how-it-works)  
4. [Installation](#-installation)  
   - [Requirements](#requirements)  
   - [Setup Instructions](#setup-instructions)  

---

## 🌟 Features

- **🎬 Demo Video**: Offers a preview for testing the application.  
- **📸 Reaction Recording**: Captures user reactions to videos using the selected camera.  
- **☁️ Google Drive Integration**: Automatically uploads recorded videos.  
- **📧 Email Sharing**: Sends a shareable Google Drive link directly to the user’s email.  

---

## 📦 Dependencies

Below is a list of all the NuGet packages used in **Caster**:  

| Package Name                   | Version    | Target Framework | Description                                |  
|--------------------------------|------------|------------------|--------------------------------------------|  
| `AForge`                       | 2.2.5      | net 4.8            | Provides image processing and computer vision features. |  
| `AForge.Video`                 | 2.2.5      | net 4.8            | Handles video processing functionality.    |  
| `AForge.Video.DirectShow`      | 2.2.5      | net 4.8            | Enables access to DirectShow-compatible cameras. |  
| `Flurl`                        | 4.0.0      | net 4.8            | Simplifies HTTP requests.                  |  
| `Flurl.Http`                   | 4.0.2      | net 4.8            | Extends Flurl for HTTP integration.        |  
| `Google.Apis`                  | 1.68.0     | net 4.8            | Connects to Google APIs, including Drive.  |  
| `Google.Apis.Drive.v3`         | 1.68.0.3601| net 4.8            | Specifically handles Google Drive operations. |  
| `MaterialDesignColors`         | 3.1.0      | net 4.8            | Provides elegant material design colors.   |  
| `MaterialDesignThemes`         | 5.1.0      | net 4.8            | Implements material design themes.         |  
| `Newtonsoft.Json`              | 13.0.3     | net 4.8            | Parses and handles JSON data.              |  
| `obs-websocket-dotnet`         | 5.0.0.3    | net 4.8            | Controls OBS via WebSocket.                |  
| `System.Text.Json`             | 6.0.4      | net 4.8            | Provides JSON serialization and deserialization. |  
| `Websocket.Client`             | 4.4.43     | net 4.8            | Maintains WebSocket connections.           |  

---

## 🚀 How It Works

1. **Setup**:  
   - User enters their email and selects their camera from the list.  

2. **Demo Video**:  
   - Plays a sample video to test the camera and workflow.  

3. **Reaction Videos**:  
   - Plays two real videos while recording the user’s reactions.  

4. **Upload**:  
   - Uploads the recorded videos to the user’s Google Drive.  

5. **Email Notification**:  
   - Automatically sends the shareable link to the user’s email.  

---

## 💻 Installation

### Requirements  
- **Windows OS**  
- **Visual Studio 2019+** with .NET Framework 4.8 installed.  

### Setup Instructions  

1. Clone this repository.  
   ```bash
   git clone https://github.com/your-repo/caster.git
   ```  
2. Open the project in Visual Studio.  
3. Restore NuGet packages via the NuGet Package Manager Console:  
   ```bash
   Install-Package AForge
   Install-Package Flurl
   Install-Package Google.Apis
   Install-Package Websocket.Client
   Install-Package obs-websocket-dotnet
   Install-Package MaterialDesignColors
   Install-Package MaterialDesignThemes
   Install-Package Newtonsoft.Json
   ```  
4. Build and run the application! 🎉  

---

## 🛠️ Support

If you encounter any issues or have questions, feel free to reach out:  
- **Email**: [omarsalah56er@gmail.com](mailto:omarsalah56er@gmail.com)  
- **GitHub Issues**: [Submit an issue](https://github.com/your-repo/caster/issues)  

---

Thank you for using **Caster**! Capture moments, share memories, and make an impact. 🎥✨
