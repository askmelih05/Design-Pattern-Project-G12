# Design Patterns Project: Inventory Management System (Java & Frontend Sim)

This project demonstrates the integration of **six critical design patterns** into a console-based inventory management application developed in Java, featuring a modern **Single Page Application (SPA) simulation** for the frontend.

## Core Architecture and Frontend Enhancements

* **Backend:** Developed in Java, incorporating **Composite, Decorator, Observer, Strategy, Singleton**, and **Builder** patterns.
* **Frontend (SPA):** Built using HTML, CSS, and JavaScript. The UI simulates a modern SPA by using the `fetch` API to load content dynamically into the main area (`#content-container`) upon menu selection.
* **Scope Resolution:** All interaction functions (`simulateAddCategory`, `simulateStrategy`, etc.) are defined in the **global scope** (`index.html`) to prevent JavaScript `ReferenceError` issues caused by dynamic page loading.

### Integrated Design Patterns Summary

| Pattern | Category | Role in Application |
| :--- | :--- | :--- |
| **Composite** | Structural | Manages the hierarchy between Categories and Products. |
| **Decorator** | Structural | Dynamically adds price adjustments (e.g., discount/markup) to products. |
| **Observer** | Behavioral | Monitors stock levels and triggers alerts upon changes (Low Stock). |
| **Strategy** | Behavioral | Enables dynamic switching of pricing logic (Normal vs. Tax Included). |
| **Singleton** | Creational | Manages global application settings (`ConfigurationManager`) centrally. |
| **Builder** | Creational | Provides controlled, step-by-step creation for complex products (e.g., Laptops). |

---

## How to Run the Project

The application requires running the Java Backend and the Web Frontend processes concurrently.

### Step 1: Run the Java Backend (Core Logic)

This process runs the core application logic and outputs all logs and alerts.

1.  In your command line, navigate to the **`backend`** directory.
2.  Compile all Java source files:
    ```bash
    javac *.java
    ```
3.  Start the main application (Core Logic):
    ```bash
    java Main
    ```
    *(Keep this console window open; all logs, alerts, and pattern outputs will appear here.)*

### Step 2: Run the Frontend Server (SPA)

The web frontend must be served over HTTP to allow JavaScript `fetch` API calls to work correctly (bypassing local file security restrictions).

1.  Open a **new** command line window and navigate to the **`backend`** directory (where `SimpleHttpServer.java` is located).
2.  Start the Frontend Server:
    ```bash
    java SimpleHttpServer
    ```
3.  Open your browser and navigate to the application address:
    ```
    http://localhost:8000/index.html
    ```

You can now interact with the web interface, and the resulting actions will simulate signals being sent to your running Java console.
