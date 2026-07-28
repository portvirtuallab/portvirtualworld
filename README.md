# Port Virtual World — PVL.ONE

**Port Virtual World** is an interactive digital-twin platform developed as part of the **PVL.ONE ecosystem** by **Escola Europea – Intermodal Transport**.

The platform digitally represents port communities through a common methodology, including transport modes, terminals, logistics operators, infrastructure, services and environmental indicators.

By applying the same structure to different ports, Port Virtual World makes it possible to:

* Analyse individual port communities.
* Compare ports using common criteria.
* Visualise logistics and transport networks.
* Identify potential connections between port communities.
* Explore and simulate multimodal and sustainable transport corridors.
* Support education, professional training, research and international cooperation.

🔗 **Live site:**
https://portvirtualworld.github.io/portvirtualworld/

> Update this URL if the repository name, organisation or GitHub Pages configuration changes.

---

## Ownership

Port Virtual World, including its source code, visual design, methodology, structure, written content, datasets, educational materials and associated digital assets, is owned by:

**Escola Europea – Intermodal Transport**

The project forms part of the Escola Europea's digital learning and simulation ecosystem, including **PVL.ONE**, the **Port Virtual Lab** and related educational and professional training initiatives.

Unless expressly authorised in writing by Escola Europea – Intermodal Transport, the contents of this repository may not be reproduced, distributed, commercially exploited, sublicensed, republished or incorporated into another platform.

The publication of this repository does not imply the transfer of ownership, intellectual property rights or commercial exploitation rights.

---

## Purpose of the project

Port Virtual World has been designed as an educational and professional tool for the logistics, transport, international trade and port sectors.

Its main objectives are to:

1. Create a structured digital representation of different port communities.
2. Facilitate the understanding of port and logistics ecosystems.
3. Support training activities based on simulation and experiential learning.
4. Connect port communities using a shared digital methodology.
5. Analyse potential green and multimodal transport corridors.
6. Promote collaboration between educational institutions, ports, companies and logistics organisations.
7. Provide a scalable foundation for future digital-twin and simulation projects.

---

## Repository structure

```text
portvirtualworld/
├── index.html                  # Main landing page and port selector
├── README.md                   # Project documentation
├── assets/                     # Shared visual resources, if applicable
├── barcelona/
│   ├── index.html              # Barcelona port digital twin
│   └── images/
│       └── banner-barcelona.jpg
├── civitavecchia/
│   ├── index.html              # Civitavecchia port digital twin
│   └── images/
├── palermo/
│   ├── index.html              # Palermo port digital twin
│   └── images/
├── rotterdam/
│   ├── index.html              # Rotterdam port digital twin
│   └── images/
└── ...
```

Each port folder contains its own digital representation.

A typical `<port>/index.html` may include:

* Port identification and introductory information.
* Transport modes.
* Port terminals.
* Logistics operators and professional archetypes.
* Port community organisations.
* Nautical and logistics services.
* Infrastructure nodes.
* Environmental and sustainability indicators.
* Community lead or institutional contact.
* Interactive maps.
* Key port statistics.
* Connections with other port communities.

Each port page is designed to be largely self-contained, allowing new ports to be incorporated without modifying the complete architecture of the platform.

---

## Adding a new port

To add a new port community, follow these steps.

### 1. Duplicate an existing port folder

Duplicate one of the existing folders, for example:

```text
barcelona/
```

Rename it using a simple lowercase slug:

```text
valencia/
```

Avoid spaces, uppercase letters and special characters in folder names.

---

### 2. Update the port information

Open the new port's `index.html` file and update the relevant configuration objects.

Depending on the version of the page, these may include:

```javascript
CONFIG
LEAD
ARCHETYPES
MODES
NODES
NAUTIC_SERVICES
TERMINALS
```

Replace the existing information with verified data for the new port.

The information should be reviewed before publication, particularly:

* Port name.
* Country and region.
* Geographic coordinates.
* Transport connections.
* Terminal information.
* Port operators.
* Infrastructure.
* Annual traffic data.
* Sustainability indicators.
* Contact information.
* Images and logos.

---

### 3. Add the port banner

Place the relevant image inside the new port's image directory:

```text
valencia/images/banner-valencia.jpg
```

Update the corresponding CSS rule:

```css
#hero .hero-photo {
  background-image: url("./images/banner-valencia.jpg");
}
```

Images should be appropriately licensed or owned by Escola Europea – Intermodal Transport.

Do not upload copyrighted images without the necessary authorisation.

---

### 4. Add the port to the main landing page

Open the root `index.html` and add the new port to the `PORTS` array:

```javascript
{
  slug: "valencia",
  name: "Valencia",
  region: "Western Mediterranean · Spain",
  flag: "ES",
  color: "#1E6BB8",
  scene: "scene-port",
  live: true,
  stats: [
    { v: "—", k: "Members" },
    { v: "—", k: "Terminals" },
    { v: "—", k: "TEU/year" }
  ]
}
```

Use:

```javascript
live: true
```

when the port page is complete and publicly available.

Use:

```javascript
live: false
```

when the port should appear as **Coming soon**.

---

### 5. Verify internal links

Confirm that the card points to the correct folder:

```text
valencia/index.html
```

All links should use relative paths so the website works correctly on GitHub Pages and other static hosting services.

---

### 6. Test the page

Before publication, verify:

* The port card opens correctly.
* The page works on desktop and mobile.
* The interactive map loads.
* Images and icons are displayed.
* There are no broken links.
* Statistics and descriptions are accurate.
* External links open correctly.
* No confidential or personal information has been included.
* Copyright and attribution requirements are respected.

---

## Data quality

Port Virtual World aims to provide accurate and useful information. However, port data, infrastructure, operators, routes, services and annual statistics may change over time.

Contributors must:

* Use reliable and identifiable sources.
* Confirm data before publication.
* Avoid presenting estimates as official figures.
* Indicate when information is provisional.
* Include the relevant reference year for statistics.
* Periodically review existing port profiles.

The platform should not be considered an official operational, navigational, customs, legal or commercial source.

---

## Technology stack

The project is built as a static website using:

* HTML5.
* CSS3.
* Vanilla JavaScript.
* Leaflet.js for interactive maps.
* CARTO Voyager map tiles.
* Google Fonts.
* Inline JavaScript configuration objects.
* GitHub Pages for static hosting.

The current version does not require:

* A build process.
* A JavaScript framework.
* A backend server.
* A database.
* Server-side authentication.

Each page stores its information directly within its HTML and JavaScript structure.

---

## Local development

The project can be opened directly in a browser. However, using a local development server is recommended to prevent browser restrictions related to local files.

Using Python:

```bash
python -m http.server 8000
```

Then open:

```text
http://localhost:8000
```

Using Visual Studio Code, the **Live Server** extension may also be used.

---

## Deployment with GitHub Pages

Port Virtual World can be deployed as a static website using GitHub Pages.

### Deployment steps

1. Open the GitHub repository.
2. Go to **Settings**.
3. Select **Pages**.
4. Under **Build and deployment**, select:

```text
Deploy from a branch
```

5. Select the following configuration:

```text
Branch: main
Folder: / (root)
```

6. Save the configuration.
7. Wait for GitHub Pages to publish the website.

The website will normally be available at:

```text
https://<organisation>.github.io/<repository>/
```

For this repository:

```text
https://portvirtualworld.github.io/portvirtualworld/
```

---

## Contributions

Internal contributions, corrections and new port profiles are welcome when they support the objectives of the project.

Before making significant modifications, contributors should coordinate with the project owner or the designated PVL.ONE project manager.

Contributions should:

* Follow the existing folder structure.
* Preserve the visual identity of the platform.
* Use verified information.
* Respect intellectual property rights.
* Avoid publishing confidential information.
* Maintain compatibility with GitHub Pages.
* Be tested before being merged into the main branch.
* Receive the relevant internal approval before public publication.

Submitting a contribution does not transfer ownership of the project or grant commercial exploitation rights.

---

## Brand use

The names, visual elements and identities associated with the following initiatives may be protected and must be used in accordance with the guidelines established by Escola Europea – Intermodal Transport:

* Escola Europea – Intermodal Transport.
* PVL.ONE.
* Port Virtual Lab.
* Port Virtual World.
* PLIKA.
* Associated simulations, methodologies and training materials.

Logos, names and visual identities must not be altered, redistributed or used in external commercial communications without prior authorisation.

---

## Third-party components

The project may include or connect to third-party technologies and resources, such as:

* Leaflet.js.
* CARTO map tiles.
* Google Fonts.
* Publicly available geographic information.
* External institutional websites.
* Third-party images or icons used under their respective licences.

These components remain subject to their own terms, licences and conditions of use.

Their inclusion does not imply that Escola Europea – Intermodal Transport owns the underlying third-party technology or content.

---

## Disclaimer

Port Virtual World is intended for educational, training, research, demonstration and institutional cooperation purposes.

The information displayed on the platform:

* May be simplified for educational use.
* May not reflect real-time port operations.
* May contain estimates or reference-year data.
* Must not be used as the sole basis for operational decisions.
* Does not constitute legal, customs, financial, navigational or commercial advice.
* Does not replace information issued by port authorities, terminal operators, public administrations or other competent organisations.

Escola Europea – Intermodal Transport is not responsible for decisions made solely on the basis of information presented through this platform.

---

## Licence and permitted use

**Copyright © Escola Europea – Intermodal Transport. All rights reserved.**

This repository is made available for authorised educational, institutional, demonstration and development purposes.

Unless prior written permission has been granted by Escola Europea – Intermodal Transport, users may not:

* Sell or commercially exploit the project.
* Redistribute substantial parts of the source code.
* Publish modified versions under another name.
* Remove ownership or copyright notices.
* Present the project as their own work.
* Use the platform to create an unauthorised competing product.
* Reuse the methodology or content for commercial training.
* Transfer the code or materials to third parties.
* Use Escola Europea, PVL.ONE or Port Virtual World branding without authorisation.

Access to the repository does not constitute a transfer of intellectual property rights.

For permissions, institutional collaboration, educational use or commercial enquiries, contact Escola Europea – Intermodal Transport.

---

## Project ecosystem

Port Virtual World forms part of a wider ecosystem of projects and initiatives promoted by Escola Europea – Intermodal Transport:

* **PVL.ONE:** https://pvl.one
* **Escola Europea – Intermodal Transport:** https://www.escolaeuropea.eu
* **PLIKA:** https://plika.org

---

## Contact

**Escola Europea – Intermodal Transport**
Moll de Barcelona Nord, s/n
Jardins de l'Areté, 1
08039 Barcelona, Spain

Website: https://www.escolaeuropea.eu
PVL.ONE: https://pvl.one

For technical questions, institutional collaborations or requests to reuse the project, please contact the Escola Europea – Intermodal Transport through its official communication channels.

---

## Credits

Developed and maintained by **Escola Europea – Intermodal Transport** as part of the **PVL.ONE digital learning, simulation and port-community ecosystem**.

Port Virtual World is designed to support the creation of connected, comparable and sustainable port communities through education, technology and international cooperation.
