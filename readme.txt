# Deprecation API Issue Demo

This repository demonstrates a potential issue with the block deprecation API when migrating a block from static to dynamic. In some cases, the migration doesn't apply correctly.

---

## ✅ Working Case

1. Switch to `working/branch-1`. The `save` function returns a `<p>`.
2. Create a new post.
3. Add the **Todo Block**.
4. Save the post.
5. Switch to `working/branch-2`, where the `save` function returns `null`.
   ➤ The deprecation API works correctly, and the block remains valid.

---

## ❌ Not Working Case

1. Switch to `not-working/branch-1`. The `save` function returns a `<div>`.
2. Create a new post.
3. Add the **Todo Block**.
4. Save the post.
5. Switch to `not-working/branch-2`, where the `save` function also returns a `<div>`.
   ➤ Despite the deprecation API, the block is flagged as invalid.