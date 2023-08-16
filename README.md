# Nuxt 3 Minimal Starter

Look at the [Nuxt 3 documentation](https://nuxt.com/docs/getting-started/introduction) to learn more.

## Setup

Make sure to install the dependencies:

```bash
# npm
npm install

# pnpm
pnpm install

# yarn
yarn install
```

## Development Server

Start the development server on `http://localhost:3000`:

```bash
# npm
npm run dev

# pnpm
pnpm run dev

# yarn
yarn dev
```

## Production

Build the application for production:

```bash
# npm
npm run build

# pnpm
pnpm run build

# yarn
yarn build
```

Locally preview production build:

```bash
# npm
npm run preview

# pnpm
pnpm run preview

# yarn
yarn preview
```

Check out the [deployment documentation](https://nuxt.com/docs/getting-started/deployment) for more information.

### Add directory alias: `nuxt.config.ts`

```diff
+   import { resolve } from "path";

    // https://nuxt.com/docs/api/configuration/nuxt-config
    export default defineNuxtConfig({
      devtools: { enabled: true },
+     alias: {
+       "@": resolve(__dirname, "/"),
+     },
    });
```

### Install Bootstrap CSS

```bash
npm i bootstrap@5.3.1
```

### Add CSS alias: `nuxt.config.ts`

```ts
css: ["bootstrap/dist/css/bootstrap.css"],
```

### Add custom css

- Create `assets` folder
- Create `css` folder
- Create `app.css` in `css` folder
- Add some initial css

```css
/*
|--------------------------------------------------------------------------
| add 'fonts'
|--------------------------------------------------------------------------
*/
@import url("https://fonts.googleapis.com/css2?family=Inter:wght@100;200;300;400;500;600;700;800;900&display=swap");

/*
|--------------------------------------------------------------------------
| add 'root' variables
|--------------------------------------------------------------------------
*/
:root {
  --black: #000;
}

/*
|--------------------------------------------------------------------------
| add '*' selector
|--------------------------------------------------------------------------
*/
* {
  font-family: "Inter", sans-serif;
}

/*
|--------------------------------------------------------------------------
| add common css, start
|--------------------------------------------------------------------------
*/
.my-10 {
  margin-top: 10rem;
  margin-bottom: 10rem;
}
/*
|--------------------------------------------------------------------------
| add common css, end
|--------------------------------------------------------------------------
*/

/*
|--------------------------------------------------------------------------
| 'bootstrap' css overloading start
|--------------------------------------------------------------------------
*/
.btn {
  padding-left: 1.5rem !important;
  padding-right: 1.5rem !important;
  border-radius: 0.5rem !important;
}
/*
|--------------------------------------------------------------------------
| 'bootstrap' css overloading end
|--------------------------------------------------------------------------
*/
```

- Create `custom.css` in `css` folder

```css
/*
|--------------------------------------------------------------------------
| section start
|--------------------------------------------------------------------------
*/

/*
|--------------------------------------------------------------------------
| section end
|--------------------------------------------------------------------------
*/
```

- Create `media.css` in `css` folder

```css
/* // Small devices (landscape phones, 576px and up) */
@media (min-width: 576px) {
}

/* // Medium devices (tablets, 768px and up) */
@media (min-width: 768px) {
}

/* // Large devices (desktops, 992px and up) */
@media (min-width: 992px) {
}

/* // X-Large devices (large desktops, 1200px and up) */
@media (min-width: 1200px) {
}

/* // XX-Large devices (larger desktops, 1400px and up) */
@media (min-width: 1400px) {
}
```

- Create `style.css` in `css` folder

```css
@import url("app.css");
@import url("custom.css");
@import url("media.css");
```

### Add `style.css` in `nuxt.config.ts` in `css` module

```ts
"~/assets/css/style.css";
```

### Modify `app.vue` to check new custom css applied or not

```diff
    <template>
      <div>
-       <NuxtWelcome />
+       <div class="container my-5">
+         <button class="btn btn-primary">Show more...</button>
+       </div>
      </div>
    </template>
```
