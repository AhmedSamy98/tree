# دليل استخدام أمر `tree` في سطر الأوامر

## مقدمة
أمر `tree` هو أداة قوية لعرض بنية الملفات والمجلدات في نظام التشغيل بطريقة شجرية منظمة. يستخدم هذا الأمر عادةً لفهم هيكلة المشاريع البرمجية أو تنظيم الملفات داخل مجلد معين.

## تثبيت `tree`
### على Linux (Debian/Ubuntu)
```bash
sudo apt install tree
```
### على macOS (باستخدام Homebrew)
```bash
brew install tree
```
### على Windows (داخل Git Bash أو WSL)
```bash
pacman -S tree  # إذا كنت تستخدم MSYS2
```

## استخدام `tree`

### 1. عرض جميع الملفات والمجلدات في المجلد الحالي
```bash
tree
```
هذا الأمر يعرض جميع الملفات والمجلدات داخل المجلد الذي تعمل فيه حاليًا.

### 2. عرض جميع المجلدات فقط بدون الملفات
```bash
tree /path/to/directory -d
```
هذا الخيار مفيد إذا كنت تريد رؤية بنية المجلدات فقط دون عرض الملفات.

### 3. عرض جميع المجلدات والملفات بما في ذلك الملفات المخفية
```bash
tree /path/to/directory -a
```
هذا الخيار يعرض جميع الملفات، بما في ذلك الملفات التي تبدأ بنقطة `.` والتي تكون مخفية عادةً في أنظمة Linux وmacOS.

### 4. تحديد عدد المستويات في العمق (مثلاً مستويين فقط)
```bash
tree /path/to/directory -L 2
```
يمكنك تغيير الرقم `2` لأي عدد آخر لتحديد عدد المستويات التي سيتم عرضها.

### 5. إظهار تفاصيل الملفات (مثل الحجم والتاريخ)
```bash
tree /path/to/directory -h
```
هذا الخيار يعرض أحجام الملفات بطريقة سهلة القراءة (KB, MB, GB).

## تشغيل `tree` على مجلد معين
إذا كنت تريد تشغيل `tree` على مجلد معين بدلًا من المجلد الحالي، يمكنك تحديد المسار بعد الأمر، مثل:
```bash
tree /path/to/directory
```
على سبيل المثال، لعرض بنية الملفات داخل مجلد `projects`:
```bash
tree ~/projects
```

## حفظ نتيجة `tree` في ملف خارجي
يمكنك حفظ نتيجة تنفيذ `tree` في ملف نصي لاستخدامه لاحقًا أو لمشاركته مع الآخرين:
```bash
tree /path/to/directory > structure.txt
```
هذا الأمر يقوم بحفظ الإخراج في ملف **structure.txt** داخل المجلد الحالي.

### حفظ النتائج مع خيارات متقدمة
إذا كنت تريد حفظ النتائج مع تفاصيل الملفات، يمكنك تنفيذ:
```bash
tree /path/to/directory -h > structure.txt
```
أما إذا كنت تريد تصدير النتائج إلى ملف مع دعم UTF-8 لمنع المشاكل في التشفير:
```bash
tree /path/to/directory -h | tee structure.txt
```

## مشاركة الملف مع الآخرين
بمجرد حفظ النتيجة في ملف، يمكنك مشاركته عبر البريد الإلكتروني أو رفعه على GitHub أو أي منصة أخرى. إذا كنت ترغب في عرضه داخل GitHub مع تنسيق مناسب، يمكنك حفظه بامتداد `.md` واستخدام كود التنسيق:
```markdown
```
tree -L 2
```
```

## ملاحظات هامة
1. في **Windows PowerShell**، استخدم `tree /F` لعرض الملفات والمجلدات.
2. في **Windows CMD**، استخدم `tree /A` للحصول على إخراج بدون أحرف خاصة.
3. عند تنفيذ الأوامر في PowerShell، تجنب استخدام الشرطات (`-d`, `-a`, `-h`) مباشرة بعد `tree` بدون تحديد مسار المجلد، حيث قد لا يعمل بشكل صحيح.

## خاتمة
أمر `tree` هو أداة رائعة لفهم بنية الملفات والمجلدات بسرعة. باستخدام الخيارات المختلفة المذكورة أعلاه، يمكنك تخصيص الإخراج ليلائم احتياجاتك كمبرمج أو مدير ملفات.

