# Precategories with attributes

```agda
module type-theories.precategories-with-attributes where
```

<details><summary>Imports</summary>

```agda
open import category-theory.functors-precategories
open import category-theory.natural-transformations-functors-precategories
open import category-theory.opposite-precategories
open import category-theory.precategories
open import category-theory.precategory-of-elements-of-a-presheaf
open import category-theory.pullbacks-in-precategories

open import foundation.action-on-identifications-functions
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

A **precategory with attributes** consists of:

- a [precategory](category-theory.precategories.md) `C`, which we think of as a
  category of contexts and context morphisms
- a [presheaf](category-theory.presheaf-categories.md) `Ty` on `C`, which we
  think of as giving the types in each context
- a [functor](category-theory.functors-precategories.md) `ext` from `∫ Ty` to
  `C`, which we think of as context extension
- a
  [natural transformation](category-theory.natural-transformations-functors-precategories.md)
  `p` from `ext` to the projection from `∫ Ty` to `C` such that
- the naturality squares of `p` are
  [pullback](category-theory.pullbacks-in-precategories.md) squares

This is a reformulation of Definition 1, slide 24 of
<https://staff.math.su.se/palmgren/ErikP_Variants_CWF.pdf>

```agda
record Precategory-With-Attributes {l1 l2 : Level}
  (C : Precategory l1 l2) (l3 : Level) : UU (l1 ⊔ l2 ⊔ lsuc l3) where
  field
    Ty-F : functor-Precategory (opposite-Precategory C) (Set-Precategory l3)
    ext : functor-Precategory (element-Precategory C Ty-F) C
    p : natural-transformation-Precategory
          (element-Precategory C Ty-F)
          C
          ext
          (proj₁-functor-element-Precategory C Ty-F)
    is-pullback-p :
      (x y : obj-Precategory (element-Precategory C Ty-F)) →
      (f : hom-Precategory (element-Precategory C Ty-F) x y) →
      is-pullback-Precategory C _ _ _ _ _ _ _ _
        (naturality-natural-transformation-Precategory
          (element-Precategory C Ty-F)
          C
          ext
          (proj₁-functor-element-Precategory C Ty-F) p f)

  -- Notation
  Ctx : UU l1
  Ctx = obj-Precategory C

  Sub : Ctx → Ctx → UU l2
  Sub = hom-Precategory C

  Ty : Ctx → UU l3
  Ty Γ = pr1 (pr1 Ty-F Γ)

  _⋆_ : (Γ : Ctx) →
      (A : type-Set
            (obj-functor-Precategory
              (opposite-Precategory C)
              (Set-Precategory l3) Ty-F Γ)) →
      Ctx
  Γ ⋆ A = pr1 ext (Γ , A)

  _·_ : {Γ Δ : Ctx} →
      (A : Ty Δ) →
      (σ : Sub Γ Δ) →
      Ty Γ
  A · σ = pr1 (pr2 Ty-F) σ A

  ⟨_,_⟩ : {Γ Δ : Ctx} (σ : Sub Γ Δ) (A : Ty Δ) →
        Sub (Γ ⋆ (A · σ)) (Δ ⋆ A)
  ⟨ σ , A ⟩ = pr1 (pr2 ext) (σ , refl)
```

The terms are defined as sections to `ext`.

```agda
  module _ (Γ : Ctx)
    (A : type-Set
          (obj-functor-Precategory
            (opposite-Precategory C)
            (Set-Precategory l3) Ty-F Γ))
    where

    Tm : UU l2
    Tm = Σ (Sub Γ (Γ ⋆ A)) λ t →
            comp-hom-Precategory C (pr1 p (Γ , A)) t ＝ id-hom-Precategory C

    is-set-Tm : is-set Tm
    is-set-Tm =
      is-set-type-subtype
        (λ t →
          Id-Prop
            (hom-set-Precategory C Γ Γ)
            (comp-hom-Precategory C (pr1 p (Γ , A)) t)
            (id-hom-Precategory C))
        (is-set-hom-Precategory C Γ (Γ ⋆ A))

    Tm-Set : Set l2
    pr1 Tm-Set = Tm
    pr2 Tm-Set = is-set-Tm

  _[_] : {Γ Δ : Ctx} →
    {A : Ty Δ} →
    (t : Tm Δ A) →
    (σ : Sub Γ Δ) →
    Tm Γ (A · σ)
  _[_] {Γ} {Δ} {A} (s , eq) σ = (pr1 gap-map , pr1 (pr2 gap-map))
    where
    sq : comp-hom-Precategory C σ (id-hom-Precategory C) ＝
      comp-hom-Precategory C (pr1 p (Δ , A)) (comp-hom-Precategory C s σ)
    sq =
      equational-reasoning
        comp-hom-Precategory C σ (id-hom-Precategory C)
          ＝ σ by right-unit-law-comp-hom-Precategory C σ
          ＝ comp-hom-Precategory
              C
              (id-hom-Precategory C)
              σ by inv (left-unit-law-comp-hom-Precategory C σ)
          ＝ comp-hom-Precategory C
              (comp-hom-Precategory C (pr1 p (Δ , A)) s)
              σ by ap (λ k → comp-hom-Precategory C k σ) (inv eq)
          ＝ comp-hom-Precategory C
              (pr1 p (Δ , A))
              (comp-hom-Precategory C s σ)
              by associative-comp-hom-Precategory C _ _ _

    gap-map : Σ (Sub Γ (Γ ⋆ (A · σ))) λ g →
            (comp-hom-Precategory C (pr1 p (Γ , (A · σ))) g ＝
              id-hom-Precategory C) ×
            (comp-hom-Precategory C (pr1 (pr2 ext) (σ , refl)) g ＝
              comp-hom-Precategory C s σ)
    gap-map =
      pr1
        (is-pullback-p (Γ , (A · σ)) (Δ , A) (σ , refl) Γ (id-hom-Precategory C)
          (comp-hom-Precategory C s σ) sq)
```

### Π-types in a precategory with attributes

```agda
record Π-structure-Precategory-With-Attributes {l1 l2}
  (C : Precategory l1 l2) (l3 : Level)
  (cwa : Precategory-With-Attributes C l3) : UU (l1 ⊔ l2 ⊔ lsuc l3) where
  open Precategory-With-Attributes cwa

  field
    Π : {Γ : Ctx} (A : Ty Γ) (B : Ty (Γ ⋆ A)) → Ty Γ
    Π-iso : {Γ : Ctx} (A : Ty Γ) (B : Ty (Γ ⋆ A)) →
          Tm Γ (Π A B) ≃ Tm (Γ ⋆ A) B

  app : {Γ : Ctx} (A : Ty Γ) (B : Ty (Γ ⋆ A)) →
      Tm Γ (Π A B) → Tm (Γ ⋆ A) B
  app A B = map-equiv (Π-iso A B)

  lam : {Γ : Ctx} (A : Ty Γ) (B : Ty (Γ ⋆ A)) →
      Tm (Γ ⋆ A) B → Tm Γ (Π A B)
  lam A B = map-inv-equiv (Π-iso A B)

  field
    Π-sub-law : {Γ Δ : Ctx} (A : Ty Δ) (B : Ty (Δ ⋆ A)) (σ : Sub Γ Δ) →
              ((Π A B) · σ) ＝ Π (A · σ) (B · ⟨ σ , A ⟩)
    Π-iso-sub-law : {Γ Δ : Ctx} (A : Ty Δ) (B : Ty (Δ ⋆ A)) (σ : Sub Γ Δ) →
      (t : Tm Δ (Π A B)) →
      app (A · σ) (B · ⟨ σ , A ⟩) (tr (Tm Γ) (Π-sub-law A B σ) (t [ σ ])) ＝
      (app A B t [ ⟨ σ , A ⟩ ])
```