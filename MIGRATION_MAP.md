# خريطة ملفات المشروع القديم إلى نسخة المتصفح

| الملف القديم | مكانه في المشروع الجديد |
|---|---|
| `main.py` | `run.py` و`app/__init__.py` |
| `security.py` | `app/security.py` |
| `fingerprint_login.py` | `app/fingerprint.py` |
| `control.py` | `app/control.py` |
| `security_access.py` | `app/security_access.py` و`app/routes/security_routes.py` |
| `meeting.py` | `app/meeting.py` و`app/routes/meeting_routes.py` |
| `person.py` | `app/person.py` و`app/routes/person_routes.py` |
| `privacy.py` | `app/privacy.py` |
| `settings.py` | `app/settings_manager.py` و`app/routes/settings_routes.py` |
| `speech_system.py` | `app/speech_system.py` و`app/static/js/voice.js` |
| `ai_assistant.py` | `app/ai_assistant.py` |
| `translator.py` | `app/translator.py` |
| `ui.py` | `app/ui.py` و`app/templates/` و`app/static/` |
| `camera.py` | `app/camera.py` و`app/routes/camera_routes.py` |
| `database.py` | `app/database.py` |
| `emotion.py` | `app/emotion.py` |
| `people.json` | `data/people.json` |
| `face_model.yml` | ينشأ تلقائيًا في `models/face_model.yml` بعد التدريب |
| `requirements.txt` | `requirements.txt` و`requirements-vision.txt` |
| `README.md` | `README.md` |
| ملفات `Activate.*` و`pyvenv.cfg` | ينشئها `python -m venv venv311` تلقائيًا |
