# Weekly Flyer Update SOP (Pilot)

## Scope
Pilot stores: T&T, H Mart, Safeway, IGA (Downtown Vancouver).

## Weekly cadence
- Run once every week (same weekday/time).

## Steps
1. Open `data/flyers_weekly.csv`.
2. Set `week_start` to current week date for all pilot rows.
3. Check each store’s latest flyer source.
4. Update `flyer_url` and `flyer_format`.
5. Set `status`:
   - `updated` = current-week flyer found
   - `no_update` = no current flyer found
   - `broken` = source link invalid/error
6. Set `last_checked` timestamp.
7. Add any issue notes in `notes`.

## Quality checks
- All 4 pilot stores present.
- No blank `status`.
- `last_checked` filled for all rows.
