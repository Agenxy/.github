# Social cards

The 1280x640 repository social previews and the organisation avatar, as
uploaded to each repository's **Settings -> Social preview**.

They are generated, not drawn: `tools/build_marks.py` in the (private) `web`
repository renders them from the same Source Serif 4 and Fragment Mono files
the site itself uses, with the palette parsed out of `tokens.css` and each
project's name, line and standing read from the register. Regenerating is how
they change; editing a PNG here would only drift from the source.

They live in this repository because everything Agenxy publishes should be
served from something Agenxy owns, and because the upload form needs to fetch
them from somewhere public.

| File | Repository |
|---|---|
| `social-org.png` | `Agenxy/.github` |
| `social-dibs.png` | `Agenxy/dibs` |
| `social-remap.png` | `Agenxy/remap` |
| `social-supgang.png` | `Agenxy/supgang` |
| `social-homebrew-tap.png` | `Agenxy/homebrew-tap` |
| `avatar.png` | the organisation avatar |
