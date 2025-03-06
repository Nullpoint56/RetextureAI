# Technical Architecture Document

## 1. Overview
This document outlines the technical architecture of the **AI-Powered Texture Manipulation Tool**, detailing the system components, data flow, and technologies used to enable **AI-assisted texture generation, object selection, and blending** in a web-based environment.

## 2. System Architecture
### 2.1 High-Level Structure
The system consists of three primary components:
- **Frontend (Web UI)**: Built with **Angular** or **Electron**, providing a simple interface for image selection, texture generation, and blending.
- **Backend (REST API & Session Management)**: Handles **user authentication, session management, and communication with the AI Model Backend**.
- **AI Model Backend (Inference Engine)**: A dedicated service that performs AI-powered **texture generation and processing** based on requests from the Backend.

### 2.2 System Diagram
```
[ User ]
    |
    | (Web UI - Angular/Electron)
    v
[ Frontend Application ]
    |
    | REST API Calls
    v
[ Backend (Session & API Management)]
    |
    | Calls AI Model Backend for Inference
    v
[ AI Model Backend (Inference Engine)]
    |
    | AI Texture Generation
    v
[ Image Processing Module (Masking, Blending)]
    |
    | Final Image Output
    v
[ Export (PNG, JPG)]
```

## 3. Core Components
### 3.1 Frontend (Web UI)
- **Technology:** Angular or Electron
- **Features:**
  - Upload an image
  - Select an object/area using a **lasso-based selection tool**
  - Enter a **text prompt for texture generation**
  - Adjust **blending settings** (predefined modes + adjustable parameters)
  - Export final image (PNG, JPG)

### 3.2 Backend (REST API & Session Management)
- **Technology:** Python (FastAPI/Flask)
- **Functionality:**
  - **User authentication & session management**
  - **Manages API requests from the frontend**
  - **Communicates with the AI Model Backend** for texture generation
  - **Passes settings & configurations** to the AI Model Backend for initialization
  - **Handles AI model loading requests and configuration** (but does not perform inference itself)

### 3.3 AI Model Backend (Inference Engine)
- **Handles AI-powered texture generation** (Stable Diffusion, Kandinsky, DALL-E, or similar open-source models)
- **Dedicated inference engine for model execution on CPU/GPU**
- **REST API Endpoint for Texture Generation**
- **Supports custom model loading** (if models are in supported formats)
- **Pre-processing & Post-processing for optimal texture integration**

## 4. Image Processing & Selection
### 4.1 Object Selection Mechanism
- **Lasso-based selection with AI-assisted refinement** (similar to Samsung AI selection tools)
- **User draws a rough selection, and the system refines it automatically**
- **Utilizes edge detection and segmentation for improved selection accuracy**

### 4.2 Facial Feature Protection
- **Ensures textures conform to the natural surface** by:
  - Detecting and preserving facial landmarks (eyes, nose, lips, etc.)
  - Using a **gradient-based blending** to maintain structure
  - Preventing AI from altering important facial details (avoiding the usual inpainting distortion issue)
- **Always active to ensure proper texture fitting**

## 5. Image Blending & Export
### 5.1 Blending
- **Predefined blending modes**: Overlay, Multiply, Soft Light, etc.
- **User-adjustable parameters** for fine-tuning texture integration
- **Layered processing** (original image + AI texture layer)

### 5.2 Supported File Formats
- **Initial Support:** PNG, JPG
- **Future Expansion:** DDS, TIFF

## 6. Performance Considerations
- **AI Model Backend Optimized for Various Hardware:**
  - Runs on **CPUs, NVIDIA GPUs, AMD GPUs, Intel GPUs**
  - Future support planned for **ARM NPUs in V2**
- **No Real-Time Preview Rendering** to optimize performance
- **Batch processing for multiple textures (Future Version)**

## 7. Future Roadmap
✅ **Version 1** (MVP):
- Web-based interface (Angular/Electron)
- REST API for session and AI model backend communication
- Selection, AI texture application, blending

🔄 **Version 2** (Planned Features):
- Native mobile backend (optimized for ARM NPUs)
- DDS & TIFF format support
- Layer-based editing with advanced controls
- Batch generation of textures with variations

