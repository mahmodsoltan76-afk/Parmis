# استقرار Parmis روی Cloudflare Workers

## روش پیشنهادی: Deploy Button

1. پروژه را در GitHub خودت push کن.
2. در Cloudflare از بخش **Workers & Pages** گزینه **Create application → Workers → Deploy from GitHub** را انتخاب کن.
3. ریپازیتوری `Parmis` و شاخه `main` را انتخاب کن.
4. Build command را خالی بگذار یا `npm ci` قرار بده.
5. Deploy را بزن.

## روش CLI

```bash
npm ci
npx wrangler login
npx wrangler deploy
```

نام Worker در این نسخه `parmis-proxy` است.

## Bindingهای لازم

Worker برای عملکرد کامل به این Bindingها نیاز دارد:

- KV Namespace با نام binding: `KV`
- D1 Database با نام binding: `DB`

در داشبورد Cloudflare:

1. Worker را باز کن.
2. Settings → Bindings برو.
3. یک KV Namespace با variable name برابر `KV` متصل کن.
4. یک D1 Database با variable name برابر `DB` متصل کن.

همچنین در بخش Settings → Variables and Secrets، متغیر اختیاری زیر را اضافه کن:

- `PARMIS_CLAIM_TOKEN`: یک رشته تصادفی قوی برای جلوگیری از تصاحب صفحه نصب اولیه.

تولید توکن:

```bash
openssl rand -hex 16
```

بعد از Deploy، آدرس زیر را باز کن:

```text
https://parmis-proxy.<SUBDOMAIN>.workers.dev/install
```

اگر `PARMIS_CLAIM_TOKEN` تنظیم کرده‌ای:

```text
https://parmis-proxy.<SUBDOMAIN>.workers.dev/install?claim=YOUR_TOKEN
```

> قبل از استفاده عمومی، حتماً رمز ادمین را تنظیم کن و Claim Token را در جای امن نگه دار.
