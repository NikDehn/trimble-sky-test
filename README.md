# trimble-sky-test

Test af om man kan lægge en himmel omkring modellen i Trimble Connects 3D Viewer via Workspace API. Ingen projektdata i repoet; himlen er genereret.

## Indhold

| Sti | Hvad |
|---|---|
| `index.html` | Extension-panelet i 3D Vieweren (forbinder via Workspace API 0.3.38) |
| `manifest.json` | Manifest som Trimble Connect læser, når extension installeres |
| `sky/pano.jpg` | Himmel-panorama, ækvirektangulært 4096 × 2048 |
| `sky/0/0_0.jpg`, `sky/0/0/0.jpg` | Samme billede som "tile 0" til URL-mønstrene med pladsholdere |
| `dome/` | Plan B: himmelkuppel (radius 2000 m) som 3D Tiles, både glb (1.1) og b3dm (1.0) |
| `icon.png` | Ikon til extension-listen |

## Kom i gang

1. Opret et **offentligt** GitHub-repo med navnet `trimble-sky-test` og læg alle filer i roden.
2. Settings → Pages → Deploy from a branch → `main` / root.
3. Ret `url` og `icon` i `manifest.json`, hvis repo eller brugernavn er et andet end `nikdehn/trimble-sky-test`.
4. I Trimble Connect: åbn 3D Vieweren → Settings → Extensions → Add custom extension → indsæt
   `https://nikdehn.github.io/trimble-sky-test/manifest.json`.
5. Åbn panelet "Himmel-test", tryk **Find modellens centrum** og derefter **Tilføj himmel**.

Se `Himmel-i-Trimble-Connect.pdf` for hele fremgangsmåden og fejlsøgning.

## Hvad er usikkert

Trimble dokumenterer ikke, hvilke pladsholdere `tilesUrl` bruger. Derfor er billedet lagt ud som én tile (niveau 0, x 0, y 0), og panelet kan sende seks varianter af URL-mønsteret. `add3DTiles` er markeret som skjult i API'et.
