# Como iniciarlo

Iniciar proyecto con `Vite`

```sh
npm init vite@latest
```

Cd nuestro proyecto

```sh
cd PROYECTO
```

instalar dependencias

```sh
npm i
```

Instalamos `TailwindCSS`

```sh
npm i -D tailwindcss postcss autoprefixer
```

Generamos `tailwind.config.js`

```sh
npx tailwindcss init -p 
```

Creamos un archivo `./src/index.css`

Ponemos dentro

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```