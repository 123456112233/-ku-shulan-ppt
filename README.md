```markdown
# Ku Shulan (库淑兰) PPT Generator

This package provides a Python script that downloads public images from predefined pages about Ku Shulan (库淑兰)
and generates an educational PPTX template including speaker notes and image attributions.

Files included:
- generate_ku_shulan_ppt.py  — the main Python script to generate PPTX
- README.md                  — this file
- (output) ku-shulan-presentation.pptx — generated PPTX after running the script
- images/                    — directory where scraped images will be saved
- generation_metadata.json   — metadata created during generation (image paths, attributions, slide defs)

Important: This script attempts to use publicly available images from pages; you must review and confirm
copyright/usage permissions for the images before using the PPT in any public or commercial context.
For classroom/educational non-commercial use, include the credit lines printed to the slides/notes.

Prerequisites
-------------
- Python 3.8+
- Install dependencies:
  pip install python-pptx requests beautifulsoup4 lxml

How to run
----------
1. (Optional) Edit `generate_ku_shulan_ppt.py`:
   - Change BACKGROUND_COLOR ("deepblue" or "chinese-red")
   - Update SOURCE_PAGES list if you want to add/remove pages or change credits
   - Edit SLIDE_DEFINITIONS to customize slide titles, bodies and which source_key to use

2. Run the script:
   python generate_ku_shulan_ppt.py

3. Output:
   - `ku-shulan-presentation.pptx` will be created in the current directory.
   - `images/` will contain downloaded images (named by the script).
   - `generation_metadata.json` contains details of what was downloaded and what was used.

Custom image URLs
-----------------
If you already have direct image URLs (or local images) you prefer, modify the script:
- Provide a mapping images_map = {"china_daily": "https://.../image.jpg", ...}
- Or place local files in `images/` and set SOURCE_PAGES' keys and filenames accordingly.

Credits & Attributions
----------------------
The script uses the following source pages by default (edit in the script if you prefer others):
- China Daily exhibition page (China Daily) — https://govt.chinadaily.com.cn/...
- iMuseum exhibition page (Shaanxi Art Museum) — https://art.icity.ly/...
- Youth.cn (CFP photos) — https://en.youth.cn/...
- Sohu article — https://www.sohu.com/...
- Alice & The City blog — https://aliceandthecity.com/...

Each slide that includes an image will have a footer line and speaker notes indicating:
  "图片来源/Photo credit: <credit text> (<page_url>)"

Legal / Copyright reminder
--------------------------
- The script attempts to download images automatically from public pages; this does NOT transfer any
  copyright or provide permission for commercial reproduction.
- For educational, in-class, non-commercial use, many news/museum photos are acceptable with credit,
  but you should verify terms on the source pages. For any public distribution (uploading PPT online,
  printing for sale, publishing in a book), obtain written permission from the rights holder.

Troubleshooting
---------------
- If images are not downloaded: network issues, the page blocked scraping, or images loaded via JS/Ajax.
  You can manually download images and place them into `images/` folder and edit `generation_metadata.json`
  or the script to point to those local files.
- Fonts: to match the intended visual style, the script sets font names (e.g., "KaiTi", "SimSun").
  If those fonts are not installed on the machine that opens the PPTX, PowerPoint will substitute.
  Install appropriate Chinese fonts on your system if you need exact appearance.

Support
-------
If you want, I can:
- Provide a version of the script that accepts an explicit JSON mapping of slide->image_url (for more control).
- Generate the PPTX for you and provide instructions to upload it to your chosen place (GitHub/Drive).  
```