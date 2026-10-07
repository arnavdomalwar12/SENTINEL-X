# SENTINEL-X
SENTINEL-X is an intelligent border surveillance and security system. It acts as a software intelligence layer that runs on top of existing IP CCTV infrastructure, giving border posts analytics without replacing cameras with expensive smart hardware. It detects targets, fences areas, names behaviors, scores risk, and keeps evidence.
<div align="center">

<!-- Animated Header Banner -->
<img src="https://capsule-render.vercel.app/api?type=waving&color=0b1121&height=200&section=header&text=SENTINEL-X&fontSize=70&fontAlignY=35&animation=twinkling&fontColor=10b981" width="100%"/>

### 🛡️ Intelligent Border Surveillance & Security System 🛡️
*Surveillance Engine for Networked Threat Intelligence, Notification and Evidence Logging*

[![SIH 2026](https://img.shields.io/badge/SIH_2026-Problem_26187-FF9900?style=for-the-badge)](#)
[![MHA](https://img.shields.io/badge/MHA-Sashastra_Seema_Bal-003366?style=for-the-badge)](#)
[![Police II Division](https://img.shields.io/badge/Division-Police_II-10b981?style=for-the-badge)](#)
[![Tests](https://img.shields.io/badge/Automated_Tests-1067-success?style=for-the-badge&logo=pytest)](#)
[![Python](https://img.shields.io/badge/Python-3.10%2B-blue?style=for-the-badge&logo=python&logoColor=white)](#)

<br>

A software intelligence layer that runs on top of **existing IP CCTV infrastructure**,
so border posts get analytics without replacing cameras with expensive smart hardware.

`VIDEO` ➔ `DETECTION` ➔ `TRACKING` ➔ `ZONES` ➔ `CONTEXT` ➔ `BEHAVIOUR` ➔ `RISK` ➔ `ALERT` ➔ `EVIDENCE`

<br>

**1067 automated tests.** Every claim below is qualified by whether it has been run
against real footage or only against a test rig — see
[What is proven, and what is not](#what-is-proven-and-what-is-not).

</div>

---

## 🎯 What it does

<!-- Placeholder for a demo GIF. Replace the src with your actual github repo raw link for a demo gif -->
<div align="center">
  <img src="https://raw.githubusercontent.com/FortAwesome/Font-Awesome/6.x/svgs/solid/video.svg" width="100" alt="Camera Demo"/>
  <br>
  <em>(Replace this block with an animated .gif of your dashboard or pipeline in action)</em>
</div>
<br>

* **Detects** people and vehicles (car, truck, bus, motorcycle, bicycle) on a still, a video file, a webcam or a live RTSP/HTTP camera.
* **Tracks** them with stable IDs, and **recovers a track after an occlusion** by appearance, so a person who steps behind a pillar is still the same person.
* **Fences** areas with polygon zones that know what they are fencing — a vehicle lane is a fence for pedestrians but not for the trucks it exists to admit.
* **Measures** speed, heading, dwell time, distance to the fence and proximity to the camera; in metres per second on a calibrated camera.
* **Names behaviours**: loitering, border-facing movement, erratic movement, night movement, rapid movement, and camera tampering.
* **Watches itself**: a camera that stops answering is treated as a possible tampering event, not just an outage.
* **Recognises the people who belong** — an enrolled guard on patrol stops reading like an intruder, so the alerts that remain mean something.
* **Scores risk** 0–100, where every point is attributable to a named factor.
* **Reads number plates** off vehicles, pools reads across cameras, and checks them against a vehicle registration extract — flagging a plate that does not match the vehicle carrying it.
* **Keeps evidence**: an annotated still, a video clip covering the seconds either side of the alert, and the plate crop.
* **Follows a subject between cameras** — vehicles by plate, people by appearance, with the weaker of the two labelled as inferred.
* **Runs many cameras in one process**, sharing one loaded model.
* **Serves** a live dashboard and a JSON API.

---

## 🚀 How to run

Works on Windows, Linux and macOS. Commands are shown for Windows PowerShell; on Linux or macOS use `python3` where it says `python`.

### 1. What you need

* **Python 3.10 or newer** (built and tested on 3.11)
* About **3 GB of disk** for the Python packages (PyTorch and PaddleOCR are the big ones)
* **No GPU**, and **no camera** for the first runs. A webcam, a video file or an RTSP camera only when you want real footage.
* Internet **once**, for `pip install` and for the YOLO weights on the first real-camera run. After that it runs fully offline.
