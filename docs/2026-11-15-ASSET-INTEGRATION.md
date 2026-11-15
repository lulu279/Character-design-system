# Integration Guide — how to merge this pack into Character-design-system

## 1. What was verified in the repository

The public `main` README identifies the repository as Cards Pack v2.0 and lists these top-level areas: `characters/`, `styles/`, `references/`, `templates/`, `docs/`, `examples/`, `prompts/`, and `workflow/`.

The README also defines the core boundary:

- `CHAR`: identity, proportions, anatomy, recognition anchors, and wardrobe variants.
- `STYLE`: linework, lighting, colour, materials, and depth of field.
- `SHOT`: the current image's outfit, action, expression, camera, scene, composition, and output scope.

This pack follows that boundary. It does **not** introduce a new wardrobe-management subsystem.

**Audit limitation:** the public root README and top-level directory names were readable, but the web fetch of individual GitHub subdirectories was blocked in this session. Therefore the exact existing filenames inside `characters/`, `styles/`, `templates/`, and `docs/` were not fully audited. The paths below are additive proposals; compare them with your local checkout before copying. Do not overwrite similarly named files.

## 2. Proposed destination mapping

| Pack path | Suggested repository destination | Merge rule |
|---|---|---|
| `cards/DeepSeek/outfits/` | `characters/outfits/DEEPSEEK/` | Add outfit-variant cards; link them from the existing `CHAR-DEEPSEEK` card. Do not replace identity/anatomy text. |
| `cards/Yaoyao/outfits/` | `characters/outfits/YAOYAO/` | Add only the two current outfit variants; link them from the existing Yaoyao character card. |
| `styles/drafts/` | `styles/drafts/` | Keep drafts separate from confirmed styles. Promote only after explicit user confirmation and a traceable reference image. |
| `prompts/scenes/` | `prompts/scenes/` | Add reusable scene briefs and SHOT prompt modules. Each output image remains a separate SHOT. |
| `prompts/modules/` | `prompts/modules/` | Add reusable light/material state blocks. Do not confuse these with character identity. |
| `templates/` | `templates/` | Add the outfit-variant and SHOT templates only if equivalent templates do not already exist. |
| `workflow/` | `workflow/` | Add the QA checklist; merge only if a matching checklist already exists. |
| `docs/ASSET_INDEX_ADDENDUM.csv` | `docs/` | Merge rows into the existing asset index after checking IDs for duplicates. |
| `references/` | `references/wardrobe/` or local-only project references | Separate user references from generated examples. Check rights before public commit. |
| `examples/` | `examples/` | Add only reviewed, independent examples; do not use contact sheets as proof of single-image validation. |

## 3. Minimal merge sequence

1. Create a local feature branch.
2. Compare the package's card IDs with the local asset index. Preserve all existing IDs and versions.
3. Copy the DeepSeek and Yaoyao outfit cards into the proposed `characters/outfits/` folders.
4. Add a short variant table to each existing character card. The character card should point to outfit-card IDs; it should not duplicate every garment detail.
5. Copy the two lighting drafts into `styles/drafts/`. Do **not** add them to the confirmed style index yet.
6. Copy the scene briefs and SHOT modules into `prompts/scenes/` and `prompts/modules/`.
7. Compare and add the outfit / SHOT templates under `templates/` if no equivalent template exists.
8. Add the QA checklist to `workflow/` and merge the asset-index rows.
9. Keep the reference images local until you have reviewed their licensing and publication suitability.
10. Update the root README only with a short link to the new asset index / integration note. Do not rewrite the existing CHAR/STYLE/SHOT explanation.
11. Run `git diff --check`, inspect the staged file list, and commit locally.

## 4. Suggested local commands

Run from your local repository root. Adjust paths if your checkout already uses a different convention.

```bash
# 1) Create a local branch
git switch -c add-wardrobe-lighting-scenes-2026-11-15

# 2) Copy additive content (review the paths before running)
cp -R /path/to/Character-design-system-update-2026-11-15/cards/DeepSeek/outfits ./characters/outfits/DEEPSEEK
cp -R /path/to/Character-design-system-update-2026-11-15/cards/Yaoyao/outfits ./characters/outfits/YAOYAO
mkdir -p styles/drafts prompts/scenes prompts/modules templates
cp -R /path/to/Character-design-system-update-2026-11-15/styles/drafts/. styles/drafts/
cp -R /path/to/Character-design-system-update-2026-11-15/prompts/scenes/. prompts/scenes/
cp -R /path/to/Character-design-system-update-2026-11-15/prompts/modules/. prompts/modules/
cp -R /path/to/Character-design-system-update-2026-11-15/templates/. templates/
cp /path/to/Character-design-system-update-2026-11-15/workflow/ASSET-QA-CHECKLIST.md workflow/

# 3) Review before adding references or public images
git status --short
git diff --check

# 4) Stage only reviewed files
git add characters styles/drafts prompts/scenes prompts/modules workflow docs

git diff --cached --stat
git commit -m "Add seasonal wardrobe and scene asset cards"
```

The commands intentionally do not copy `references/` into a public repository. Keep those files local unless their source and licensing are verified.

## 5. What must not be changed

- Do not replace `CHAR-DEEPSEEK` identity anchors or the whale-tail anatomy lock with outfit-specific content.
- Do not let a lighting card change the character's face, proportions, tail anatomy, or outfit.
- Do not promote `STYLE-LANTERN-POINT-LIGHT` or `STYLE-NOON-COASTAL-DIRECTIONAL` from draft to confirmed without user approval and a traceable reference.
- Do not treat the multi-panel seven-scene fishing board, the four-season collage, or the Yaoyao chocolate contact sheet as independent illustrations.
- Do not use the superseded Yaoyao sheer/bralette homewear drafts as the current indoor outfit. The current indoor direction is the plain white cotton T-shirt and home shorts.
- Do not use the sunset tide-pool image as evidence of the final noon-light requirement.

## 6. Why this is the smallest viable change

The existing system already separates identity, rendering style, and single-image instructions. The additions are therefore limited to:

- wardrobe variants linked from the character cards;
- two candidate lighting modules;
- reusable scene briefs and SHOT blocks;
- an asset index addendum and a validation checklist.

No new database, application, schema migration, or root-level subsystem is required.
