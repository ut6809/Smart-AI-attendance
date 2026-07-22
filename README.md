# Smart AI Attendance

Short description

A lightweight Smart AI Attendance system combining face and voice recognition to take automated attendance, manage subjects and students, and provide a simple dashboard for teachers and administrators.


## Table of Contents
- [Key Features](#key-features)
- [Quick Start](#quick-start)
- [Installation](#installation)
- [Running the App](#running-the-app)
- [Project Structure](#project-structure)
- [Usage](#usage)
- [Configuration & Secrets](#configuration--secrets)
- [Contributing](#contributing)
- [Troubleshooting](#troubleshooting)
- [License](#license)


## Key Features
- Face-based attendance using the face pipeline
- Voice-based attendance using the voice pipeline
- Manual and automatic enrollment flows
- Subject and student management via UI dialogs
- Simple dashboard for viewing attendance and subjects
- Export or share attendance data (CSV/export-ready)
- Streamlit-based UI for quick deployment and local testing


## Quick Start (short)
1. Create a virtual environment and install requirements:

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

2. Start the app (Streamlit):

```bash
streamlit run app.py
```

Open the URL printed by Streamlit (usually http://localhost:8501).


## Installation (detailed)
1. Clone or copy the project to your machine.
2. Ensure you have Python 3.9+ installed.
3. Install dependencies:

```bash
pip install -r requirements.txt
```

4. (Optional) Create and activate a virtual environment before installing packages.


## Running the App
- Local development / UI:

```bash
streamlit run app.py
```

- If `app.py` is a wrapper, you can also run it directly:

```bash
python app.py
```

The app uses Streamlit pages and custom screens located under `src/screens/`. The UI components and dialogs are in `src/screens/components/`.


## Project Structure
- `app.py` - Application entrypoint (Streamlit runner)
- `requirements.txt` - Python dependencies
- `src/` - Main source folder
  - `pipelines/` - `face_pipeline.py`, `voice_pipeline.py` (recognition flow implementations)
  - `screens/` - Streamlit screen modules and UI components
    - `components/` - Dialog components (e.g., enroll dialogs, header/footer, subject card)
    - `database/` - `db.py`, `config.py` for data persistence
  - `streamlit/` - Streamlit secrets and configuration (e.g., `secrets.toml`)

Example important files:
- [app.py](app.py)
- [src/pipelines/face_pipeline.py](src/pipelines/face_pipeline.py)
- [src/pipelines/voice_pipeline.py](src/pipelines/voice_pipeline.py)
- [src/screens/components/header.py](src/screens/components/header.py)
- [src/screens/components/dialog_enroll.py](src/screens/components/dialog_enroll.py)


## Usage
- Home screen: Overview and quick actions (start face or voice attendance).
- Student/Teacher screens: Manage profiles, view attendance history, and enroll students.
- Enrollment: Use the enroll dialogs to add a student with a photo (auto-enroll supported) or voice sample.
- Attendance flow:
  - Face: The face pipeline captures an image, compares with enrolled embeddings, and marks attendance.
  - Voice: The voice pipeline captures a voice sample and performs speaker recognition to mark attendance.


## Configuration & Secrets
- Secrets for third-party services or Streamlit-specific values can be placed in `streamlit/secrets.toml`.
- Database configuration can be found/modified in `src/screens/database/config.py`.


## Contributing
- Fork the repo, create a feature branch, and open a pull request.
- Keep changes focused and include tests for new functionality when possible.
- Update `requirements.txt` when adding new dependencies.


## Troubleshooting
- If the app fails to start, ensure dependencies were installed and the correct Python interpreter is used.
- For camera/microphone access issues, ensure the browser where Streamlit opened has permissions and your OS allows the app to access devices.
- If recognition accuracy is low, review enrollment sample quality and dataset size.


## License
This project is provided "as-is". Add a LICENSE file or update this section to match your preferred license.


---

If you want, I can also:
- Add a brief badge header (build/coverage) to `README.md`.
- Commit the file and create a Git summary pull request message.
- Add example screenshots or an assets folder for UI previews.

