# 5. Legal aspects

!!! warning "I'm not a lawyer"

    This is a brief, non-expert overview. If in doubt, check your institution's guidance or ask a real lawyer.

Publishing a website comes with a few small responsibilities. For a personal academic site none of this is onerous, but it is worth knowing about.

## Privacy policy

It is good practice to include a short **privacy policy** stating what data (if any) your site collects and what happens to it, together with a clear note of **who is responsible** for the site — your name and a way to contact you. If your site collects any personal data at all (through analytics, a contact form, comments, etc.), data-protection rules such as GDPR expect you to be upfront about what you collect, why, and how visitors can reach you.

## Data management

Simplest approach: collect as little as possible. A plain static site that collects *nothing* has almost nothing to manage. Forms, comments, or analytics need deliberate choices: store only what you need, only for as long as you need it.

## Cookies and web analytics

Once live, you may want to track visitor numbers and page views. All tools here support analytics—MkDocs Material has [built-in configuration](https://squidfunk.github.io/mkdocs-material/setup/setting-up-site-analytics/), Jekyll's Minimal Mistakes does too, and JupyterBook uses a script snippet.

The default choice is often **Google Analytics**, which is free and widely supported. There are two reasons to think twice before using it. The first is practical: GA drops tracking cookies in visitors' browsers, which requires a cookie consent banner under GDPR — an annoying addition to an otherwise clean academic site. Cookie banners are not always supported out-of-the-box via the workflows we have shown here, often requiring [custom or community implementations](https://github.com/karstenj/cookie-consent-banner). The second is ethical: by embedding GA, you are sending detailed behavioural data about your readers to Google, who uses it for their own purposes (ad targeting, profiling).

A cleaner alternative is **[Plausible](https://plausible.io)**: cookieless, privacy-respecting, and no consent banner needed. The cloud-hosted version costs around €9/month, which is fine for a funded project but not for a personal site. The self-hosted version is free and open-source — [OGGM](https://oggm.org) runs its own Plausible server, which anyone in the project can use at no cost, though someone has to maintain the server. [GoatCounter](https://www.goatcounter.com) is another cookieless option with a generous free tier.

For a personal academic website with modest traffic, any of these works. For a project site where you care about GDPR compliance, Plausible is worth the effort.

## Copyright: own what you publish

**Make sure you own, or are licensed to use, every image, font, icon and video you put on your site** — and any substantial text you did not write yourself.

Don't drop images from Google search onto your pages. Use your own photos, public-domain or Creative Commons material (respecting attribution requirements), or properly licensed assets. Getting this wrong is one of the easiest ways to land in genuine trouble—and one of the easiest to avoid.