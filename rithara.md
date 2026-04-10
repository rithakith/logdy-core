# Rithara's Logdy Guide 🚀

This guide helps you remember how to run Logdy in different modes.

## 1. Demo Versions (Quickest way to see it)

### Option A: UI-Only Demo (No Go needed)
Use this if you only want to play with the interface.
1. Navigate to `logdy-ui` folder.
2. Run: `npm run dev`
3. Open: `http://localhost:5173?demo` in your browser.

### Option B: Core Demo (The "Go" way)
Use this to see the Go backend generating fake logs.
1. Navigate to `logdy-core` folder.
2. Run: `go run . demo 1`
3. Open: `http://localhost:8080` in your browser.

---

## 2. Real Version (Streaming your own logs)

### Running as a Go developer
To run the latest backend code with the embedded UI:
1. Navigate to `logdy-core`.
2. Run any command, for example:
   - Pipe logs: `tail -f my_app.log | go run .`
   - Run a command: `go run . stdin "npm run start"`
3. Open: `http://localhost:8080`.

### Building the Single Binary (Production)
If you want to create the final `logdy.exe` that has the UI inside it:
1. **In `logdy-ui`**: Run `npm run build`.
2. **Copy Files**: Copy everything from `logdy-ui/dist` to `logdy-core/http/assets/`.
3. **In `logdy-core`**: Run `go build`.
4. Run the generated `logdy.exe`.

---

## 3. Do I need both repos?

**No, you don't always need both.**

- **Just the UI?** You only need `logdy-ui` (running in `?demo` mode).
- **Just the Go app?** You only need `logdy-core`. Since the UI is already embedded in `logdy-core/http/assets`, running the Go app will serve the UI automatically.
- **Both?** You only need both if you are **developing** the UI. You run the `logdy-ui` dev server for hot-reloads and the `logdy-core` backend for the actual log data.

---

### Useful Commands Recap
| Goal | Command | Location |
| :--- | :--- | :--- |
| **Run UI Dev** | `npm run dev` | `logdy-ui` |
| **Run Go Demo** | `go run . demo 1` | `logdy-core` |
| **Run Go Stdin** | `some_cmd | go run .` | `logdy-core` |
| **Build Binary** | `go build` | `logdy-core` |
