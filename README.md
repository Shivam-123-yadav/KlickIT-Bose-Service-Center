# Bose Service Centre — Service Booking & E-Commerce Platform

A Django-based service booking and e-commerce platform built for a Bose product retailer, covering
online product sales, customer service appointment booking, and payment processing.

> **Note:** The original production deployment is currently offline due to organisational changes
> at the client company. The application is fully functional and can be redeployed on request. A
> hosted demo link will be added here once available.

The platform processed 500+ customer bookings in its first quarter in production, with a payment
flow designed around server-side callback verification to prevent duplicate or mismatched orders.

---

## Screenshots

<img width="1919" height="956" alt="Home Page" src="https://github.com/user-attachments/assets/1b1fdf83-5ec7-40f8-9a53-1c57744513a3" />

<img width="1920" height="959" alt="Booking Page" src="https://github.com/user-attachments/assets/86a26c75-d46e-423b-8a3f-9f5ec014c733" />

<img width="1920" height="1000" alt="Dashboard" src="https://github.com/user-attachments/assets/afca2932-efcd-42b2-859b-f17966e2f5e7" />

---

## Tech Stack

| Layer | Technology |
|---|---|
| Backend | Python, Django, Django REST Framework |
| Database | MySQL |
| Frontend | HTML, CSS, JavaScript |
| Async / Data | Pandas (CSV product import), Playwright (review scraping) |
| Payments | Cashfree Payment Gateway |
| PDF Generation | WeasyPrint |
| Deployment | Linux VPS, Gunicorn, Nginx |

---

## Key Features

- Product catalogue with categories, colour variants, and image management
- Cart, wishlist, checkout, and order history
- Customer service appointment booking (onsite and offsite visits)
- Cashfree payment integration with server-side callback verification
- CSV-based bulk product import
- Google review scraping for product pages
- Custom Django admin for order, inventory, and appointment management
- SEO: slug-based URLs, sitemap, robots.txt
- Email notifications for orders and bookings
- JWT-ready authentication with custom user model

---

---

## Installation

**Prerequisites:** Python 3.10+, MySQL server, pip

```bash
git clone https://github.com/Shivam-123-yadav/bose-service-centre.git
cd bose-service-centre
```

Create and activate a virtual environment

```bash
python -m venv venv
```

**Windows**
```bash
venv\Scripts\activate
```

**Linux / macOS**
```bash
source venv/bin/activate
```

Install dependencies

```bash
pip install -r requirements.txt
```

### Environment variables

Copy the example environment file and fill in your own values — no credentials are committed to
this repository:

```bash
cp .env.example .env
```

`.env` expects:

```
SECRET_KEY=
DEBUG=True
DB_NAME=
DB_USER=
DB_PASSWORD=
DB_HOST=127.0.0.1
DB_PORT=3306
CASHFREE_APP_ID=
CASHFREE_SECRET_KEY=
EMAIL_HOST_USER=
EMAIL_HOST_PASSWORD=
```

Create the database

```sql
CREATE DATABASE boseservicecentre;
```

Run migrations and create a superuser

```bash
python manage.py migrate
python manage.py createsuperuser
```

Start the development server

```bash
python manage.py runserver
```

Visit `http://127.0.0.1:8000/`

---

## Deployment

The application is configured for standard Django production deployment (Gunicorn + Nginx behind
HTTPS, `DEBUG=False`, `ALLOWED_HOSTS` and `CSRF_TRUSTED_ORIGINS` set per environment). It can be
deployed to any VPS, or to platforms like Render or Railway with a MySQL/PostgreSQL add-on.

---

## License

This project is shared for portfolio and educational purposes.
