# Welcome to your Expo app 👋

This is an [Expo](https://expo.dev) project created with [`create-expo-app`](https://www.npmjs.com/package/create-expo-app).

## Get started

1. Install dependencies

   ```bash
   npm install
   ```

2. Start the app

   ```bash
    npx expo start
   ```

# Create Progressive web apps with Expo

## Expo setup

app.json

```
"web": {
"bundler": "metro",
"output": "single",
"favicon": "./assets/images/favicon.png"
}
```

## Manifest

create the required images in the same directory

public/manifest.json

```
{
 "short_name": "Expo App",
 "name": "Expo Router Sample",
 "icons": [
   {
     "src": "favicon.ico",
     "sizes": "64x64 32x32 24x24 16x16",
     "type": "image/x-icon"
   },
   {
     "src": "logo192.png",
     "type": "image/png",
     "sizes": "192x192"
   },
   {
     "src": "logo512.png",
     "type": "image/png",
     "sizes": "512x512"
   }
 ],
 "start_url": ".",
 "display": "standalone",
 "theme_color": "#000000",
 "background_color": "#ffffff"
}
```

Create the below example

```
public
- manifest.json
- index.html
- logo192.png
- logo512.png
- favicon.ico

```

## create below and the required code

app/+html.tsx

`npx expo export -p web`

select `dist` while running this cmd

```
npx workbox-cli wizard

? What is the root of your web app (that is which directory do you deploy)? dist/
? Which file types would you like to precache? js, html, ttf, ico, json
? Where would you like your service worker file to be saved? dist/sw.js
? Where would you like to save these configuration options? workbox-config.js
? Does your web app manifest include search parameter(s) in the 'start_url', other than 'utm_' or 'fbclid' (like '?source=pwa')? No
```

```
update the package.json while building the application
```

{
"scripts": {
"build:web": "expo export -p web && npx workbox-cli generateSW workbox-config.js"
}
}

```
npm run build:web
npx serve dist
```

```

```
