# Map My Argument — v2 interface refresh

## What's new
- Name entry is the first step. Returning visitors can see a list of arguments to assess.
- A prominent **Create a new argument** button leads to the creation screen.
- Argument cards lead directly to assessment, or to results if the entered name already submitted.
- Redesigned typography, spacing, colors, premise cards, bell curves, and group results.
- Individual confidence ratings and evidence strengths appear alongside group averages.
- Local preview works before publishing. Online shared arguments require Supabase.

## Preview on Windows
Extract the ZIP and open `index.html` in Chrome or Edge. If your browser blocks JavaScript modules from local files, open a terminal in the extracted folder and run `py -m http.server 8000`, then visit `http://localhost:8000`.

## Later: publish
1. Create a Supabase project, and run `supabase.sql` in SQL Editor.
2. Copy your Supabase project URL and **publishable/anon key** into `config.js`. Never use a service-role key in public frontend code.
3. Upload all files in this folder to a GitHub repository. Enable GitHub Pages (main branch, root).
4. Test with two names and two browsers.

## Important limitations
- Without Supabase, arguments and submissions exist only in the same browser's local storage; links do not sync across devices.
- Name-only identification is not secure authentication. Anyone using another participant's name can access their results.
- The provided public Supabase read policies do **not** technically protect pre-submission results. The UI hides them, but anyone can query the public database. Do not use for sensitive arguments.
- The scoring algorithm is an illustrative heuristic, **not a statistical probability**. Correlated premises can double-count evidence.
- A shared argument's wording is locked after publication, and each display name has one immutable assessment per argument.
- The argument hub shows up to 100 most recent arguments in online mode; production should add pagination, abuse prevention, and moderation.
