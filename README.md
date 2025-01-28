# 📽️ AR Video Player (Vuforia) Documentation 🎥

![WhatsApp Image 2023-01-07 at 7 00 57 PM](https://user-images.githubusercontent.com/62818241/211153430-f4294707-de45-4f14-b929-660ced9066f2.jpeg)

## 📌 Project Overview

**AR Video Player** is a Unity-based **Augmented Reality (AR) application** that plays videos using **Vuforia** image targets. This project allows users to scan a predefined **AR marker**, triggering an embedded video to play on the detected surface. The app provides an interactive and immersive **AR video playback experience** on mobile devices.

---

## 🚀 Key Features

✅ **Augmented Reality Video Playback** using Vuforia.  
✅ **Marker-Based Tracking** for stable video placement.  
✅ **Customizable Video UI** with play, pause, and stop functions.  
✅ **Automatic Video Looping** for continuous playback.  
✅ **Optimized for Mobile (Android & iOS).**  

---

## 🎮 Application Mechanics

### 🎬 Video Playback (ARVideoPlayer.cs)
- Uses **Unity VideoPlayer** to render video on an **Image Target**.
- Triggers video playback when the AR marker is detected.
- Supports **Play, Pause, Stop** functions via UI buttons.

```csharp
using UnityEngine;
using UnityEngine.Video;

public class ARVideoPlayer : MonoBehaviour
{
    public VideoPlayer videoPlayer;
    public GameObject playButton;
    public GameObject pauseButton;
    public GameObject stopButton;

    void Start()
    {
        videoPlayer.Prepare();
    }

    public void PlayVideo()
    {
        videoPlayer.Play();
        playButton.SetActive(false);
        pauseButton.SetActive(true);
        stopButton.SetActive(true);
    }

    public void PauseVideo()
    {
        videoPlayer.Pause();
        playButton.SetActive(true);
    }

    public void StopVideo()
    {
        videoPlayer.Stop();
        playButton.SetActive(true);
        pauseButton.SetActive(false);
        stopButton.SetActive(false);
    }
}
```

### 🌍 Augmented Reality Integration (Vuforia)
- **Vuforia Image Target** detects the marker and overlays the video.
- Video remains **anchored to the target**, ensuring a stable AR experience.
- **Re-triggers playback** when the marker is detected again.

### 🖥️ UI Controls (UIManager.cs)
- Provides an **interactive UI** for controlling video playback.
- Uses Unity’s **Canvas System** for buttons.
- Implements basic **visibility toggles** for UI elements.

```csharp
using UnityEngine;

public class UIManager : MonoBehaviour
{
    public GameObject controlPanel;

    public void ToggleControls()
    {
        controlPanel.SetActive(!controlPanel.activeSelf);
    }
}
```

---

## 🔧 How to Use

1. **Open** the **AR Video Player** app.
2. **Scan** the AR marker using the device camera.
3. The video **automatically starts playing** on the marker.
4. Use the **Play, Pause, and Stop** buttons to control playback.
5. Enjoy an **interactive AR video experience!**

---

## 🛠️ Technical Details
- **Platform:** Unity (C#) with Vuforia SDK
- **Supported Devices:** Android & iOS
- **Rendering Pipeline:** Unity Standard VideoPlayer
- **Dependencies:** Vuforia, Unity UI System

---

## 🌟 Future Enhancements
✨ **Multiple Video Markers:** Support for different videos on different markers.  
✨ **360° Video Support:** Immersive VR-style video playback.  
✨ **Gesture Controls:** Swipe-based video controls.  

