# Aprozar Digital

A minimal Django 5 project for a small greengrocer-style shop. It includes a `products` app with `Product` and `Offer` models and a simple Bootstrap UI that lists products with image, name and price.

---

## Features

- Django 5.2 project (`AprozarDigital`) with one app: `products`
- Models: `Product(name, price, stock, image_url)`, `Offer(code, description, discount)`
- URLs:
  - `/products/` – list all products (template-based view)
  - `/admin/` – Django admin
- Templates with Bootstrap 5 (CDN)
- SQLite by default

---

## Tech stack

- Python 3.11+ (recommended)
- Django 5.2.x
- Bootstrap 5 for styling (CDN)

---

## Project layout

- Aprozar Digital/
- ├─ AprozarDigital/
- │ ├─ settings.py
- │ ├─ urls.py
- │ └─ wsgi.py
- ├─ products/
- │ ├─ models.py # Product, Offer
- │ ├─ views.py # index view -> /products/
- │ ├─ urls.py
- │ ├─ templates/
- │ │ └─ index.html # lists products
- │ └─ migrations/ # Django migrations
- ├─ templates/
-  └─ base.html # Bootstrap layout
- ├─ manage.py
- └─ db.sqlite3 # local dev only (ignored by Git)

---

## Getting started

1. **Create & activate a virtual environment**
   ```bash```
   python -m venv .venv
   # Windows
   .venv\\Scripts\\activate
   # macOS/Linux
   source .venv/bin/activate

2. **Install dependencies**
- pip install "Django>=5.2,<6"
- pip freeze > requirements.txt

3. **Run migrations**
- python manage.py migrate

4. **Create a superuser (to access /admin)**
- python manage.py createsuperuser

5. **Start the development server**
- python manage.py runserver

Visit http://127.0.0.1:8000/products and http://127.0.0.1:8000/admin

---

## Environment variables

- The project uses Django defaults (DEBUG=True in dev). If you add secrets or production settings, keep them in a .env file and ensure it’s not committed (see .gitignore).

Typical values you might introduce later:
- SECRET_KEY=replace-me
- DEBUG=False
- ALLOWED_HOSTS=your-domain.com
- DATABASE_URL=postgres://...

---

## Data & admin

Add products via the Django admin or the shell:
- python manage.py shell
- from products.models import Product
- Product.objects.create(name="Bananas", price=2.49, stock=50, image_url="https://example.com/banana.jpg")

---

## Tests

Add tests under products/tests.py and run:
- python manage.py test

---

## Deployment notes

- Switch to Postgres in production (via DATABASE_URL or settings.py changes).
- Set DEBUG=False and configure ALLOWED_HOSTS.
- Serve static files with WhiteNoise or the web server; collect them with:

---

## Contributing

Issues and PRs are welcome. Please follow typical Python/Django code style and keep commits focused.

---

## License

MIT — see LICENSE

---

## Write files

- (proj_root / ".gitignore").write_text(gitignore_content, encoding="utf-8")
- (proj_root / "LICENSE").write_text(license_content, encoding="utf-8")
- (proj_root / "README.md").write_text(readme_content, encoding="utf-8")

---

## Return file sizes for confirmation

- {p.name: p.stat().st_size for p in [proj_root/".gitignore", proj_root/"LICENSE", proj_root/"README.md"]}
- {'.gitignore': 541, 'LICENSE': 1063, 'README.md': 3092}
