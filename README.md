# Solar System from Earth

A small teaching tool for exploring the Sun, Earth’s Moon, seven other planets, and Pluto from the ground at 45° north. Earth is the observer’s home and the ground beneath the horizon. The original Sun–Earth–Moon playground is preserved in [playground.html](playground.html).

## Run and explore

Open `index.html` in a modern browser. It is a standalone HTML file with no packages, rendering libraries, network requests, API keys, or build step. Use GitHub Pages with **main / (root)** to host the repository.

- The 24-hour slider changes local solar time. Sunrise, Noon, and Sunset jump to the appropriate solar positions and turn the camera toward the Sun.
- Sweep day animates the observing longitude through a day while freezing the orbital arrangement.
- Model day advances the orbits. The time slider covers ten model years initially; the number input allows longer intervals. ±30 d and seasonal presets provide short jumps.
- Drag or use arrow keys to look around; scroll or use +/− to zoom. Reset view looks south again.
- Click a sky label or an object button to inspect a magnified disk, phase, angular diameter, altitude, azimuth, and distance. An object button also points the camera toward that body if it is above the horizon. Dashed buttons mean below the horizon.
- Daylight sky adds an illustrative daytime background. Labels remain visible for teaching; their presence does not establish naked-eye visibility.
- Save HTML downloads a standalone copy, with the MIT notice and credits embedded.

## Geometry and scale

Planets and Pluto follow circular orbits at fixed representative distances based on semimajor axes. All are deliberately placed in one ecliptic plane, including Pluto. Earth’s axis retains 23.44° tilt; the Moon retains a 5.145° orbital tilt, a fixed node, a circular 384,400 km orbit and a 27.321661-day period. No other moons are included.

Body radii and physical distances share one scale in astronomical units. The sky uses a perspective projection from Earth’s surface and computes topocentric apparent positions and angular diameters. The Sun and Moon are not enlarged in the main sky. For disks smaller than a pixel, a locator dot identifies the direction; that dot is not their physical diameter. The magnified inspector is explicitly separate from the main angular scale. Spherical surface shading uses a point Sun; Earth can cast a hard shadow on the Moon. Phase percentages describe illumination geometry before eclipse darkening. A dim unlit side aids readability.

Model days are not real calendar dates or observing predictions. Initial planetary longitudes use JPL’s J2000 nominal elements, then evolve uniformly on the simplified circular orbits. Earth uses the Earth–Moon barycenter’s nominal orbital radius and longitude as an approximation. Pluto uses NASA’s J2000 mean elements. The Moon starts at an illustrative 218° longitude with its node fixed at 0°; this does not define an accurate epoch. Daily time sweeps freeze orbital motion, including lunar motion, over the sweep.

Local solar time selects an observing longitude relative to the Sun’s meridian at 45° N. Sunrise, noon, and sunset thus represent different longitudes, rather than a specified city and civil clock time. Sunrise/sunset use the center of the point Sun at the geometric horizon; refraction, terrain, and finite-disk sunrise effects are omitted.

No eccentricity, planetary inclinations, nodal precession, nutation, light-time, aberration, star background, rings, or other satellites are modeled. Saturn’s inset shows its spherical body without rings. Pluto’s real inclination and eccentricity are intentionally omitted. Surface colors and daylight colors are illustrative. There is no photometric visibility calculation. This is a geometry teaching tool, not a realistic planetarium or eclipse forecast.

## Sources

- [JPL approximate planetary positions](https://ssd.jpl.nasa.gov/planets/approx_pos.html): nominal orbital radii and initial longitudes. The model deliberately omits JPL’s eccentricity/inclination terms and does not claim their ephemeris accuracy.
- [JPL physical parameters](https://ssd.jpl.nasa.gov/planets/phys_par.html): body radii and orbital periods, including Pluto.
- NASA [Pluto fact sheet](https://nssdc.gsfc.nasa.gov/planetary/factsheet/plutofact.html): Pluto’s J2000 radius of orbit and initial mean longitude.
- NASA [Moon fact sheet](https://nssdc.gsfc.nasa.gov/planetary/factsheet/moonfact.html), [Sun fact sheet](https://nssdc.gsfc.nasa.gov/planetary/factsheet/sunfact.html), and [Moon orbit](https://eclipse.gsfc.nasa.gov/SEhelp/moonorbit.html): lunar distance/size/period, solar size, axial tilt and lunar inclination.

## Validation

Checked in headless Microsoft Edge. Geometry checks cover every circular orbital radius and return after a period, shared planetary plane, lunar distance/inclination, observer surface location and latitude, Sun angular diameter, sunrise/noon/sunset, horizon hiding at midnight, northern summer/winter noon heights, east/west orientation, Pluto inspection, and outer-planet motion over model years. Browser checks cover daylight controls, selection, reset, startup errors, and exported MIT/source text. Desktop and 390-pixel layouts were visually inspected. These checks do not establish ephemeris accuracy or real-world visibility.

## Credits and license

LawnDartLeo supplied the concept, requirements, and educational direction. Code and documentation were developed with OpenAI Codex assistance. NASA/JPL sources did not create or endorse this implementation. No third-party image assets or rendering libraries are bundled.

[MIT License](LICENSE), copyright © 2026 LawnDartLeo. Preserve the copyright and license notice when redistributing. The full notice is embedded in HTML copies.

[Public repository](https://github.com/LawnDartLeo/sun-earth-moon). The original adjustable model remains in [playground.html](playground.html), with its documentation in [PLAYGROUND.md](PLAYGROUND.md).

