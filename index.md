# Assignment 9.3 — Combine Flexbox and Grid Responsively

## Objective

Create a responsive landing page using CSS Grid and Flexbox. The page should display multiple columns on larger screens and switch to a single-column layout on mobile screens.

## 1. HTML Code (`index.html`)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Creative Landing Page</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <header class="header">
        <a href="#" class="logo">CreativeSpace</a>

        <nav class="navbar">
            <a href="#home">Home</a>
            <a href="#features">Features</a>
            <a href="#about">About</a>
            <a href="#contact">Contact</a>
        </nav>

        <a href="#features" class="header-button">Get Started</a>
    </header>

    <main>
        <section class="hero" id="home">
            <div class="hero-content">
                <p class="eyebrow">WELCOME TO CREATIVESPACE</p>
                <h1>Build Something Amazing</h1>
                <p class="hero-description">
                    Discover creative ideas, useful tools, and simple
                    solutions to bring your next project to life.
                </p>
                <div class="hero-actions">
                    <a href="#features" class="button primary-button">Explore Features</a>
                    <a href="#about" class="button secondary-button">Learn More</a>
                </div>
            </div>

            <div class="hero-image">
                <img
                    src="https://images.unsplash.com/photo-1497366754035-f200968a6e72?auto=format&fit=crop&w=1000&q=80"
                    alt="Modern creative workspace"
                >
            </div>
        </section>

        <section class="features section-container" id="features">
            <div class="section-heading">
                <p class="eyebrow">WHAT WE OFFER</p>
                <h2>Our Key Features</h2>
                <p>Everything you need to start creating and growing.</p>
            </div>

            <div class="feature-grid">
                <article class="feature-card">
                    <div class="feature-icon">🎨</div>
                    <div class="feature-content">
                        <h3>Creative Design</h3>
                        <p>Create clean and attractive designs for your projects.</p>
                    </div>
                </article>

                <article class="feature-card">
                    <div class="feature-icon">📱</div>
                    <div class="feature-content">
                        <h3>Responsive Layout</h3>
                        <p>Make your website work smoothly across different screens.</p>
                    </div>
                </article>

                <article class="feature-card">
                    <div class="feature-icon">⚡</div>
                    <div class="feature-content">
                        <h3>Fast Performance</h3>
                        <p>Build simple experiences that are easy to navigate.</p>
                    </div>
                </article>

                <article class="feature-card">
                    <div class="feature-icon">🔒</div>
                    <div class="feature-content">
                        <h3>Safe Experience</h3>
                        <p>Follow good practices to create a reliable website.</p>
                    </div>
                </article>
            </div>
        </section>

        <section class="about" id="about">
            <div class="about-content">
                <h2>Designed for Your Ideas</h2>
                <p>
                    CreativeSpace is a sample landing page that demonstrates
                    how CSS Grid and Flexbox can work together to create
                    a clean, responsive website.
                </p>
            </div>
        </section>
    </main>

    <footer class="footer" id="contact">
        <p>&copy; 2026 CreativeSpace. All rights reserved.</p>
        <a href="#home">Back to top ↑</a>
    </footer>

</body>
</html>
```

## 2. CSS Code (`style.css`)

```css
/* General styles */
* {
    box-sizing: border-box;
}

html {
    scroll-behavior: smooth;
}

body {
    margin: 0;
    font-family: Arial, sans-serif;
    line-height: 1.6;
    color: #1f2937;
    background-color: #ffffff;
}

a {
    text-decoration: none;
}

img {
    display: block;
    max-width: 100%;
}

/* Header and navbar using Flexbox */
.header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-wrap: wrap;
    gap: 18px;
    padding: 18px 5%;
    background-color: #ffffff;
    border-bottom: 1px solid #e5e7eb;
}

.logo {
    color: #4338ca;
    font-size: 1.5rem;
    font-weight: bold;
}

.navbar {
    display: flex;
    align-items: center;
    flex-wrap: wrap;
    gap: 22px;
}

.navbar a {
    color: #374151;
    font-size: 0.95rem;
}

.navbar a:hover {
    color: #4338ca;
}

.header-button {
    padding: 10px 16px;
    color: white;
    background-color: #4338ca;
    border-radius: 7px;
}

/* Hero section using Grid */
.hero {
    display: grid;
    grid-template-columns: minmax(0, 1fr) minmax(0, 1fr);
    align-items: center;
    gap: 40px;
    max-width: 1200px;
    margin: 0 auto;
    padding: 65px 5%;
}

.hero-content {
    min-width: 0;
}

.eyebrow {
    color: #4338ca;
    font-size: 0.8rem;
    font-weight: bold;
    letter-spacing: 1.5px;
}

.hero h1 {
    margin: 12px 0;
    font-size: clamp(2rem, 4vw, 3.5rem);
    line-height: 1.15;
}

.hero-description {
    max-width: 520px;
    color: #6b7280;
    font-size: 1.1rem;
}

.hero-actions {
    display: flex;
    align-items: center;
    flex-wrap: wrap;
    gap: 12px;
    margin-top: 25px;
}

.button {
    display: inline-block;
    padding: 12px 18px;
    border: 2px solid #4338ca;
    border-radius: 7px;
    font-weight: bold;
}

.primary-button {
    color: white;
    background-color: #4338ca;
}

.secondary-button {
    color: #4338ca;
    background-color: white;
}

.hero-image {
    min-width: 0;
}

.hero-image img {
    width: 100%;
    aspect-ratio: 4 / 3;
    object-fit: cover;
    border-radius: 16px;
}

/* Features section */
.section-container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 45px 5%;
}

.features {
    background-color: #f8fafc;
}

.section-heading {
    margin-bottom: 30px;
    text-align: center;
}

.section-heading h2,
.about h2 {
    margin: 8px 0;
    font-size: clamp(1.7rem, 3vw, 2.4rem);
}

/* Main feature layout using Grid */
.feature-grid {
    display: grid;
    grid-template-columns: repeat(2, minmax(0, 1fr));
    gap: 22px;
}

/* Flexbox inside each feature card */
.feature-card {
    display: flex;
    align-items: flex-start;
    gap: 16px;
    min-width: 0;
    padding: 24px;
    background-color: white;
    border: 1px solid #e5e7eb;
    border-radius: 12px;
}

.feature-icon {
    display: flex;
    flex-shrink: 0;
    align-items: center;
    justify-content: center;
    width: 50px;
    height: 50px;
    background-color: #eef2ff;
    border-radius: 10px;
    font-size: 1.5rem;
}

.feature-content {
    min-width: 0;
    overflow-wrap: anywhere;
}

.feature-content h3 {
    margin: 0 0 8px;
    font-size: 1.15rem;
}

.feature-content p {
    margin: 0;
    color: #6b7280;
}

/* About section */
.about {
    padding: 55px 5%;
    text-align: center;
    background-color: #eef2ff;
}

.about-content {
    max-width: 750px;
    margin: 0 auto;
}

.about-content p {
    color: #4b5563;
}

/* Footer */
.footer {
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-wrap: wrap;
    gap: 12px;
    padding: 22px 5%;
    color: white;
    background-color: #1f2937;
}

.footer p {
    margin: 0;
}

.footer a {
    color: #c7d2fe;
}

/* Tablet layout */
@media (max-width: 900px) {
    .header {
        padding: 16px 4%;
    }

    .navbar {
        gap: 14px;
    }

    .hero {
        gap: 25px;
        padding: 45px 4%;
    }

    .feature-grid {
        gap: 16px;
    }

    .feature-card {
        padding: 18px;
    }
}

/* Mobile layout */
@media (max-width: 600px) {
    .header {
        flex-direction: column;
        align-items: stretch;
        text-align: center;
    }

    .navbar {
        justify-content: center;
        gap: 12px 18px;
    }

    .header-button {
        align-self: center;
    }

    .hero {
        grid-template-columns: minmax(0, 1fr);
        gap: 25px;
        padding: 35px 5%;
    }

    .hero-content {
        text-align: center;
    }

    .hero-description {
        margin-right: auto;
        margin-left: auto;
    }

    .hero-actions {
        justify-content: center;
    }

    .feature-grid {
        grid-template-columns: minmax(0, 1fr);
        gap: 15px;
    }

    .section-container {
        padding: 35px 5%;
    }

    .about {
        padding: 35px 5%;
    }

    .footer {
        flex-direction: column;
        text-align: center;
    }
}
```

## 3. Requirements Completed

* Created a header and navigation bar using Flexbox.
* Arranged text and an image in the hero section using CSS Grid.
* Added four feature cards.
* Used Grid for the main hero and feature layouts.
* Used Flexbox for navigation, hero buttons, and card contents.
* Changed the hero and feature layouts to a single column on mobile.
* Added tablet and mobile media queries.
* Used `minmax()`, `fr`, `gap`, and `clamp()` for flexible sizing and spacing.
* Added image sizing and text-overflow safeguards.

## 4. Testing

1. Open `index.html` in a browser.
2. Check that the navigation and hero section align correctly on desktop.
3. Confirm that all four feature cards appear.
4. Resize the browser to tablet width and check the spacing.
5. Resize it to mobile width and confirm that the hero and cards stack vertically.
6. Check for horizontal scrolling, overlapping text, and image overflow.
7. Take desktop and mobile screenshots.

## Result

A responsive landing page was created using CSS Grid for the main layout and Flexbox for navigation, buttons, and card contents.

## Submission

* `Assignment-9.3.md`
* `index.html`
* `style.css`
* Desktop screenshot
* Mobile screenshot
*