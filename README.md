# personal portfolio workshop 🌐

<video controls width="640">
  <source src="https://github.com/janrebolledo/portfolio-workshop/raw/refs/heads/main/demo.mov" type="video/mp4">
  your browser does not support the video tag.
</video>

intro:
what is a personal portfolio, why build one, project visibility & personal branding, how will we design it, what tools we use (astro, tailwind, markdown)

resources:

- [astro docs](https://docs.astro.build/)
- [tailwind docs](https://tailwindcss.com/docs)
- [workshop slides](https://www.figma.com/deck/ta8dqRu8qSGhYYO88FIgWV/Jan-for-CSS---SEA---Personal-Website?node-id=1-42&t=wuSt3EkUVWGkS5Td-1)
- [figma design](https://www.figma.com/design/JrVxg7qCZgJhausEqRz3xl/Jan-for-CSS---SEA---Personal-Website?node-id=0-1&t=iHVXTtfxG9oQkNbg-1)

prereqs:

- [vscode](https://code.visualstudio.com/download)
- [node + npm](https://nodejs.org/en/download)

post workshop exploration:

- add an about page
- [connect a cms](https://docs.astro.build/en/guides/cms/) for managing content

<details>
<summary>scaffolding the project from scratch</summary>

initialize astro project

```sh
npm create astro@latest -- --template minimal
```

add project dependencies

```sh
npx astro add tailwind mdx
```

```sh
npm install -D @tailwindcss/typography
```

create `layouts` & `projects` folders in `/src`

```sh
mkdir ./src/pages/projects && mkdir ./src/layouts
```

start the development server

```sh
npm run dev
```

add a web font

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

@view-transition {
  navigation: auto;
}
```

</details>

## defining the layout

the home page automatically picks up any `.md` file in the `projects/` folder 🌱

created with 🫶 by jan rebolledo, for software engineering association & computer science society @ california state polytechnic university, pomona
