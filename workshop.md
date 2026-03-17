# Personal Portfolio Workshop

Hosted by Jan Rebolledo for CSS & SEA.

[Link to slide presentation](https://www.figma.com/deck/ta8dqRu8qSGhYYO88FIgWV/Jan-for-CSS---SEA---Personal-Website?node-id=1-42&t=wuSt3EkUVWGkS5Td-1)

[Link to design](https://www.figma.com/design/JrVxg7qCZgJhausEqRz3xl/Jan-for-CSS---SEA---Personal-Website?node-id=0-1&t=iHVXTtfxG9oQkNbg-1)

## Scaffolding the project

Initialize Astro project

```sh
npm create astro@latest -- --template minimal
```

Adding project dependencies

```sh
npx astro add tailwind mdx
```

```sh
npm install -D @tailwindcss/typography
```

Create `layouts` & `projects` folders in `/src`

```sh
mkdir ./src/pages/projects && mkdir ./src/layouts
```

Starting the development server

```sh
npm run dev
```

Adding web font

```css
/* globals.css */

@import url('https://fonts.googleapis.com/css2?family=Inter:ital,opsz,wght@0,14..32,100..900;1,14..32,100..900&display=swap');
@import 'tailwindcss';
@plugin "@tailwindcss/typography";

@theme {
  --font-sans: 'Inter', sans-serif;
}

body {
  font-family: 'Inter', sans-serif;
}
```

## Defining the layout

```jsx
// layouts/Layout.astro
---
import '../styles/global.css';

const { title } = Astro.props;
---

<html lang='en'>
  <head>
    <meta charset='utf-8' />
    <link rel='icon' type='image/svg+xml' href='/favicon.svg' />
    <link rel='icon' href='/favicon.ico' />
    <meta name='viewport' content='width=device-width' />
    <meta name='generator' content={Astro.generator} />
    <title>{title}</title>
  </head>
  <body>
    <header
      class='container mx-auto px-6 h-40 flex items-center justify-between'
    >
      <h1>Billy Bronco</h1>
      <div class='hidden md:flex items-center gap-30'>
        <a href='/about'>About</a>
        <a href='/resume.pdf' download='resume.pdf'>Resume</a>
      </div>
      <a href='mailto:bbronco@cpp.edu'>Contact</a>
    </header>
    <slot />
    <footer class='container mx-auto px-6 h-40 flex flex-col gap-6'>
      <p class='font-medium text-xl'>
        &copy; Billy Bronco {new Date().getFullYear()}
      </p>
      <p>
        Get in touch <a href='mailto:bbronco@cpp.edu' class='underline'
          >bbronco@cpp.edu</a
        >
      </p>
      <div class='flex items-center gap-6 text-black/50'>
        <a href='https://github.com/bbronco' target='_blank'>GitHub</a>
        <a href='https://linkedin.com/in/bbronco' target='_blank'>LinkedIn</a>
        <a href='/resume.pdf' download='resume.pdf'>Resume</a>
      </div>
    </footer>
  </body>
</html>

```
