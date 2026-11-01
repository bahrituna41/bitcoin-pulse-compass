<!-- LOVABLE:BEGIN -->
> [!IMPORTANT]
> This project is connected to [Lovable](https://lovable.dev). Avoid rewriting
> published git history — force pushing, or rebasing/amending/squashing commits
> that are already pushed — as it rewrites history on Lovable's side and the
> user will likely lose their project history.
>
> Commits you push to the connected branch sync back to Lovable and show up in
> the editor, so keep the branch in a working state.
<!-- LOVABLE:END -->
- The only content screen is FractalTerminal with FractalChart and the reusable local watchlist; obsolete CRT and macro screens are removed to prevent accidental restoration.
- Fractal detection lives in pure tested src/lib/fractal-engine.ts, translated from references/fractal_fxraptor_POI.pine; replay uses closed LTF bars and never future HTF extrema to avoid hindsight signals.
- Shared candle types and timeframe utilities remain in indicators.ts and terminal-engine.ts; the Fractal UI never invokes the legacy range/MMXM strategies.
- Metals use Yahoo COMEX futures through metals.functions.ts, not spot prices; UTC 4H aggregation and potential delays must remain disclosed.
- Market query keys include the actual asset and timeframe; browser and scheduled detection must invoke the same pure Fractal engine to avoid strategy drift.
- Telegram destinations are opt-in via signed Telegram /start and /stop webhooks; groups require a Telegram administrator, and service-role-only RLS tables keep destination identifiers private.
- Scheduled sends use managed cron authentication and durable unique per-event/per-chat delivery claims; ambiguous provider failures must never be blindly retried because that can duplicate alerts.
- Automatic SMT library mapping is unavailable in the uploaded source; explicit comparison/inversion controls replace it, and exact TradingView tick parity must not be claimed without an external comparison.
