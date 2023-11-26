# Precategories with families

```agda
module type-theories.precategories-with-families where
```

<details><summary>Imports</summary>

```agda
open import category-theory.functors-precategories
open import category-theory.natural-transformations-functors-precategories
open import category-theory.opposite-precategories
open import category-theory.precategories
open import category-theory.precategory-of-elements-of-a-presheaf
open import category-theory.pullbacks-in-precategories

open import foundation.cartesian-product-types
open import foundation.category-of-sets
open import foundation.dependent-pair-types
open import foundation.equivalences
open import foundation.function-extensionality
open import foundation.identity-types
open import foundation.sections
open import foundation.sets
open import foundation.subtypes
open import foundation.transport-along-identifications
open import foundation.universe-levels
```

</details>

## Idea

A **precategory with families** consists of:

- a [precategory](category-theory.precategories.md) `C`, which we think of as a
  category of contexts and context morphisms
- a [presheaf](category-theory.presheaf-categories.md) `Ty` on `C`, which we
  think of as giving the types in each context
- a [presheaf](category-theory.presheaf-categories.md) `Tm` on `∫ Ty`, which we
  think of as giving the terms of each type in each context
- a [functor](category-theory.functors-precategories.md) `ext` from `∫ Ty` to
  `C`, which we think of as context extension such that
- for every pair of contexts `Γ` and `Δ`, and types `A` in context `Γ`, there is
  an equivalence between the type of context morphisms from `Δ` to `Γ` extended
  by `A`, and the type of context morphisms from `Δ` to `Γ` together with terms
  of `A`.

## Definitions

### Precategories with families

```agda
record
  Precategory-With-Families
    (l1 l2 l3 : Level) :
    UU (lsuc l1 ⊔ lsuc l2 ⊔ lsuc l3)
  where

  field
    ctx-category : Precategory l1 l2

  Ctx : UU l1
  Ctx = obj-Precategory ctx-category

  Sub : Ctx → Ctx → UU l2
  Sub = hom-Precategory ctx-category

  field
    ty-functor :
      functor-Precategory
        ( opposite-Precategory ctx-category)
        ( Set-Precategory l3)

  Ty : Ctx → UU l3
  Ty Γ =
    type-Set
      ( obj-functor-Precategory
        ( opposite-Precategory ctx-category)
        ( Set-Precategory l3)
        ( ty-functor)
        ( Γ))

  _·_ : {Δ Γ : Ctx} (A : Ty Γ) (γ : Sub Δ Γ) → Ty Δ
  A · γ =
    hom-functor-Precategory
      ( opposite-Precategory ctx-category)
      ( Set-Precategory l3)
      ( ty-functor)
      ( γ)
      ( A)

  preserves-composition-Ty :
    {Δ Δ' Γ : Ctx} (A : Ty Γ) (γ : Sub Δ' Γ) (δ : Sub Δ Δ') →
    A · comp-hom-Precategory ctx-category γ δ ＝ (A · γ) · δ
  preserves-composition-Ty A γ δ =
    htpy-eq
      ( preserves-comp-functor-Precategory
        ( opposite-Precategory ctx-category)
        ( Set-Precategory l3)
        ( ty-functor)
        ( δ)
        ( γ))
      ( A)

  preserves-id-Ty :
    {Γ : Ctx} (A : Ty Γ) → A · id-hom-Precategory ctx-category ＝ A
  preserves-id-Ty {Γ} =
    htpy-eq
      ( preserves-id-functor-Precategory
        ( opposite-Precategory ctx-category)
        ( Set-Precategory l3)
        ( ty-functor)
        ( Γ))

  field
    tm-functor :
      functor-Precategory
        ( opposite-Precategory (element-Precategory ctx-category ty-functor))
        ( Set-Precategory l3)

  Tm : (Γ : Ctx) (A : Ty Γ) → UU l3
  Tm Γ A = pr1 (pr1 tm-functor (Γ , A))

  _[_] :
    {Δ Γ : Ctx} {A : Ty Γ} (M : Tm Γ A) (γ : Sub Δ Γ) → Tm Δ (A · γ)
  _[_] {Δ} {Γ} {A} M γ =
    hom-functor-Precategory
      ( opposite-Precategory (element-Precategory ctx-category ty-functor))
      ( Set-Precategory l3)
      ( tm-functor)
      ( γ , refl)
      ( M)

  field
    ext-functor :
      functor-Precategory
        ( element-Precategory ctx-category ty-functor)
        ( ctx-category)

  ext : (Γ : Ctx) (A : Ty Γ) → Ctx
  ext Γ A =
    obj-functor-Precategory
      ( element-Precategory ctx-category ty-functor)
      ( ctx-category)
      ( ext-functor)
      ( Γ , A)

  field
    ext-iso :
      (Δ Γ : Ctx) (A : Ty Γ) →
      hom-Precategory ctx-category Δ (ext Γ A) ≃
      Σ (hom-Precategory ctx-category Δ Γ) (λ γ → Tm Δ (A · γ))

  ext-sub :
    {Δ Γ : Ctx} (A : Ty Γ) (γ : Sub Δ Γ) → Tm Δ (A · γ) → Sub Δ (ext Γ A)
  ext-sub {Δ} {Γ} A γ M = map-inv-equiv (ext-iso Δ Γ A) (γ , M)

  wk : {Γ : Ctx} (A : Ty Γ) → Sub (ext Γ A) Γ
  wk {Γ} A =
    pr1 (map-equiv (ext-iso (ext Γ A) Γ A) (id-hom-Precategory ctx-category))

  q : {Γ : Ctx} (A : Ty Γ) → Tm (ext Γ A) (A · wk A)
  q {Γ} A =
    pr2 (map-equiv (ext-iso (ext Γ A) Γ A) (id-hom-Precategory ctx-category))

  ⟨_,_⟩ :
    {Δ Γ : Ctx} (γ : Sub Δ Γ) (A : Ty Γ) → Sub (ext Δ (A · γ)) (ext Γ A)
  ⟨_,_⟩ {Δ} {Γ} γ A =
    ext-sub
      ( A)
      ( comp-hom-Precategory ctx-category γ (wk (A · γ)))
      ( tr
        ( Tm (ext Δ (A · γ)))
        ( inv (preserves-composition-Ty A γ (wk (A · γ))))
        ( q (A · γ)))
```