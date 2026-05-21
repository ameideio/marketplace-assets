# ameideio/marketplace-assets

**Public** companion to [io-ameide-marketplace-azure](https://github.com/ameideio/io-ameide-marketplace-azure) — holds the offer assets (logos, screenshots, etc.) that Microsoft Marketplace must be able to fetch over HTTPS during cert review.

## Why a separate repo
`io-ameide-marketplace-azure` is **internal**, so its `raw.githubusercontent.com` URLs return 404 to anonymous fetchers (including Microsoft's listing-asset validator). The marketplace render.sh pulls asset URLs from THIS repo's `main` branch instead.

## Layout
```
offers/<offer-family>/<asset-category>/<file>
```

Today:
- `offers/public-cloud/listing/small.png`  — `azureLogoSmall`  (48×48)
- `offers/public-cloud/listing/medium.png` — `azureLogoMedium` (90×90)
- `offers/public-cloud/listing/large.png`  — `azureLogoLarge`  (216×216)

## Source of truth
Same as everything else in the Ameide stack: **git is master**. Changes flow PR → main → raw.githubusercontent.com → Microsoft's validator. No KV, no Storage account, no AFD content origin.

## Replacing placeholders
The PNGs committed today are solid-color placeholders. Replace with real Ameide brand artwork at the same paths/dimensions — render.sh URL emission is content-blind.
