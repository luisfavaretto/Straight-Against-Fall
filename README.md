/* style.css */
:root {
  --color-bg: #000000;
  --color-red: #c62828;
  --color-gray-light: #b0b0b0;
  --color-gray-dark: #2e2e2e;
  --color-white: #f5f5f5;
  --font-family: 'Montserrat', sans-serif;
  --transition-speed: 0.3s;
}

*,
*::before,
*::after {
  box-sizing: border-box;
}

body {
  margin: 0;
  background-color: var(--color-bg);
  color: var(--color-white);
  font-family: var(--font-family);
  line-height: 1.6;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

.container {
  width: 90%;
  max-width: 1100px;
  margin: 0 auto;
}

/* Header */
header {
  background-color: var(--color-gray-dark);
  border-bottom: 2px solid var(--color-red);
  position: sticky;
  top: 0;
  z-index: 1000;
}

.header-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem 0;
}

.logo h1 {
  font-weight: 700;
  font-size: 1.5rem;
  color: var(--color-red);
  margin: 0;
  letter-spacing: 2px;
  user-select: none;
}

nav ul {
  list-style: none;
  display: flex;
  gap: 1.5rem;
  margin: 0;
  padding: 0;
}

nav a {
  color: var(--color-gray-light);
  text-decoration: none;
  font-weight: 600;
  font-size: 1rem;
  position: relative;
  transition: color var(--transition-speed);
}

nav a::after {
  content: '';
  position: absolute;
  width: 0%;
  height: 2px;
  bottom: -4px;
  left: 0;
  background-color: var(--color-red);
  transition: width var(--transition-speed);
}

nav a:hover,
nav a:focus {
  color: var(--color-red);
  outline: none;
}

nav a:hover::after,
nav a:focus::after {
  width: 100%;
}

/* Hero */
.hero {
  background: linear-gradient(
      rgba(0, 0, 0, 0.7),
      rgba(0, 0, 0, 0.7)
    ),
    url('images/hero-bg.jpg') center center/cover no-repeat;
  color: var(--color-red);
  text-align: center;
  padding: 6rem 1rem 5rem;
  user-select: none;
}

.hero-title {
  font-size: 3rem;
  margin: 0 0 0.5rem;
  font-weight: 900;
  letter-spacing: 4px;
  text-shadow: 0 0 8px var(--color-red);
}

.hero-subtitle {
  font-size: 1.25rem;
  font-weight: 600;
  letter-spacing: 1.5px;
  text-shadow: 0 0 6px var(--color-red);
  margin: 0;
}

/* Sections */
.section {
  padding: 3rem 0 4rem;
  border-bottom: 1px solid var(--color-gray-dark);
}

.section h3 {
  font-size: 2rem;
  color: var(--color-red);
  margin-bottom: 1rem;
  letter-spacing: 2px;
  user-select: none;
}

/* Sobre */
.sobre p {
  max-width: 700px;
  font-size: 1.1rem;
  color: var(--color-gray-light);
  line-height: 1.7;
}

/* Música */
.musica-links {
  list-style: none;
  padding: 0;
  display: flex;
  gap: 1.5rem;
  flex-wrap: wrap;
}

.btn-link {
  display: inline-block;
  background-color: var(--color-red);
  color: var(--color-white);
  padding: 0.75rem 1.5rem;
  border-radius: 4px;
  font-weight: 700;
  text-decoration: none;
  transition: background-color var(--transition-speed), color var(--transition-speed);
  user-select: none;
}

.btn-link:hover,
.btn-link:focus {
  background-color: transparent;
  border: 2px solid var(--color-red);
  color: var(--color-red);
  outline: none;
}

/* Agenda */
.agenda-list {
  list-style: none;
  padding: 0;
  max-width: 400px;
  color: var(--color-gray-light);
  font-size: 1.1rem;
}

.agenda-list li {
  margin-bottom: 0.75rem;
  border-left: 4px solid var(--color-red);
  padding-left: 0.75rem;
  user-select: none;
}

/* Galeria */
.gallery-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
  gap: 1rem;
}

.gallery-grid img {
  width: 100%;
  height: 140px;
  object-fit: cover;
  border-radius: 6px;
  border: 2px solid var(--color-gray-dark);
  transition: transform var(--transition-speed), box-shadow var(--transition-speed);
  cursor: pointer;
  user-select: none;
}

.gallery-grid img:hover,
.gallery-grid img:focus {
  transform: scale(1.05);
  box-shadow: 0 0 12px var(--color-red);
  outline: none;
}

/* Contato */
.contato p {
  font-size: 1.1rem;
  color: var(--color-gray-light);
  margin-bottom: 0.75rem;
  user-select: none;
}

.link {
  color: var(--color-red);
  text-decoration: none;
  font-weight: 600;
  transition: color var(--transition-speed);
}

.link:hover,
.link:focus {
  color: #ff4d4d;
  outline: none;
}

/* Footer */
footer {
  background-color: var(--color-gray-dark);
  text-align: center;
  padding: 1rem 0;
  color: var(--color-gray-light);
  font-size: 0.9rem;
  user-select: none;
}

/* Responsive */
@media (max-width: 768px) {
  .header-container {
    flex-direction: column;
    gap: 0.75rem;
  }

  nav ul {
    flex-direction: column;
    gap: 0.75rem;
    align-items: center;
  }

  .hero-title {
    font-size: 2.25rem;
  }

  .hero-subtitle {
    font-size: 1rem;
  }

  .musica-links {
    justify-content: center;
  }

  .agenda-list {
    max-width: 100%;
  }
}

@media (max-width: 400px) {
  .gallery-grid {
    grid-template-columns: 1fr 1fr;
  }
}
