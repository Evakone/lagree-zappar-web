# Lagree AR Zappar Demo

Lightweight static experience for the Lagree sandwich board marker using Zappar's WebGL pipeline. The project ships as plain HTML/CSS/JS that can be hosted on any static server.

## Develop

```bash
zapworks serve . --lan --port 8080
```

Open the printed LAN URL on an HTTPS-capable device, tap **Start Experience**, and allow camera access. The marker tracker expects `assets/marker.zpt` (generated via `zapworks train`).

## Deploy

Publish the contents of this folder to any static host (Vercel, Netlify, S3, etc.). For Zappar licensing banners to disappear, set a Universal AR WebGL license key before the camera is created:

```js
ZapparThree.setOptions({ licenseKey: 'your-license-key' });
```

You can keep the key in `localStorage` while developing:

```js
localStorage.setItem('zapparLicenseKey', 'your-license-key');
```

## Files

- `index.html`: marketing/landing page.
- `zappar.html`: Zappar ThreeJS experience.
- `assets/`: marker image + 3D assets.
- `vendor/`: prepackaged MindAR fallback libraries and helpers (unused by Zappar path).
- `brand.css`: shared brand styling.
