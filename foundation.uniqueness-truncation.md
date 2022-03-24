# Uniqueness of the truncations

<pre class="Agda"><a id="42" class="Symbol">{-#</a> <a id="46" class="Keyword">OPTIONS</a> <a id="54" class="Pragma">--without-K</a> <a id="66" class="Pragma">--exact-split</a> <a id="80" class="Pragma">--allow-unsolved-metas</a> <a id="103" class="Symbol">#-}</a>

<a id="108" class="Keyword">module</a> <a id="115" href="foundation.uniqueness-truncation.html" class="Module">foundation.uniqueness-truncation</a> <a id="148" class="Keyword">where</a>

<a id="155" class="Keyword">open</a> <a id="160" class="Keyword">import</a> <a id="167" href="foundation.dependent-pair-types.html" class="Module">foundation.dependent-pair-types</a> <a id="199" class="Keyword">using</a> <a id="205" class="Symbol">(</a><a id="206" href="foundation-core.dependent-pair-types.html#502" class="Record">Σ</a><a id="207" class="Symbol">;</a> <a id="209" href="foundation-core.dependent-pair-types.html#575" class="InductiveConstructor">pair</a><a id="213" class="Symbol">;</a> <a id="215" href="foundation-core.dependent-pair-types.html#592" class="Field">pr1</a><a id="218" class="Symbol">;</a> <a id="220" href="foundation-core.dependent-pair-types.html#604" class="Field">pr2</a><a id="223" class="Symbol">)</a>
<a id="225" class="Keyword">open</a> <a id="230" class="Keyword">import</a> <a id="237" href="foundation.equivalences.html" class="Module">foundation.equivalences</a> <a id="261" class="Keyword">using</a> <a id="267" class="Symbol">(</a><a id="268" href="foundation-core.equivalences.html#1542" class="Function">is-equiv</a><a id="276" class="Symbol">)</a>
<a id="278" class="Keyword">open</a> <a id="283" class="Keyword">import</a> <a id="290" href="foundation.functions.html" class="Module">foundation.functions</a> <a id="311" class="Keyword">using</a> <a id="317" class="Symbol">(</a><a id="318" href="foundation-core.functions.html#407" class="Function Operator">_∘_</a><a id="321" class="Symbol">;</a> <a id="323" href="foundation-core.functions.html#309" class="Function">id</a><a id="325" class="Symbol">)</a>
<a id="327" class="Keyword">open</a> <a id="332" class="Keyword">import</a> <a id="339" href="foundation.homotopies.html" class="Module">foundation.homotopies</a> <a id="361" class="Keyword">using</a> <a id="367" class="Symbol">(</a><a id="368" href="foundation-core.homotopies.html#467" class="Function Operator">_~_</a><a id="371" class="Symbol">)</a>
<a id="373" class="Keyword">open</a> <a id="378" class="Keyword">import</a> <a id="385" href="foundation.truncated-types.html" class="Module">foundation.truncated-types</a> <a id="412" class="Keyword">using</a>
  <a id="420" class="Symbol">(</a> <a id="422" href="foundation-core.truncated-types.html#1651" class="Function">Truncated-Type</a><a id="436" class="Symbol">;</a> <a id="438" href="foundation-core.truncated-types.html#1786" class="Function">type-Truncated-Type</a><a id="457" class="Symbol">;</a> <a id="459" href="foundation.truncated-types.html#3483" class="Function">type-hom-Truncated-Type</a><a id="482" class="Symbol">)</a>
<a id="484" class="Keyword">open</a> <a id="489" class="Keyword">import</a> <a id="496" href="foundation.truncation-levels.html" class="Module">foundation.truncation-levels</a> <a id="525" class="Keyword">using</a> <a id="531" class="Symbol">(</a><a id="532" href="foundation-core.truncation-levels.html#382" class="Datatype">𝕋</a><a id="533" class="Symbol">)</a>
<a id="535" class="Keyword">open</a> <a id="540" class="Keyword">import</a> <a id="547" href="foundation.universal-property-truncation.html" class="Module">foundation.universal-property-truncation</a> <a id="588" class="Keyword">using</a>
  <a id="596" class="Symbol">(</a> <a id="598" href="foundation.universal-property-truncation.html#1985" class="Function">is-truncation</a><a id="611" class="Symbol">)</a>
<a id="613" class="Keyword">open</a> <a id="618" class="Keyword">import</a> <a id="625" href="foundation.universe-levels.html" class="Module">foundation.universe-levels</a> <a id="652" class="Keyword">using</a> <a id="658" class="Symbol">(</a><a id="659" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="664" class="Symbol">;</a> <a id="666" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a><a id="668" class="Symbol">)</a>
</pre>
## Idea

The universal property of n-truncations implies that n-truncations are determined uniquely up to a unique equivalence.

<pre class="Agda"><a id="812" class="Keyword">module</a> <a id="819" href="foundation.uniqueness-truncation.html#819" class="Module">_</a>
  <a id="823" class="Symbol">{</a><a id="824" href="foundation.uniqueness-truncation.html#824" class="Bound">l1</a> <a id="827" href="foundation.uniqueness-truncation.html#827" class="Bound">l2</a> <a id="830" href="foundation.uniqueness-truncation.html#830" class="Bound">l3</a> <a id="833" class="Symbol">:</a> <a id="835" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="840" class="Symbol">}</a> <a id="842" class="Symbol">(</a><a id="843" href="foundation.uniqueness-truncation.html#843" class="Bound">k</a> <a id="845" class="Symbol">:</a> <a id="847" href="foundation-core.truncation-levels.html#382" class="Datatype">𝕋</a><a id="848" class="Symbol">)</a> <a id="850" class="Symbol">{</a><a id="851" href="foundation.uniqueness-truncation.html#851" class="Bound">A</a> <a id="853" class="Symbol">:</a> <a id="855" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="858" href="foundation.uniqueness-truncation.html#824" class="Bound">l1</a><a id="860" class="Symbol">}</a>
  <a id="864" class="Symbol">(</a><a id="865" href="foundation.uniqueness-truncation.html#865" class="Bound">B</a> <a id="867" class="Symbol">:</a> <a id="869" href="foundation-core.truncated-types.html#1651" class="Function">Truncated-Type</a> <a id="884" href="foundation.uniqueness-truncation.html#827" class="Bound">l2</a> <a id="887" href="foundation.uniqueness-truncation.html#843" class="Bound">k</a><a id="888" class="Symbol">)</a> <a id="890" class="Symbol">(</a><a id="891" href="foundation.uniqueness-truncation.html#891" class="Bound">f</a> <a id="893" class="Symbol">:</a> <a id="895" href="foundation.uniqueness-truncation.html#851" class="Bound">A</a> <a id="897" class="Symbol">→</a> <a id="899" href="foundation-core.truncated-types.html#1786" class="Function">type-Truncated-Type</a> <a id="919" href="foundation.uniqueness-truncation.html#865" class="Bound">B</a><a id="920" class="Symbol">)</a>
  <a id="924" class="Symbol">(</a><a id="925" href="foundation.uniqueness-truncation.html#925" class="Bound">C</a> <a id="927" class="Symbol">:</a> <a id="929" href="foundation-core.truncated-types.html#1651" class="Function">Truncated-Type</a> <a id="944" href="foundation.uniqueness-truncation.html#830" class="Bound">l3</a> <a id="947" href="foundation.uniqueness-truncation.html#843" class="Bound">k</a><a id="948" class="Symbol">)</a> <a id="950" class="Symbol">(</a><a id="951" href="foundation.uniqueness-truncation.html#951" class="Bound">g</a> <a id="953" class="Symbol">:</a> <a id="955" href="foundation.uniqueness-truncation.html#851" class="Bound">A</a> <a id="957" class="Symbol">→</a> <a id="959" href="foundation-core.truncated-types.html#1786" class="Function">type-Truncated-Type</a> <a id="979" href="foundation.uniqueness-truncation.html#925" class="Bound">C</a><a id="980" class="Symbol">)</a>
  <a id="984" class="Symbol">{</a><a id="985" href="foundation.uniqueness-truncation.html#985" class="Bound">h</a> <a id="987" class="Symbol">:</a> <a id="989" href="foundation.truncated-types.html#3483" class="Function">type-hom-Truncated-Type</a> <a id="1013" href="foundation.uniqueness-truncation.html#843" class="Bound">k</a> <a id="1015" href="foundation.uniqueness-truncation.html#865" class="Bound">B</a> <a id="1017" href="foundation.uniqueness-truncation.html#925" class="Bound">C</a><a id="1018" class="Symbol">}</a> <a id="1020" class="Symbol">(</a><a id="1021" href="foundation.uniqueness-truncation.html#1021" class="Bound">H</a> <a id="1023" class="Symbol">:</a> <a id="1025" class="Symbol">(</a><a id="1026" href="foundation.uniqueness-truncation.html#985" class="Bound">h</a> <a id="1028" href="foundation-core.functions.html#407" class="Function Operator">∘</a> <a id="1030" href="foundation.uniqueness-truncation.html#891" class="Bound">f</a><a id="1031" class="Symbol">)</a> <a id="1033" href="foundation-core.homotopies.html#467" class="Function Operator">~</a> <a id="1035" href="foundation.uniqueness-truncation.html#951" class="Bound">g</a><a id="1036" class="Symbol">)</a>
  <a id="1040" class="Keyword">where</a>

  <a id="1049" class="Keyword">abstract</a>
    <a id="1062" href="foundation.uniqueness-truncation.html#1062" class="Function">is-equiv-is-truncation-is-truncation</a> <a id="1099" class="Symbol">:</a>
      <a id="1107" class="Symbol">({</a><a id="1109" href="foundation.uniqueness-truncation.html#1109" class="Bound">l</a> <a id="1111" class="Symbol">:</a> <a id="1113" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="1118" class="Symbol">}</a> <a id="1120" class="Symbol">→</a> <a id="1122" href="foundation.universal-property-truncation.html#1985" class="Function">is-truncation</a> <a id="1136" href="foundation.uniqueness-truncation.html#1109" class="Bound">l</a> <a id="1138" href="foundation.uniqueness-truncation.html#865" class="Bound">B</a> <a id="1140" href="foundation.uniqueness-truncation.html#891" class="Bound">f</a><a id="1141" class="Symbol">)</a> <a id="1143" class="Symbol">→</a>
      <a id="1151" class="Symbol">({</a><a id="1153" href="foundation.uniqueness-truncation.html#1153" class="Bound">l</a> <a id="1155" class="Symbol">:</a> <a id="1157" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="1162" class="Symbol">}</a> <a id="1164" class="Symbol">→</a> <a id="1166" href="foundation.universal-property-truncation.html#1985" class="Function">is-truncation</a> <a id="1180" href="foundation.uniqueness-truncation.html#1153" class="Bound">l</a> <a id="1182" href="foundation.uniqueness-truncation.html#925" class="Bound">C</a> <a id="1184" href="foundation.uniqueness-truncation.html#951" class="Bound">g</a><a id="1185" class="Symbol">)</a> <a id="1187" class="Symbol">→</a>
      <a id="1195" href="foundation-core.equivalences.html#1542" class="Function">is-equiv</a> <a id="1204" href="foundation.uniqueness-truncation.html#985" class="Bound">h</a>
    <a id="1210" href="foundation.uniqueness-truncation.html#1062" class="Function">is-equiv-is-truncation-is-truncation</a> <a id="1247" href="foundation.uniqueness-truncation.html#1247" class="Bound">H</a> <a id="1249" href="foundation.uniqueness-truncation.html#1249" class="Bound">K</a> <a id="1251" class="Symbol">=</a>
      <a id="1259" href="foundation-core.dependent-pair-types.html#575" class="InductiveConstructor">pair</a>
        <a id="1272" class="Hole">{! sec-is-truncation!}</a>
        <a id="1303" class="Hole">{!!}</a>

<a id="1309" class="Comment">{-
      is-equiv-has-inverse 
        ( pr1 (center K))
        ( htpy-eq
          ( is-injective-is-equiv
            ( Ug C)
            { h ∘ k}
            { id}
            ( ( precomp-comp-Set-Quotient R C g B k C h) ∙
              ( ( ap (λ t → precomp-Set-Quotient R B t C h) α) ∙
                ( ( eq-htpy-reflecting-map-Eq-Rel R C
                    ( precomp-Set-Quotient R B f C h) g H) ∙
                  ( inv (precomp-id-Set-Quotient R C g)))))))
        ( htpy-eq
          ( is-injective-is-equiv
            ( Uf B)
            { k ∘ h}
            { id}
            ( ( precomp-comp-Set-Quotient R B f C h B k) ∙
              ( ( ap
                  ( λ t → precomp-Set-Quotient R C t B k)
                  ( eq-htpy-reflecting-map-Eq-Rel R C
                    ( precomp-Set-Quotient R B f C h) g H)) ∙
                ( ( α) ∙
                  ( inv (precomp-id-Set-Quotient R B f)))))))
      where
      K : is-contr
            ( Σ ( type-hom-Set C B)
                ( λ h →
                  ( h ∘ map-reflecting-map-Eq-Rel R g) ~
                  ( map-reflecting-map-Eq-Rel R f)))
      K = universal-property-set-quotient-is-set-quotient R C g Ug B f
      k : type-Set C → type-Set B
      k = pr1 (center K)
      α : Id (precomp-Set-Quotient R C g B k) f
      α = eq-htpy-reflecting-map-Eq-Rel R B
            ( precomp-Set-Quotient R C g B k)
            ( f)
            ( pr2 (center K))
            -}</a>

  
<a id="2765" class="Comment">{-
-- Uniqueness of set truncations

module _
  {l1 l2 l3 : Level} {A : UU l1} (B : UU-Set l2) (f : A → type-Set B)
  (C : UU-Set l3) (g : A → type-Set C) {h : type-hom-Set B C}
  (H : (h ∘ f) ~ g)
  where

  abstract
    is-equiv-is-set-truncation-is-set-truncation :
      ({l : Level} → is-set-truncation l B f) →
      ({l : Level} → is-set-truncation l C g) →
      is-equiv h
    is-equiv-is-set-truncation-is-set-truncation Sf Sg =
      is-equiv-is-set-quotient-is-set-quotient
        ( mere-eq-Eq-Rel A)
        ( B)
        ( reflecting-map-mere-eq B f)
        ( C)
        ( reflecting-map-mere-eq C g)
        ( H)
        ( λ {l} → is-set-quotient-is-set-truncation B f Sf)
        ( λ {l} → is-set-quotient-is-set-truncation C g Sg)

  abstract
    is-set-truncation-is-equiv-is-set-truncation :
      ({l : Level} → is-set-truncation l C g) → is-equiv h → 
      {l : Level} → is-set-truncation l B f
    is-set-truncation-is-equiv-is-set-truncation Sg Eh =
      is-set-truncation-is-set-quotient B f
        ( is-set-quotient-is-equiv-is-set-quotient
          ( mere-eq-Eq-Rel A)
          ( B)
          ( reflecting-map-mere-eq B f)
          ( C)
          ( reflecting-map-mere-eq C g)
          ( H)
          ( is-set-quotient-is-set-truncation C g Sg)
          ( Eh))

  abstract
    is-set-truncation-is-set-truncation-is-equiv :
      is-equiv h → ({l : Level} → is-set-truncation l B f) →
      {l : Level} → is-set-truncation l C g
    is-set-truncation-is-set-truncation-is-equiv Eh Sf =
      is-set-truncation-is-set-quotient C g
        ( is-set-quotient-is-set-quotient-is-equiv
          ( mere-eq-Eq-Rel A)
          ( B)
          ( reflecting-map-mere-eq B f)
          ( C)
          ( reflecting-map-mere-eq C g)
          ( H)
          ( Eh)
          ( is-set-quotient-is-set-truncation B f Sf))

module _
  {l1 l2 l3 : Level} {A : UU l1} (B : UU-Set l2) (f : A → type-Set B)
  (C : UU-Set l3) (g : A → type-Set C)
  (Sf : {l : Level} → is-set-truncation l B f)
  (Sg : {l : Level} → is-set-truncation l C g)
  where

  abstract
    uniqueness-set-truncation :
      is-contr (Σ (type-Set B ≃ type-Set C) (λ e → (map-equiv e ∘ f) ~ g))
    uniqueness-set-truncation =
      uniqueness-set-quotient
        ( mere-eq-Eq-Rel A)
        ( B)
        ( reflecting-map-mere-eq B f)
        ( is-set-quotient-is-set-truncation B f Sf)
        ( C)
        ( reflecting-map-mere-eq C g)
        ( is-set-quotient-is-set-truncation C g Sg)
  
  equiv-uniqueness-set-truncation : type-Set B ≃ type-Set C
  equiv-uniqueness-set-truncation =
    pr1 (center uniqueness-set-truncation)

  map-equiv-uniqueness-set-truncation : type-Set B → type-Set C
  map-equiv-uniqueness-set-truncation =
    map-equiv equiv-uniqueness-set-truncation

  triangle-uniqueness-set-truncation :
    (map-equiv-uniqueness-set-truncation ∘ f) ~ g
  triangle-uniqueness-set-truncation =
    pr2 (center uniqueness-set-truncation)
-}</a>
</pre>