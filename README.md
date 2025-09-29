# SMILES → IUPAC in the Browser (GitHub Pages)

This is a static site that runs **CDK**'s `IUPACNameGenerator` **entirely in the browser** via **CheerpJ** (WebAssembly-based JVM). No servers, no API keys.

## How to host on GitHub Pages
1. Create a new GitHub repo and upload this folder.
2. Download CDK bundle JAR (about ~11–20 MB):
   https://repo1.maven.org/maven2/org/openscience/cdk/cdk-bundle/2.9/cdk-bundle-2.9.jar
3. Place it at: `lib/cdk-bundle-2.9.jar` in the repo.
4. Enable GitHub Pages: Settings → Pages → Deploy from Branch (root).
5. Open your site. First load will fetch the CheerpJ runtime + CDK JARs and can take 10–30s.

## Usage
- Paste an *isomeric* SMILES string.
- Click **Generate IUPAC**.
- Copy the result.

## Notes
- The page uses static CheerpJ CDN: `https://cjrtnc.leaningtech.com/3.0rc2/cj3loader.js`.
- No InChI functionality in this build (JNI-based; not needed for naming).
- Complex/fused polycycles may yield partial names — a limitation of CDK's algorithmic namer.

## Local testing
You can open `index.html` directly, but some browsers restrict `file://` XHRs. Use a simple local server if needed.
