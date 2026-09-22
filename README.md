# n8n GOD Architect v58

**معمار، سازنده و موتور کنترل کیفیت سیستم‌های حرفه‌ای n8n**

`n8n GOD Architect` یک Skill پیشرفته برای طراحی، ساخت، بررسی، دیباگ، امن‌سازی، تست، استقرار و مدیریت سیستم‌های واقعی مبتنی بر n8n است. این ابزار نیاز کسب‌وکار را به معماری اجرایی، Workflowهای قابل Import، قراردادهای داده، سیستم مدیریت خطا، برنامه تست، مستندات عملیاتی و بسته انتشار قابل‌ردیابی تبدیل می‌کند.

این پروژه صرفاً یک Workflow Generator نیست. هدف آن ساخت اتوماسیون‌هایی است که در شرایط واقعی قابل اعتماد، قابل بازیابی، قابل مانیتورینگ و قابل توسعه باشند.

## چه سیستم‌هایی می‌تواند بسازد؟

* Workflowهای ساده و چندمرحله‌ای n8n
* AI Agentها و سیستم‌های چندعاملی
* Webhookها و API Integrationهای امن
* CRM و سیستم‌های مدیریت لید
* Voice-to-CRM و پردازش صوت
* سیستم‌های Scraping و جمع‌آوری داده
* ETL و Data Pipeline
* اتصال PostgreSQL، Redis، Supabase و سرویس‌های خارجی
* MCP Server و MCP Integration
* سیستم‌های Queue Mode و Worker-Based
* داشبوردهای عملیاتی و مدیریتی
* سیستم‌های اعلان، پیگیری، تأیید انسانی و Automation
* زیرساخت‌های آماده Staging و Production

## قابلیت‌های کلیدی

### معماری هوشمند

نیاز کسب‌وکار را تحلیل می‌کند و متناسب با شرایط، معماری مناسب را از میان الگوهای زیر انتخاب می‌کند:

* Webhook Processing
* Async Job Processing
* Controller/Worker
* Queue Mode
* Batch Processing
* Transactional Outbox
* Saga و Compensation
* DLQ و Quarantine
* Reconciliation
* Human Approval
* Bounded AI Agent Loop

### ساخت Artifact واقعی

برای پروژه‌های حرفه‌ای فقط توضیح متنی تولید نمی‌کند؛ بلکه مجموعه‌ای از فایل‌های قابل استفاده می‌سازد:

* Workflow JSON
* Manifest
* Evidence Ledger
* Database Schema و Migration
* Test Fixtures
* Error Workflow
* Validation Report
* Deployment Configuration
* Rollback Plan
* SLO و Alert Rules
* Runbook
* Release Package

### اعتبارسنجی قطعی Workflow

ابزار داخلی `validate_workflow.py` موارد زیر را بررسی می‌کند:

* معتبر بودن JSON
* اتصال صحیح Nodeها
* نبود Node ID یا نام تکراری
* وجود `typeVersion`
* صحت Credential Referenceها
* تکراری نبودن مسیر Webhook
* محدود بودن Retry
* وجود تنظیمات اجرایی
* وضعیت Error Workflow
* Secretهای احتمالی
* خطرهای مربوط به Agent Loop
* استفاده نادرست از Continue On Fail

### امتیازدهی آمادگی Production

ابزار `score_readiness.py` پروژه را در ده حوزه ارزیابی می‌کند:

* تطابق با نیاز کسب‌وکار
* معماری
* صحت عملکرد
* پایداری و بازیابی
* امنیت و حریم خصوصی
* مانیتورینگ و عملیات
* عملکرد و مقیاس‌پذیری
* هزینه
* نگهداری‌پذیری
* مستندات و مالکیت

سپس وضعیت واقعی سیستم را مشخص می‌کند:

* Prototype
* Staging Only
* Production Release Candidate
* Production Ready
* Production Proven

### سیستم Evidence واقعی

این Skill بین «ساخته‌شدن فایل»، «موفقیت Import»، «اجرای Workflow» و «موفقیت واقعی کسب‌وکار» تفاوت قائل می‌شود.

سطوح شواهد:

* `E0`: فرض یا ادعا
* `E1`: مستندات رسمی
* `E2`: اعتبارسنجی ایستا
* `E3`: اجرای Fixture و تست منطقی
* `E4`: تست یکپارچه Sandbox
* `E5`: تست کامل Staging، امنیت، بار و بازیابی
* `E6`: داده واقعی Production در بازه مانیتورینگ

هیچ سیستم بدون شواهد `E5`، امتیاز حداقل ۸۵، امنیت و پایداری بالاتر از ۸۰ درصد و نبود Hard Blocker با عنوان Production-ready معرفی نمی‌شود.

### امنیت از ابتدا

کنترل‌های امنیتی پروژه شامل موارد زیر است:

* جلوگیری از قرارگرفتن Secret داخل Workflow
* Credential Reference استاندارد
* Webhook Authentication
* Replay Protection
* Rate Limiting
* Least Privilege
* Data Redaction
* Retention Policy
* SSRF و Network Control
* Tenant Isolation
* Approval برای عملیات حساس
* Prompt Injection Defense
* AI Tool Allowlist
* Structured Output Validation
* جلوگیری از دسترسی مدل به Credentialها

### پایداری و بازیابی

برای Side Effectها، APIها و عملیات حساس موارد زیر طراحی می‌شود:

* Idempotency Key
* Bounded Retry
* Exponential Backoff
* Jitter
* Timeout
* Unknown Outcome Handling
* DLQ
* Reconciliation
* Stale Lock Recovery
* Checkpoint
* Compensation
* Backup
* Restore
* Rollback

### AI Agent و MCP

برای Agentها و ابزارهای MCP محدودیت‌های مشخصی اعمال می‌شود:

* حداکثر تعداد Step
* Timeout
* Token Budget
* Tool Budget
* Termination Condition
* Tool Schema
* Permission Boundary
* Human Approval
* Memory Scope
* Prompt Injection Protection
* Regression Evaluation
* جلوگیری از Excessive Agency

## ابزارهای داخلی

* `validate_workflow.py`
  اعتبارسنجی ایستای پروژه‌ها و Workflowهای n8n

* `score_readiness.py`
  محاسبه امتیاز و وضعیت واقعی آمادگی Production

* `build_release_bundle.py`
  ساخت ZIP انتشار همراه با Secret Scan و `MANIFEST.sha256`

* `validate_package.py`
  بررسی سلامت ساختاری خود Skill

## Production Gates

فرایند انتشار با Gateهای اجباری کنترل می‌شود:

* `G0`: تکمیل اطلاعات ورودی
* `G1`: تأیید معماری
* `G2`: اعتبارسنجی ایستا
* `G3`: تست عملکرد
* `G4`: بررسی امنیت
* `G5`: تست پایداری و بازیابی
* `G6`: تست بار و هزینه
* `G7`: تأیید انتشار
* `G8`: Smoke Test
* `G9`: پایان بازه مانیتورینگ

شکست هر Gate می‌تواند انتشار Production را متوقف کند.

## فلسفه پروژه

اصل مرکزی این سیستم ساده است:

> نبود شواهد، به معنی موفقیت نیست.

ساخته‌شدن JSON به معنی کارکردن Workflow نیست.
موفقیت Import به معنی سازگاری کامل نیست.
پاسخ HTTP موفق به معنی تکمیل نتیجه کسب‌وکار نیست.
اجرای سبز n8n نیز تضمین نمی‌کند که Side Effect درست، بدون تکرار و قابل بازیابی انجام شده باشد.

`n8n GOD Architect` برای ساخت اتوماسیون‌هایی طراحی شده است که فقط روی Canvas زیبا نیستند؛ بلکه در دنیای واقعی قابل اعتماد، امن، قابل اندازه‌گیری و قابل نگهداری هستند.
