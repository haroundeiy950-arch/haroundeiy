# Smart AI Glasses Web Modular

نسخة ويب جديدة ومنظمة من مشروع **Smart AI Glasses System**. كل وظيفة موجودة في ملف مستقل، بدل وضع كل الأكواد في `main.py`.

## أهم الملفات

- `app/security.py`: اسم المستخدم وكلمة المرور.
- `app/fingerprint.py`: Windows Hello والبصمة.
- `app/security_access.py`: صور محاولات الدخول المرفوضة.
- `app/control.py`: المتحكم المركزي الذي يربط الخدمات.
- `app/person.py`: تسجيل الأشخاص وملف `people.json`.
- `app/face_model.py`: عينات الوجه، التدريب، و`face_model.yml`.
- `app/camera.py`: تحليل إطار الكاميرا.
- `app/emotion.py`: تحليل المشاعر النصي الأساسي.
- `app/meeting.py`: الاجتماعات والملخص والمهام.
- `app/privacy.py`: موافقة الخصوصية ومسارات البيانات.
- `app/settings_manager.py`: قراءة وحفظ الإعدادات.
- `app/speech_system.py`: تحويل الصوت إلى نص والنص إلى صوت AI.
- `app/ai_assistant.py`: المساعد الذكي.
- `app/translator.py`: الترجمة.
- `app/database.py`: SQLite.
- `app/routes/`: كل صفحة ومسارات API في ملف مستقل.
- `app/static/js/`: JavaScript منفصل لكل صفحة.
- `app/templates/`: HTML منفصل لكل صفحة.

## لا تنسخ ملفات venv القديمة

الملفات التالية ينشئها Python تلقائيًا، ولا تُكتب يدويًا داخل المشروع:

`Activate.bat`, `Activate.ps1`, `activate.fish`, `pyvenv.cfg`, ملفات `pywin32`.

## التشغيل على Windows

1. فك الضغط، ثم افتح PowerShell داخل مجلد المشروع.
2. شغّل:

```powershell
Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
.\start.ps1
```

أو اضغط مرتين على `start.bat`.

3. افتح:

```text
http://127.0.0.1:8000
```

بيانات الدخول الأولى:

```text
Username: admin
Password: ChangeMe@12345
```

غيّر كلمة المرور من صفحة **الإعدادات**.

## تفعيل التعرف على الوجه

داخل البيئة الافتراضية:

```powershell
python -m pip install -r requirements-vision.txt
```

ثم:

1. سجل الشخص.
2. افتح الكاميرا في صفحة الأشخاص.
3. اختر الشخص والتقط 20 عينة.
4. اضغط تدريب النموذج.
5. افتح صفحة الكاميرا واضغط التعرف المحلي.

سيتم إنشاء:

```text
models/face_model.yml
models/face_labels.json
```

## تفعيل AI Voice القوي

انسخ `.env.example` إلى `.env`:

```powershell
Copy-Item .env.example .env
```

افتح `.env` وضع المفتاح:

```env
OPENAI_API_KEY=your_key_here
```

ثم أعد تشغيل المشروع. بدون المفتاح تعمل واجهة الصوت باستخدام `SpeechSynthesis` في المتصفح، ويعمل المساعد بوضع محلي بسيط.

## البصمة

زر البصمة داخل صفحة تسجيل الدخول يستدعي `app/fingerprint.py`. تعمل هذه الطريقة عند تشغيل الخادم محليًا على Windows وبوجود Windows Hello مضبوط في إعدادات الجهاز. اسم المستخدم المكتوب يجب أن يكون موجودًا في قاعدة بيانات المشروع.

## ملاحظة الخصوصية

لا تستخدم التعرف على الوجه أو تسجيل الصوت دون موافقة الأشخاص. البيانات البيومترية حساسة، لذلك أضف سياسة موافقة وحذف ومدة احتفاظ قبل عرض المشروع خارج جهازك.
