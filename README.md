# Adaptive Interface for Neurodiverse Users

An adaptive web interface that adjusts layout, font, and accessibility features in real time based on user interaction patterns.  
It currently detects and responds to behavioral patterns related to **ADHD** and **Dyslexia**, modifying visual complexity, typography, and focus to enhance usability.

---

## Run Locally

### Step 1: Extract
- Extract the zip anywhere

---

### Step 2: Setup the Backend (FastAPI)

**Requirements:** Python 3.10+ and pip

```bash
cd backend
python -m venv .venv
# Activate environment:
# Windows → .venv\Scripts\activate
# macOS/Linux → source .venv/bin/activate

pip install -r requirements.txt
uvicorn app.main:asgi --reload --port 8000
```

✅ Verify Backend:
Open http://127.0.0.1:8000/docs
 — you should see the FastAPI documentation.

### Step 3: Setup the Frontend (React + Vite)

Requirements: Node.js 18+ and npm

Open another terminal window:
```
cd frontend
npm install
npm run dev
```

# Verify Frontend:
Go to http://localhost:5173
 in your browser.
You should see the interface with the accessibility toolbar and adaptive features.


### Testing the System
```
1. Type text into the Additional Notes field and click Simplify — the text will be processed through the backend API.
2. Open browser DevTools → Network → WS — you’ll see an active /socket.io connection.
3. Use the Debug Panel buttons:
  #Simulate ADHD-like: triggers focus and distraction-free UI adjustments.
  #Simulate Dyslexia-like: triggers font and readability changes.
4. The UI adapts automatically based on the simulated user behavior.
```
### Tech Stack
| Layer                       | Technology                                         |
| --------------------------- | -------------------------------------------------- |
| **Frontend**                | React 18, TypeScript, TailwindCSS, Zustand         |
| **Backend**                 | FastAPI, Python, Socket.IO                         |
| **Real-Time Communication** | WebSockets                                         |
| **Purpose**                 | Adaptive accessibility for neurodiverse user needs |



### Project Structure
```
adaptive-interface/
├─ README.md
├─ backend/
│  ├─ requirements.txt
│  └─ app/
│     ├─ main.py
│     ├─ rules.py
│     └─ util.py
└─ frontend/
   ├─ index.html
   ├─ package.json
   ├─ tsconfig.json
   ├─ vite.config.ts
   ├─ postcss.config.js
   ├─ tailwind.config.js
   └─ src/
      ├─ main.tsx
      ├─ App.tsx
      ├─ styles.css
      ├─ lib/
      │  ├─ api.ts
      │  └─ socket.ts
      ├─ store/
      │  └─ adaptiveStore.ts
      ├─ hooks/
      │  ├─ useBehaviorTracker.ts
      │  └─ useAdaptiveRules.ts
      └─ components/
         ├─ AccessibilityToolbar.tsx
         ├─ DistractionFreeOverlay.tsx
         ├─ CheckoutDemo.tsx
         ├─ DebugPanel.tsx
         └─ StatusBar.tsx

```
---
