[README_1.md](https://github.com/user-attachments/files/30837570/README_1.md)
# Deficit — setup

One file, no build step, no server, no cost. Everything below is free.

## 1. Put it online (about 10 minutes)

You need HTTPS, because browsers refuse camera access to pages opened from a plain file. Any of these work; GitHub Pages is the most permanent.

**GitHub Pages**

1. Make a free account at github.com.
2. Click **+** → **New repository**. Name it `deficit`. Set it to **Public**. Check **Add a README file**. Create.
3. Click **Add file** → **Upload files**. Drag in `index.html`. Commit.
4. Go to **Settings** → **Pages**. Under Source pick **Deploy from a branch**, branch `main`, folder `/ (root)`. Save.
5. Wait about a minute, then reload the Pages settings screen. Your URL appears at the top: `https://YOURNAME.github.io/deficit/`

Public repo means the *code* is public. Your food log is not — it never leaves your phone.

**Netlify** (faster, no account needed to start): go to app.netlify.com/drop and drag the file in. You get a URL immediately. Make an account if you want to keep it.

## 2. Install it on your iPhone

1. Open the URL in **Safari** (not Chrome — only Safari can install to the home screen on iOS).
2. Tap the share button, scroll down, tap **Add to Home Screen**.
3. Open it from the home screen icon from now on, not from Safari.

That last part matters. Safari deletes stored site data after seven days without interaction. Home screen web apps are exempt from that rule, so opening from the icon protects your log.

## 3. Set your targets

Go to **Setup**, fill in weight, height, age, and pick your deficit. Since you're lifting, 250 to 350 leaves more room to build than 500 does. Tap Calculate, then Use these. Adjust protein afterward if you want it higher.

## 4. Wire up your Apple Watch (optional)

1. Open **Shortcuts** → **+** → **Add Action**.
2. Search **Find Health Samples**. Set Type to **Active Energy**, filter **is today**, Group by **Day**, Fill Missing **off**, Limit **off**. Grant access when asked.
3. Add another action: **Open URLs**. Set the URL to your app address plus `?burn=` and then insert the Health result as a variable. Example: `https://YOURNAME.github.io/deficit/?burn=` + variable.
4. Name it something like "Log my burn". Run it to open the app with today's active energy already filled in.

Use **Active Energy**, not Total. Total includes the calories you burn just existing, and those are already inside your ceiling.

## 5. Turn on food search (optional, 2 minutes)

The Search tab inside Add Food pulls generic foods from USDA FoodData Central: raw apples, dry-roasted pistachios, a chicken breast. It works out of the box on a shared key capped around 50 lookups a day. For your own:

1. Go to fdc.nal.usda.gov/api-key-signup, enter your name and email. The key arrives by email immediately.
2. In the app: **Setup** → **Food search key** → paste → Save key.

That raises the limit to 1,000 lookups an hour. The key is stored on your phone only. Do not put it in `index.html` in the repo, the repo is public and USDA deactivates keys it finds in public code.

## 6. Back up

**Setup** → **Export a copy** saves a JSON file to your phone. Do this monthly. Your data lives in one browser on one device; there's no cloud copy. Restore from that same screen.

## Notes

- **Search**: generic, unbranded foods from USDA. Pick a food and you get its real portions, "1 medium apple", "1 cup chopped", plus a plain ounce or gram amount, and macros for each. Names come through long and clinical; edit them on the next screen before saving.
- **Scanner**: uses your phone's native barcode reader where available and a fallback library on iOS. Barcode data comes from Open Food Facts, a free community database. US coverage is decent but incomplete, and some entries store per-100g values rather than per-serving, so check the numbers before saving. Anything not found can be typed once and saved forever.
- **Exercise estimates**: net MET values from the Adult Compendium of Physical Activities, scaled to your body weight. Net means resting calories are subtracted, because those are already counted in your base target.
- **Eat-back**: defaults to 75%. Watch estimates run generous. If the scale and tape aren't moving after a month, lower this before you lower your calories.
- **Streak**: a day counts only when you hit protein *and* stay under the ceiling. Days you don't log break it, deliberately.
