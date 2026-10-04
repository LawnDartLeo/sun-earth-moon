# Sun–Earth–Moon orbital playground

An interactive, deliberately exaggerated three-body model for exploring orbital geometry, Moon phases, eclipses, and views from Earth.

## Run it

Open **index.html** in a browser with WebGL enabled. Everything is contained in that file: HTML, CSS, JavaScript, and the WebGL shaders. There is no build step, package installation, external rendering library, OpenAI account, or API key.

To publish with GitHub Pages, place index.html in the repository root, then select **Settings → Pages → Deploy from a branch → main → /(root)** and save. GitHub Pages is available for public repositories on GitHub Free. See [GitHub's publishing-source documentation](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site).

## Explore

- Drag to rotate the camera; scroll or pinch to zoom.
- Play, pause, change speed, or scrub the model time.
- Use **Follow Earth** to inspect the Moon more closely.
- Adjust body radii, orbit radii, Moon orbit inclination, and the line of nodes.
- Use **Next solar** or **Next lunar** to pause at the next model eclipse.
- Try **Eclipse scale** to reduce the body radii and make more alignments miss.
- The three small views track the Moon from 45° north at sunrise, sunset, and local solar noon. Altitude, azimuth, and the geometric horizon are shown.

## What is modeled

The Moon's orbit defaults to an inclination of **5.145°** relative to Earth's orbital plane. Earth's spin axis is tilted **23.44°** relative to the normal of that plane.

Both orbits are circular, with nominal periods of 365.25 and 27.32 model days. The line of nodes stays fixed unless adjusted manually. The Moon follows Earth as Earth follows the Sun. A point light at the Sun's center illuminates Earth and Moon, and they can cast shadows on one another.

Each observer lies at **45° N relative to Earth's tilted spin axis**. The observer longitudes move to maintain the specified local solar condition; these are three separate sites, not one fixed person viewed at three times of day. Sunrise and sunset use the point-light geometric terminator. The local horizon hides below-horizon targets. Telescope views auto-zoom, so their fields of view can differ.

The eclipse buttons search forward from the current arrangement, find a closest approach of the relevant shadow axis, and check for overlap using the current sizes and distances. They pause there. Search is limited to the next 1,100 model days and skips the first model day to avoid selecting an ongoing event.

## Compromises and limitations

- **Sizes and distances are not to scale.** Controls use arbitrary model units. Large display radii can produce frequent eclipses even with the appropriate orbital tilt. Eclipse scale helps demonstrate near misses but is also exaggerated.
- **This is not an ephemeris or eclipse predictor.** Model day numbers are not calendar dates. Manual arrangement changes the starting geometry.
- The visible Sun sphere illustrates the Sun; lighting comes from a **point source**, not a finite solar disk. Hard shadows therefore do not reproduce penumbrae or annular eclipses. Apparent overlap of the displayed Sun and Moon can differ from the point-light shadow criterion.
- No orbital eccentricity, nodal precession, gravitational integration, or detailed lunar rotation is modeled.
- Planet markings are procedural illustrations, not accurate geographic maps.
- Dark-side fill and daylight sky colors are visual aids, not physically calibrated radiometry or atmospheric scattering.
- Observer views use the exaggerated geometry, so their parallax, apparent angular sizes, and visibility should not be treated as real-world observing predictions.
- Refraction, terrain, and finite solar-disk effects on sunrise/sunset are omitted.
- A solar eclipse somewhere on the model Earth need not be visible to the three observers at 45° north.

## Authorship and AI assistance

LawnDartLeo supplied the concept, requirements, and direction, inspired by a SOLIDWORKS model whose true scale made exploration difficult. Code and documentation were developed with assistance from **OpenAI Codex** through an iterative conversation. AI assistance is disclosed in the model itself.

Astronomical constants and geometric references are credited below. The cited organizations did not create or endorse this implementation. No third-party image assets or rendering libraries are bundled.

## References

- [NASA: Eclipses and the Moon's orbit](https://eclipse.gsfc.nasa.gov/SEhelp/moonorbit.html) — mean lunar orbital inclination and nodes.
- [NASA: Earth fact sheet](https://nssdc.gsfc.nasa.gov/planetary/factsheet/earthfact.html) — Earth's obliquity.
- [NOAA: General solar position calculations](https://gml.noaa.gov/grad/solcalc/solareqns.PDF) — solar-angle geometry. This model uses its own vector implementation and simplified orbital state, not NOAA's calendar ephemeris.

## Verification

JavaScript startup, controls, camera inputs, tilt and node geometry, observer latitude, sunrise/sunset signs, terminator placement, and eclipse navigation were checked using simulated browser APIs. Eclipse jumps were checked for shadow overlap. HTML export and its clipboard fallback were also checked.

Live WebGL shader compilation and final visual appearance were not independently previewed by the assistant. The project author explored the embedded model and provided feedback. This is a statement of what was actually checked, not a claim of scientific validation.

Before publishing changes, open the file in a browser and check:
1. Play/pause, scrubbing, reset, and camera movement.
2. Tilt and node controls, including 0° inclination.
3. Solar and lunar jumps with both scale presets.
4. All three observer views, horizon hiding, and reported local solar conditions.
5. HTML/README downloads and copying when downloads are blocked.

## Contributing

Questions, corrections, and improvements are welcome through issues and pull requests. Explain any change to the geometry or scale assumptions, cite primary sources for astronomical claims, and describe how you checked the result. Preserve the scientific references and AI-assistance disclosure.

## License

[MIT License](LICENSE), copyright (c) 2026 LawnDartLeo. The full notice is in the repository's LICENSE file and embedded in exported HTML. Keep the copyright and license notice when redistributing copies or substantial portions.

## Public source and hosting

Source: [LawnDartLeo/sun-earth-moon](https://github.com/LawnDartLeo/sun-earth-moon).

After GitHub Pages is enabled for main / (root), its standard project-site address is https://lawndartleo.github.io/sun-earth-moon/. A link here is not confirmation that hosting has already been enabled.
