# Live Location Tracker & OSINT Solution

A full-stack, hybrid intelligence system designed for real-time geolocation tracking, deep Open-Source Intelligence (OSINT) analysis, and network heuristics. 

Standard location trackers rely on easily spoofed browser APIs. I engineered this system to bypass those limitations by combining a React frontend and Python Flask backend with high-performance C++ shared libraries. It actively validates network integrity, detects VPNs/Proxies, and performs multi-threaded social media validation without compromising UI responsiveness.

## Core Architecture & Features

* **High-Performance Geofencing (C++ DLLs):** To prevent system bottlenecking, computationally intensive geometric algorithms (Ray Casting and the Shoelace Formula) were offloaded to custom-compiled C++ shared libraries. This allows the system to calculate territorial geofences in microseconds, scaling effortlessly to thousands of coordinate points.
* **Multi-Threaded OSINT Scanning:** The backend engine performs simultaneous data validation across 10+ target websites. By implementing advanced multithreading, the system prevents data-processing freezes, keeping the React/Leaflet UI entirely responsive during deep scans.
* **Network Heuristics & Validation:** Integrates GeoIP2 database heuristics for accurate VPN and proxy detection, alongside SMTP MX Record logic to strictly validate email address authenticity.
* **"Brutal Mode" Build:** A highly optimized, production-ready state that adheres to strict industry standards for memory management, modularity, and error handling.

## Technology Stack

* **Frontend:** React.js, Leaflet API (MapContainer / Marker rendering)
* **Backend:** Python (Flask), Multi-threading modules
* **Low-Level Processing:** C++ (Compiled DLLs for geometric algorithms)
* **Concepts Applied:** Data Structures & Algorithms, Computer Organization, Assembly-level Memory Management, Hybrid Full-Stack Design.

## Project Structure & Setup

This repository contains the core logic for the hybrid system. 

**To run the system locally:**
1. Clone the repository.
2. Install frontend dependencies:
   ```bash
   cd frontend
   npm install
   npm start
   ```

   ## nitialize the Python backend:
    ```bash
   cd backend
   pip install -r requirements.txt
   python app.py
    ```

    ## Technical Hurdles & Engineering Focus

The primary challenge of this project was bridging high-level web frameworks with low-level execution. Standard Python struggled with the sheer mathematical overhead of processing complex geofences in real-time.

By identifying this bottleneck, I integrated concepts from Computer Organization and designed a C++ DLL to handle the heavy lifting. Managing the memory pointers and data-type conversions between Python and C++ was incredibly complex, but it resulted in a system that is exponentially faster than a pure Python implementation. This project cemented my understanding of how low-level optimization directly drives high-level application scalability.

