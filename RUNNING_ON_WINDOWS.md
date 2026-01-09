# How to Run CC-Switch on Windows

## 1. Prerequisites
Before running the project, ensure you have the following installed:
*   **Node.js** (v18+)
*   **Rust** (Latest stable)
*   **Visual Studio Build Tools** (must include "Desktop development with C++")
*   **pnpm** (install via `npm install -g pnpm`)

## 2. Important: Path Issue with "Ying's File"
The current folder path contains a single quote (`'`) in "Ying's File". 
**This breaks the Windows Resource Compiler (RC.EXE)** used by Rust/Tauri.

You **cannot** run the project directly from this folder. You must move or copy it to a path with no special characters (e.g., `C:\Users\li_ca\cc-switch`).

## 3. Step-by-Step Run Instructions

1.  **Copy the project to a safe location**:
    Open PowerShell and run:
    ```powershell
    xcopy "C:\Users\li_ca\Downloads\Ying's File\myproject\cc-switch" "C:\Users\li_ca\cc_switch_temp" /E /I /Q /H /Y
    ```

2.  **Navigate to the new folder**:
    ```powershell
    cd C:\Users\li_ca\cc_switch_temp
    ```

3.  **Install Dependencies**:
    ```powershell
    pnpm install
    ```

4.  **Run the Development Server**:
    This command will start the frontend and compile the Rust backend.
    ```powershell
    pnpm dev
    ```

The application window should appear once compilation completes.
