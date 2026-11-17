# Jarvis — Andrew's personal assistant

A heads-up-display style dashboard that greets you, surfaces your **important unread emails**, tracks **school and work due dates**, and **reminds you** before they're due — out loud if you want. It runs entirely in your browser and is hosted free on GitHub Pages.

## What it does

- **Priority Inbox** — pulls unread Gmail marked *Important* from the last 7 days. Anything from GWC, CCCD, CSUSB, ATI or Canvas gets a **SCHOOL** tag.
- **Deadlines** — merges your Google Calendar (next 14 days) with due dates you add yourself. School items are highlighted in amber; overdue items turn red. Filter by All / School / Mine.
- **Reminders** — each due date you add can alert you 2 days, 1 day, or 1 hour before, plus again when it's due (browser notification + spoken alert).
- **Brief Me** — tap the glowing core and Jarvis reads you a spoken summary of your inbox and upcoming deadlines.
- **Demo mode** — shows sample data until you connect Google, so you can see it working right away.

## 1. Put it on GitHub (5 minutes)

1. Sign in at [github.com](https://github.com) (or create a free account).
2. Click **+ → New repository**. Name it `jarvis`, set it to **Public**, check **Add a README**, and click **Create repository**.
3. Click **Add file → Upload files**, drag in `index.html` and this `README.md`, then **Commit changes**.
4. Go to **Settings → Pages**. Under *Branch*, pick `main` and `/ (root)`, then **Save**.
5. After a minute your Jarvis is live at `https://YOUR-USERNAME.github.io/jarvis/`. Bookmark it, or on your phone use **Share → Add to Home Screen**.

## 2. Connect Gmail and Google Calendar (about 10 minutes, one time)

Jarvis needs a Google "Client ID" so it can ask you to sign in. This is free.

1. Go to [console.cloud.google.com](https://console.cloud.google.com) and create a new project called `Jarvis`.
2. **APIs & Services → Library**: enable **Gmail API** and **Google Calendar API**.
3. **APIs & Services → OAuth consent screen**: choose **External**, app name `Jarvis`, your email for support and developer contact. Leave it in **Testing** mode and under **Test users** add your own Gmail address.
4. **APIs & Services → Credentials → Create credentials → OAuth client ID**:
   - Application type: **Web application**
   - Authorized JavaScript origins: `https://YOUR-USERNAME.github.io`
5. Copy the **Client ID** (ends in `.apps.googleusercontent.com`).
6. Open your Jarvis page → **Settings** → paste the Client ID → **Save** → **Connect Google**.

Google will warn that the app "hasn't been verified." That's expected for a personal app you made yourself — click **Continue**. Access is read-only, and sign-in lasts about an hour before you tap Connect again.

## 3. Get your Canvas due dates in automatically

1. In Canvas, open **Calendar** and click **Calendar Feed** (bottom right). Copy the link.
2. In Google Calendar on a computer, click **+ next to Other calendars → From URL**, paste the link, and add it.

Now every Canvas assignment and exam shows up in Jarvis's Deadlines panel, tagged as school.

## 4. Turn on alerts

Tap **Enable Alerts** and allow notifications. Reminders fire while Jarvis is open in a browser tab, so keep it pinned. Speech can be turned off in Settings.

## Privacy

There's no server. Your emails and calendar are fetched straight from Google into your browser and never stored anywhere else. Due dates you add are saved only in that browser. The Client ID isn't a secret, so it's fine for the repo to be public.

## Personalize it

The top of the `<script>` in `index.html` has a `CONFIG` block where you can change your name, which email domains count as school, which words mark a calendar event as school, and how far ahead to look.
