```markdown
# TRL TEAM FOR DEVELOPMENT

الموقع الرسمي لفريق TRL TEAM FOR DEVELOPMENT — من تطوير وقائد الفريق Taimdev9.

Official website of TRL TEAM FOR DEVELOPMENT — developed and led by Taimdev9.

- الموقع | Website: https://taimdev9.github.io
- GitHub: https://github.com/Taimdev9

---

## عن الموقع | About

هذا الموقع عبارة عن معرض شخصي للمشاريع البرمجية مفتوحة المصدر الخاصة بـ Taimdev9 وفريق TRL TEAM FOR DEVELOPMENT. تم بناؤه باستخدام HTML و CSS و JavaScript فقط، بدون أي مكتبات أو أدوات بناء خارجية. يقوم الموقع بجلب جميع المستودعات العامة من حساب GitHub تلقائيًا وعرضها في بطاقات أنيقة، مع تصميم بسيط بالأبيض والأسود والرمادي.

This is a personal portfolio website for the open-source projects of Taimdev9 and TRL TEAM FOR DEVELOPMENT. It is built with pure HTML, CSS, and JavaScript — no frameworks, no build tools, no dependencies. The site automatically fetches all public repositories from the GitHub account and displays them in clean cards, with a minimal black, white, and gray design.

---

## المميزات | Features

- تصميم بسيط بالأبيض والأسود والرمادي | Minimal black, white, and gray design
- بدون أي مكتبات خارجية | Zero dependencies
- متوافق مع الجوال والحاسوب | Fully responsive
- يجلب المشاريع تلقائيًا من GitHub | Auto-fetches projects from GitHub
- ترتيب المشاريع حسب النجوم ثم آخر تحديث | Sorted by stars, then by last update
- قوانين وإخلاء مسؤولية بالعربي والإنجليزي | Bilingual legal terms and disclaimers
- دعم كامل للغة العربية (RTL) | Full RTL support for Arabic
- خفيف جدًا وسريع التحميل | Very lightweight and fast

---

## التخصيص | Customization

### تغيير اسم المستخدم | Change the GitHub username

افتح ملف index.html وابحث عن السطر التالي:

Open index.html and find the following line:

```javascript
const USERNAME = 'Taimdev9';
```

استبدل Taimdev9 باسم المستخدم الخاص بك.

Replace Taimdev9 with your own GitHub username.

استثناء مستودع معين من العرض | Exclude a specific repository

ابحث عن هذا السطر في ملف index.html:

Find this line in index.html:

```javascript
const filtered = repos.filter(r => !r.fork && !r.name.endsWith('.github.io'));
```

لاستثناء مستودع اسمه my-private-repo غيّره إلى:

To exclude a repo named my-private-repo, change it to:

```javascript
const filtered = repos.filter(r => !r.fork && !r.name.endsWith('.github.io') && r.name !== 'my-private-repo');
```

تغيير الألوان | Change the color palette

عدّل متغيرات CSS في أعلى وسم style:

Edit the CSS variables at the top of the style tag:

```css
:root {
  --bg: #0a0a0a;
  --surface: #141414;
  --surface-2: #1c1c1c;
  --border: #2a2a2a;
  --text: #e0e0e0;
  --text-dim: #888888;
  --accent: #ffffff;
}
```

تغيير اسم الفريق | Change the team name

ابحث عن TRL TEAM FOR DEVELOPMENT في ملف index.html واستبدله باسم فريقك، ولا تنسَ تحديث وسم title.

Search for TRL TEAM FOR DEVELOPMENT in index.html and replace it with your own team name, and don't forget to update the title tag.

---

هيكل المشروع | Project Structure

```
Taimdev9.github.io/
│
├── index.html      # الموقع كامل (HTML + CSS + JS في ملف واحد) | The entire website in one file
└── README.md       # هذا الملف | This file
```

ملف واحد فقط يكفي لعمل الموقع. لا توجد أدوات بناء ولا مكتبات ولا ملفات إعدادات.

Only one file is needed for the site to work. No build tools, no dependencies, no configuration files.

---

كيف يعمل الاتصال بـ GitHub API | How the GitHub API Integration Works

يقوم الموقع بجلب المستودعات العامة عند تحميل الصفحة عبر:

The site fetches public repositories on page load using:

```
GET https://api.github.com/users/{USERNAME}/repos?sort=updated&per_page=100
```

لا يحتاج أي مصادقة للمستودعات العامة. الحد الأقصى بدون مصادقة هو 60 طلبًا في الساعة لكل عنوان IP، وهو أكثر من كافٍ لموقع شخصي.

No authentication is required for public repositories. The unauthenticated limit is 60 requests per hour per IP address, which is more than enough for a personal portfolio site.

يتم استثناء المستودعات التالية من العرض:

The following repositories are excluded from the display:

· المستودعات المنسوخة (Forks) | Forked repositories
· مستودع الموقع نفسه (لتجنب التكرار) | The site's own repository (to avoid recursion)

يتم ترتيب الباقي حسب عدد النجوم تنازليًا ثم حسب تاريخ آخر تحديث.

The rest are sorted by star count descending, then by last update date.

---

إخلاء المسؤولية | Disclaimer

بالعربية

هذا الموقع عبارة عن معرض شخصي للمشاريع البرمجية مفتوحة المصدر الخاصة بـ Taimdev9 وفريق TRL TEAM FOR DEVELOPMENT. يتم توفير جميع الأكواد والمشاريع كما هي دون أي ضمانات من أي نوع، صريحة أو ضمنية.

أنا غير مسؤول عن أي استخدام غير قانوني أو ضار أو غير مصرح به لأي من الأكواد أو المشاريع المعروضة هنا. أي شخص يستخدم هذه المشاريع يتحمل المسؤولية الكاملة عن أفعاله وعواقبها.

· لا يُسمح بإساءة استخدام الموقع أو محاولة اختراقه أو تعطيله.
· جميع المشاريع مفتوحة المصدر تخضع لشروط الترخيص المذكورة في مستودع كل مشروع على حدة.
· الروابط الخارجية مثل GitHub لا نتحكم في محتواها ولا نتحمل مسؤوليتها.
· المحتوى مقدم لأغراض معلوماتية وتعليمية فقط.

باستخدامك هذا الموقع فإنك توافق على هذه الشروط. إذا كنت لا توافق، يرجى عدم استخدام الموقع.

In English

This website is a personal showcase of open-source software projects by Taimdev9 and TRL TEAM FOR DEVELOPMENT. All code and projects are provided as is, without warranty of any kind, express or implied.

I am not responsible for any illegal, harmful, or unauthorized use of any code or project displayed here. Any person who uses these projects assumes full responsibility for their actions and consequences.

· Abuse of this site, attempts to hack it, or disrupt it are strictly prohibited.
· All open-source projects are governed by the license terms stated in their respective repositories on GitHub.
· External links such as GitHub are not under our control, and we assume no responsibility for their content.
· Content is provided for informational and educational purposes only.

By using this site, you agree to these terms. If you do not agree, please do not use the site.

---

حقوق النشر | Copyright

© 2026 TRL TEAM FOR DEVELOPMENT — جميع الحقوق محفوظة | All rights reserved.

المطور وقائد الفريق | Developer and Team Leader: Taimdev9

لا يُسمح بنسخ أو إعادة نشر تصميم أو هوية أو محتوى هذا الموقع دون إذن كتابي صريح من Taimdev9. المشاريع الفردية المعروضة قد تخضع لتراخيصها الخاصة، راجع مستودع كل مشروع للتفاصيل.

You may not copy, redistribute, or republish the design, branding, or content of this website without explicit written permission from Taimdev9. Individual projects listed on this site may have their own licenses — refer to each project's repository for details.

---

شكر وتقدير | Acknowledgements

· مبني باستخدام HTML و CSS و JavaScript فقط | Built with pure HTML, CSS, and Vanilla JavaScript
· يعتمد على GitHub REST API | Powered by the GitHub REST API
· مستضاف مجانًا على GitHub Pages | Hosted for free on GitHub Pages
· مصمم بلوحة أحادية اللون لأقصى وضوح وسرعة | Designed with a minimal monochrome palette for maximum clarity and speed

---

التواصل | Contact

· GitHub: https://github.com/Taimdev9
· Website: https://taimdev9.github.io

للتعاون أو الاستفسارات أو الإبلاغ عن مشاكل، يرجى فتح Issue على المستودع المعني أو التواصل عبر GitHub.

For collaborations, inquiries, or bug reports, please open an issue on the relevant repository or reach out via GitHub.

```