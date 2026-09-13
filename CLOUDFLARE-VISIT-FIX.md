# رفع صفحه There is nothing here yet

این پروژه باید به‌عنوان Cloudflare Worker دیپلوی شود، نه Pages Static.

تنظیمات Build:
- Root directory: /
- Install command: npm install --no-audit --no-fund
- Build command: npm run build
- Deploy command: npx wrangler deploy --config wrangler.jsonc
- Node.js: 20

نام Worker در این نسخه `parmis` است. بعد از دیپلوی، آدرس صحیح باید از صفحه Workers > parmis > Deployments > Visit گرفته شود.

اگر در داشبورد Pages پروژه‌ای با نام parmis ساخته‌اید، آن پروژه را برای این سورس استفاده نکنید؛ این سورس با Wrangler به Workers دیپلوی می‌شود.
