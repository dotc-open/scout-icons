> **The icon library has moved to Kilnfield.** See the [current repository](https://github.com/ZacBytes/kilnfield) for downloads and artwork licensing, or [browse the catalog](https://zacbytes.github.io/kilnfield/).

# Scout Icons

[Browse the live catalog](https://zacbytes.github.io/kilnfield/)

Scout's softly sculpted 3D icon collection covers infrastructure, economy, technology, society, environment, security, country flags, and everyday interfaces. The topic and flag artwork comes from Scout’s original AI-generated pack. The interface illustrations were generated as a single contact sheet and cropped as individual assets.

The original topic icons use a shallow three-quarter view, softly rounded clay surfaces, diffuse light and a muted sandstone, slate, teal, ochre, terracotta and olive palette. The flags use national colours with a thin waving satin treatment.

## Files and formats

- `catalog.json` lists stable icon IDs, categories, artwork provenance and search terms.
- `assets/<id>.png` and `assets/<id>.webp` are 256 × 256 transparent images. WebP is lossless.
- `assets/<id>.svg` is a self-contained SVG with the transparent PNG embedded at its original resolution. The embedded artwork is bitmap-based.
- `embeddings.json` contains numeric search vectors derived from public icon metadata.

The artwork contains no political figures or portraits. The generic population image, which depicts three human busts, was omitted. Scout’s separate portrait and brand collections are outside this release. The flags are stylized Scout artwork. Their reference files and source atlases are outside this release.

## Coverage

Lucide and Google Material Symbols cover a broader range of reusable interface controls. Scout concentrates on recognisable objects and scenarios such as port equipment, undersea cables, grid infrastructure and extreme weather. [Lucide icon catalog](https://lucide.dev/icons/) and [Material Symbols library](https://fonts.google.com/icons)

| Need | Original Scout coverage | Examples from Lucide and Material Symbols | Public catalog additions |
| --- | --- | --- | --- |
| Discovery and navigation | Magnifier and place pin appeared inside larger compositions | `search` in Lucide, `location_on` in Material Symbols | Standalone search and map pin |
| Saving and organization | Sealed dossier, shipping boxes and server racks | `bookmark` in Lucide, `cloud_download` in Material Symbols | Bookmark, folder and cloud download |
| Preferences and communication | Antenna, news and fact-checking imagery | `bell` in Lucide, `chat` in Material Symbols | Settings, chat and notification bell |
| Time and planning | No dedicated date or time symbols | `clock` in Lucide, `calendar_month` in Material Symbols | Calendar and clock |
| Feedback | Emergency siren and specialist safety imagery | `triangle-alert` in Lucide, `check_circle` in Material Symbols | Success and warning |

The additions use Scout’s sculpted palette and rounded, lightly angled shapes. The collection still has limited coverage of directional arrows, text editing, media playback and accessibility controls.

## Run locally

Serve the repository root with a static HTTP server, for example `python3 -m http.server 8000`, and open `http://localhost:8000`. GitHub Pages serves the same files from the main branch.

Search combines local descriptions, related terms and prefix matching with normalized [MiniLM embeddings](https://huggingface.co/Xenova/all-MiniLM-L6-v2) in a browser worker. The browser fetches the pinned Transformers.js runtime and model on demand and runs inference locally. The text index works immediately and remains available if the runtime cannot load. The GitHub badge fetches the public repository's current star count, with the direct repository link available independently.

After editing the catalog or artwork, regenerate the derived files with `node tools/build-svg.mjs` and `node tools/build-search.mjs`. The search builder requires `npm install --no-save --no-package-lock @huggingface/transformers@3.8.1`. The SVG builder has no third-party dependencies.

## Licensing

The source artwork has no published general-purpose reuse license. Public access to the artwork and catalog code does not grant additional reuse permission. National flag illustrations may be subject to local rules for use and display. The runtime and model are loaded from their upstream distributors under their respective [Transformers.js](https://github.com/huggingface/transformers.js/blob/main/LICENSE) and [MiniLM](https://huggingface.co/Xenova/all-MiniLM-L6-v2) licenses.
