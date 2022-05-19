# Locally finite posets

<pre class="Agda"><a id="34" class="Symbol">{-#</a> <a id="38" class="Keyword">OPTIONS</a> <a id="46" class="Pragma">--without-K</a> <a id="58" class="Pragma">--exact-split</a> <a id="72" class="Symbol">#-}</a>

<a id="77" class="Keyword">module</a> <a id="84" href="order-theory.locally-finite-posets.html" class="Module">order-theory.locally-finite-posets</a> <a id="119" class="Keyword">where</a>

<a id="126" class="Keyword">open</a> <a id="131" class="Keyword">import</a> <a id="138" href="foundation.cartesian-product-types.html" class="Module">foundation.cartesian-product-types</a> <a id="173" class="Keyword">using</a> <a id="179" class="Symbol">(</a><a id="180" href="foundation-core.cartesian-product-types.html#577" class="Function Operator">_×_</a><a id="183" class="Symbol">)</a>
<a id="185" class="Keyword">open</a> <a id="190" class="Keyword">import</a> <a id="197" href="foundation.dependent-pair-types.html" class="Module">foundation.dependent-pair-types</a> <a id="229" class="Keyword">using</a> <a id="235" class="Symbol">(</a><a id="236" href="foundation-core.dependent-pair-types.html#502" class="Record">Σ</a><a id="237" class="Symbol">;</a> <a id="239" href="foundation-core.dependent-pair-types.html#575" class="InductiveConstructor">pair</a><a id="243" class="Symbol">;</a> <a id="245" href="foundation-core.dependent-pair-types.html#592" class="Field">pr1</a><a id="248" class="Symbol">;</a> <a id="250" href="foundation-core.dependent-pair-types.html#604" class="Field">pr2</a><a id="253" class="Symbol">)</a>
<a id="255" class="Keyword">open</a> <a id="260" class="Keyword">import</a> <a id="267" href="foundation.propositions.html" class="Module">foundation.propositions</a> <a id="291" class="Keyword">using</a>
  <a id="299" class="Symbol">(</a> <a id="301" href="foundation-core.propositions.html#1380" class="Function">UU-Prop</a><a id="308" class="Symbol">;</a> <a id="310" href="foundation-core.propositions.html#1482" class="Function">type-Prop</a><a id="319" class="Symbol">;</a> <a id="321" href="foundation-core.propositions.html#1549" class="Function">is-prop-type-Prop</a><a id="338" class="Symbol">;</a> <a id="340" href="foundation-core.propositions.html#1295" class="Function">is-prop</a><a id="347" class="Symbol">;</a> <a id="349" href="foundation-core.propositions.html#6683" class="Function">Π-Prop</a><a id="355" class="Symbol">)</a>
<a id="357" class="Keyword">open</a> <a id="362" class="Keyword">import</a> <a id="369" href="foundation.universe-levels.html" class="Module">foundation.universe-levels</a> <a id="396" class="Keyword">using</a> <a id="402" class="Symbol">(</a><a id="403" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="408" class="Symbol">;</a> <a id="410" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a><a id="412" class="Symbol">;</a> <a id="414" href="Agda.Primitive.html#810" class="Primitive Operator">_⊔_</a><a id="417" class="Symbol">)</a>

<a id="420" class="Keyword">open</a> <a id="425" class="Keyword">import</a> <a id="432" href="order-theory.finite-posets.html" class="Module">order-theory.finite-posets</a> <a id="459" class="Keyword">using</a> <a id="465" class="Symbol">(</a><a id="466" href="order-theory.finite-posets.html#836" class="Function">is-finite-poset-Prop</a><a id="486" class="Symbol">)</a>
<a id="488" class="Keyword">open</a> <a id="493" class="Keyword">import</a> <a id="500" href="order-theory.interval-subposets.html" class="Module">order-theory.interval-subposets</a> <a id="532" class="Keyword">using</a> <a id="538" class="Symbol">(</a><a id="539" href="order-theory.interval-subposets.html#873" class="Function">interval-sub-Poset</a><a id="557" class="Symbol">)</a>
<a id="559" class="Keyword">open</a> <a id="564" class="Keyword">import</a> <a id="571" href="order-theory.posets.html" class="Module">order-theory.posets</a> <a id="591" class="Keyword">using</a> <a id="597" class="Symbol">(</a><a id="598" href="order-theory.posets.html#731" class="Function">Poset</a><a id="603" class="Symbol">;</a> <a id="605" href="order-theory.posets.html#1145" class="Function">element-Poset</a><a id="618" class="Symbol">;</a> <a id="620" href="order-theory.posets.html#1280" class="Function">leq-Poset</a><a id="629" class="Symbol">)</a>
</pre>
## Idea

A poset `X` is said to be locally finite if for every `x, y ∈ X`, the poset `[x, y]` consisting of `z ∈ X` such that `x ≤ z ≤ y`, is finite.

## Definition

<pre class="Agda"><a id="810" class="Keyword">module</a> <a id="817" href="order-theory.locally-finite-posets.html#817" class="Module">_</a>
  <a id="821" class="Symbol">{</a><a id="822" href="order-theory.locally-finite-posets.html#822" class="Bound">l1</a> <a id="825" href="order-theory.locally-finite-posets.html#825" class="Bound">l2</a> <a id="828" class="Symbol">:</a> <a id="830" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="835" class="Symbol">}</a> <a id="837" class="Symbol">(</a><a id="838" href="order-theory.locally-finite-posets.html#838" class="Bound">X</a> <a id="840" class="Symbol">:</a> <a id="842" href="order-theory.posets.html#731" class="Function">Poset</a> <a id="848" href="order-theory.locally-finite-posets.html#822" class="Bound">l1</a> <a id="851" href="order-theory.locally-finite-posets.html#825" class="Bound">l2</a><a id="853" class="Symbol">)</a>
  <a id="857" class="Keyword">where</a>
  
  <a id="868" href="order-theory.locally-finite-posets.html#868" class="Function">is-locally-finite-poset-Prop</a> <a id="897" class="Symbol">:</a> <a id="899" href="foundation-core.propositions.html#1380" class="Function">UU-Prop</a> <a id="907" class="Symbol">(</a><a id="908" href="order-theory.locally-finite-posets.html#822" class="Bound">l1</a> <a id="911" href="Agda.Primitive.html#810" class="Primitive Operator">⊔</a> <a id="913" href="order-theory.locally-finite-posets.html#825" class="Bound">l2</a><a id="915" class="Symbol">)</a>
  <a id="919" href="order-theory.locally-finite-posets.html#868" class="Function">is-locally-finite-poset-Prop</a> <a id="948" class="Symbol">=</a>
    <a id="954" href="foundation-core.propositions.html#6683" class="Function">Π-Prop</a>
      <a id="967" class="Symbol">(</a> <a id="969" href="order-theory.posets.html#1145" class="Function">element-Poset</a> <a id="983" href="order-theory.locally-finite-posets.html#838" class="Bound">X</a><a id="984" class="Symbol">)</a>
      <a id="992" class="Symbol">(</a> <a id="994" class="Symbol">λ</a> <a id="996" href="order-theory.locally-finite-posets.html#996" class="Bound">x</a> <a id="998" class="Symbol">→</a>
        <a id="1008" href="foundation-core.propositions.html#6683" class="Function">Π-Prop</a>
          <a id="1025" class="Symbol">(</a> <a id="1027" href="order-theory.posets.html#1145" class="Function">element-Poset</a> <a id="1041" href="order-theory.locally-finite-posets.html#838" class="Bound">X</a><a id="1042" class="Symbol">)</a>
          <a id="1054" class="Symbol">(</a> <a id="1056" class="Symbol">λ</a> <a id="1058" href="order-theory.locally-finite-posets.html#1058" class="Bound">y</a> <a id="1060" class="Symbol">→</a>
            <a id="1074" href="order-theory.finite-posets.html#836" class="Function">is-finite-poset-Prop</a> <a id="1095" class="Symbol">(</a><a id="1096" href="order-theory.interval-subposets.html#873" class="Function">interval-sub-Poset</a> <a id="1115" href="order-theory.locally-finite-posets.html#838" class="Bound">X</a> <a id="1117" href="order-theory.locally-finite-posets.html#996" class="Bound">x</a> <a id="1119" href="order-theory.locally-finite-posets.html#1058" class="Bound">y</a><a id="1120" class="Symbol">)))</a>

  <a id="1127" href="order-theory.locally-finite-posets.html#1127" class="Function">is-locally-finite-Poset</a> <a id="1151" class="Symbol">:</a> <a id="1153" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="1156" class="Symbol">(</a><a id="1157" href="order-theory.locally-finite-posets.html#822" class="Bound">l1</a> <a id="1160" href="Agda.Primitive.html#810" class="Primitive Operator">⊔</a> <a id="1162" href="order-theory.locally-finite-posets.html#825" class="Bound">l2</a><a id="1164" class="Symbol">)</a>
  <a id="1168" href="order-theory.locally-finite-posets.html#1127" class="Function">is-locally-finite-Poset</a> <a id="1192" class="Symbol">=</a> <a id="1194" href="foundation-core.propositions.html#1482" class="Function">type-Prop</a> <a id="1204" href="order-theory.locally-finite-posets.html#868" class="Function">is-locally-finite-poset-Prop</a>

  <a id="1236" href="order-theory.locally-finite-posets.html#1236" class="Function">is-prop-is-locally-finite-Poset</a> <a id="1268" class="Symbol">:</a> <a id="1270" href="foundation-core.propositions.html#1295" class="Function">is-prop</a> <a id="1278" href="order-theory.locally-finite-posets.html#1127" class="Function">is-locally-finite-Poset</a>
  <a id="1304" href="order-theory.locally-finite-posets.html#1236" class="Function">is-prop-is-locally-finite-Poset</a> <a id="1336" class="Symbol">=</a>
    <a id="1342" href="foundation-core.propositions.html#1549" class="Function">is-prop-type-Prop</a> <a id="1360" href="order-theory.locally-finite-posets.html#868" class="Function">is-locally-finite-poset-Prop</a>
</pre>