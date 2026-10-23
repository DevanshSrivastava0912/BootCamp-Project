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

## Project rules
- Data access goes through `src/lib/companyRepository.ts` only; normalizers in `src/lib/companyData.ts` take raw short_json/full_json/skill_levels shapes — keeps the seed→database swap a one-file change.
- Selected company lives in CompanyContext + localStorage key `selected-company`; company pages restore from it and redirect to `/` when missing — pages must survive refresh without server state.
- Intelligence section/field schema lives only in `src/data/intelligenceData.tsx`; a test asserts every profile key appears exactly once.
- Category/Bloom/criticality class strings live in `src/lib/styleMaps.ts` as literals so Tailwind can detect them.
