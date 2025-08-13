/* ====== Base Theme ====== */
:root {
  --bg: #ffffff;
  --fg: #0f172a;      /* Text color */
  --muted: #475569;   /* Secondary text */
  --brand: #0ea5e9;   /* Brand blue */
  --brand-dark: #0284c7;
  --border: #e2e8f0;
  --chip: #f1f5f9;
}

@media (prefers-color-scheme: dark) {
  :root {
    --bg: #0b1220;
    --fg: #e5e7eb;
    --muted: #94a3b8;
    --brand: #38bdf8;
    --brand-dark: #0ea5e9;
    --border: #1f2937;
    --chip: #111827;
  }
}

* {
  box-sizing: border-box;
}
body {
  margin: 0;
  font-family: system-ui, sans-serif;
  background: var(--bg);
  color: var(--fg);
}

/* ====== Header Wrapper ====== */
.site-header {
  position: sticky;
  top: 0;
  z-index: 50;
  background: var(--bg);
  border-bottom: 1px solid var(--border);
  backdrop-filter: saturate(180%) blur(10px);
}
.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 16px;
}

/* ====== Top Bar ====== */
.topbar {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 12px 0;
}
.brand {
  display: flex;
  align-items: center;
  gap: 12px;
  text-decoration: none;
  color: inherit;
}
.brand-mark {
  width: 40px;
  height: 40px;
  border-radius: 12px;
  background: linear-gradient(135deg, var(--brand), var(--brand-dark));
  color: #fff;
  font-weight: 800;
  display: grid;
  place-items: center;
}
.brand-name {
  font-weight: 800;
  font-size: 1.25rem;
}
.brand-tag {
  display: block;
  font-size: 0.72rem;
  color: var(--muted);
}

/* ====== Navigation ====== */
.nav {
  display: flex;
  gap: 12px;
}
.nav a {
  text-decoration: none;
  color: var(--muted);
  padding: 8px 10px;
  border-radius: 10px;
  font-weight: 600;
}
.nav a:hover,
.nav a.active {
  background: var(--chip);
  color: var(--fg);
}

/* ====== Right Utilities ====== */
.utils {
  display: flex;
  align-items: center;
  gap: 10px;
}
.search {
  display: flex;
  align-items: center;
  background: var(--chip);
  border: 1px solid var(--border);
  border-radius: 999px;
  padding: 6px 10px;
}
.search input {
  border: none;
  outline: none;
  background: transparent;
  color: var(--fg);
}
.search button {
  border: none;
  background: transparent;
  color: var(--muted);
  cursor: pointer;
}
.cta {
  background: var(--brand);
  color: #fff;
  border: none;
  padding: 10px 14px;
  border-radius: 12px;
  font-weight: 700;
  cursor: pointer;
}
.menu-btn {
  display: none;
  border: 1px solid var(--border);
  background: var(--chip);
  border-radius: 12px;
  padding: 8px 10px;
}

/* ====== Section Chips ====== */
.sections {
  border-top: 1px solid var(--border);
  display: flex;
  gap: 6px;
  padding: 8px 0;
  overflow-x: auto;
}
.sections::-webkit-scrollbar {
  display: none;
}
.chip {
  padding: 8px 12px;
  border: 1px solid var(--border);
  background: var(--chip);
  border-radius: 999px;
  text-decoration: none;
  color: var(--muted);
  font-weight: 600;
}
.chip:hover,
.chip.active {
  color: var(--fg);
}

/* ====== Mobile Responsive ====== */
@media (max-width: 900px) {
  .nav {
    display: none;
  }
  .menu-btn {
    display: inline-flex;
    align-items: center;
    gap: 6px;
  }
  .search {
    display: none;
  }
}