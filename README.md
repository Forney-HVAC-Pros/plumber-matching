# Forney Plumbing Pros — plumber matching tool

Public GitHub Pages embed for [forneyplumbingpros.com](https://forneyplumbingpros.com). Forney Plumbing Pros is a **free matching service, not a plumbing contractor**. This tool does not list or recommend a specific plumber until a signed partner is in place.

Live pages (after GitHub Pages is enabled):

- Full quiz: `https://forney-hvac-pros.github.io/plumber-matching/`
- Compact iframe: `https://forney-hvac-pros.github.io/plumber-matching/mini.html`
- Inline Durable snippet: `durable-snippet.html` (paste into a Durable custom-code block)

## Behavior

- Quiz: service (water heater, leak/slab leak, drain/sewer, gas line, softener, freeze/burst pipe, other), urgency, and city. Supports `?city=forney` (and other city slugs), plus optional `?service=` and `?urgency=`.
- Results CTA is the site number, **(469) 200-0065**. Quote form is secondary.
- Quote form posts to Formspree. **Endpoint:** `FORMSPREE_ENDPOINT = 'https://formspree.io/f/mrpqpola'` in `index.html`, `mini.html`, and `durable-snippet.html`. (Formspree account contact@forneyplumbingpros.com; do not reuse the HVAC form ID.)
- Hidden fields capture `gclid`, `gbraid`, `wbraid`, UTMs, `landing_page`, and `attr_ts`. Includes an `also_needs_hvac` checkbox that cross-sells [forneyhvacpros.com](https://forneyhvacpros.com).
- Contact: (469) 200-0065 · [contact@forneyplumbingpros.com](mailto:contact@forneyplumbingpros.com)
- GA4 `G-9LSH07TDFN` loads only when the page is opened directly. When iframed, events are posted to `forneyplumbingpros.com` as `{ type: 'fpp-event', ... }`. Height is posted as `{ iframeHeight }`.
- Events: `tool_started`, `question_answered`, `results_viewed`, `call_clicked`, `quote_form_opened`, `lead_submitted`, plus `generate_lead` after a successful form post. Events are tagged with `site: 'plumbing'` (same GA4 property as HVAC).

See `/workspace/forney-plumbing/EMBEDS.md` for Durable iframe snippets and the global head code.
