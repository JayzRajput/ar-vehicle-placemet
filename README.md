# Road Vehicle AR

WebXR augmented-reality app: point your phone at a road, tap, and a true-scale
car / SUV / truck / bus is parked there. Includes a 3.5 m lane guide overlay and
a desktop 3D preview mode.

## Run locally
    npx serve .          # then open via an HTTPS tunnel (e.g. `npx localtunnel --port 3000`)
WebXR requires HTTPS (localhost counts, but a phone needs a tunnel or deployment).

## Deploy (static, free)
- **Netlify**: drag the `ar-road-vehicles` folder onto app.netlify.com/drop
- **GitHub Pages**: push `index.html`, enable Pages on the branch
- **Vercel**: `npx vercel --prod`

## Devices
Android + Chrome + ARCore (Google Play Services for AR). iOS Safari has no
WebXR AR; use the 3D preview there, or add a `<model-viewer>` Quick Look fallback.

## Notes
- Vehicles are modelled in real metres, so scale looks right on the road.
- Hit-testing finds any flat surface; it does not recognise "road" semantically.
- To use your own models, swap `makeVehicle()` for a GLTFLoader load of a .glb.
