# Vegan-Eats: Online Store Backend

Backend of an e-commerce platform for vegan food products, built as the team project for **CS 308 Software Engineering** at Sabancı University (Fall 2024). The team of 6 developed it over five two-week **Scrum** sprints, with sprint planning, reviews and retrospectives.

> This is a fork of the team repository, [cemrekkandemir/Vegan-Eats](https://github.com/cemrekkandemir/Vegan-Eats). The `frontend` folder is a pointer to a separate repository and is not included here.

## Features
- **Product catalogue:** categories, stock tracking (a product cannot be added to the cart beyond available stock) and popularity tracking
- **Cart:** guest carts that merge into the user's cart on login
- **Orders:** placing, cancelling and tracking orders (processing → in-transit → delivered)
- **Payments and invoices:** mock payment and PDF invoices generated with PDFKit
- **Reviews:** ratings and comments that become visible only after product-manager approval
- **Wishlist:** customers with a product in their wishlist are emailed when it is discounted
- **Role-based access:** separate permissions for customers, sales managers and product managers
- **Sales manager tools:** pricing and discounts, invoices by date range, revenue reports, refund approval
- **Product manager tools:** product, category and stock management, delivery list, comment moderation

## Tech stack
Node.js · Express · MongoDB / Mongoose · JWT · bcrypt · Joi · express-session · PDFKit · Nodemailer · Jest · Supertest · mongodb-memory-server

## Project structure
```
Controller/   request handlers (auth, cart, order, payment, product, wishlist)
Middleware/   authentication, guest/user handling, cart merging
Models/       Mongoose schemas (User, Product, Category, Cart, Order)
Routes/       REST API routes
tests/        Jest + Supertest API tests against an in-memory MongoDB
scripts/      data migration helpers
server.js     app entry point
```

## Running locally
```bash
npm install
# create a .env file with MONGO_URI, ACCESS_TOKEN_SECRET, REFRESH_TOKEN_SECRET, SESSION_SECRET and email settings
npm run dev     # start with nodemon
npm test        # run the Jest test suite
```

## My contribution (Sude Kumbasar)
I worked mainly on the backend, with some frontend work:
- **Order and cart APIs:** order placement and the order lifecycle, cart endpoints, and merging a guest's cart into the user's cart on login
- **Role handling:** middleware that separates guest and logged-in user behaviour
- **Delivery management:** the product manager's delivery list and order-status tracking
- **Testing:** co-wrote the Jest/Supertest API tests with a teammate

## Team
Cemre ([cemrekkandemir](https://github.com/cemrekkandemir)) · Hakan Mert Özcan · Nil Sarışık · Ruken Gökçe · Sezin Yılmaz · Sude Kumbasar
