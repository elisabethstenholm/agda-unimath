# Intersection of subtypes

<pre class="Agda"><a id="37" class="Symbol">{-#</a> <a id="41" class="Keyword">OPTIONS</a> <a id="49" class="Pragma">--without-K</a> <a id="61" class="Pragma">--exact-split</a> <a id="75" class="Symbol">#-}</a>

<a id="80" class="Keyword">module</a> <a id="87" href="foundation.intersection.html" class="Module">foundation.intersection</a> <a id="111" class="Keyword">where</a>

<a id="118" class="Keyword">open</a> <a id="123" class="Keyword">import</a> <a id="130" href="foundation.conjunction.html" class="Module">foundation.conjunction</a> <a id="153" class="Keyword">using</a> <a id="159" class="Symbol">(</a><a id="160" href="foundation.conjunction.html#693" class="Function">conj-Prop</a><a id="169" class="Symbol">;</a> <a id="171" href="foundation.conjunction.html#1031" class="Function">conj-decidable-Prop</a><a id="190" class="Symbol">)</a>
<a id="192" class="Keyword">open</a> <a id="197" class="Keyword">import</a> <a id="204" href="foundation.decidable-subtypes.html" class="Module">foundation.decidable-subtypes</a> <a id="234" class="Keyword">using</a> <a id="240" class="Symbol">(</a><a id="241" href="foundation.decidable-subtypes.html#1349" class="Function">decidable-subtype</a><a id="258" class="Symbol">)</a>
<a id="260" class="Keyword">open</a> <a id="265" class="Keyword">import</a> <a id="272" href="foundation.subtypes.html" class="Module">foundation.subtypes</a> <a id="292" class="Keyword">using</a> <a id="298" class="Symbol">(</a><a id="299" href="foundation-core.subtypes.html#2197" class="Function">subtype</a><a id="306" class="Symbol">)</a>
<a id="308" class="Keyword">open</a> <a id="313" class="Keyword">import</a> <a id="320" href="foundation.universe-levels.html" class="Module">foundation.universe-levels</a> <a id="347" class="Keyword">using</a> <a id="353" class="Symbol">(</a><a id="354" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="359" class="Symbol">;</a> <a id="361" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a><a id="363" class="Symbol">;</a> <a id="365" href="Agda.Primitive.html#810" class="Primitive Operator">_⊔_</a><a id="368" class="Symbol">)</a>
</pre>
## Idea

The intersection of two subtypes `A` and `B` is the subtype that contains the elements that are in `A` and in `B`.

## Definition

<pre class="Agda"><a id="523" class="Keyword">module</a> <a id="530" href="foundation.intersection.html#530" class="Module">_</a>
  <a id="534" class="Symbol">{</a><a id="535" href="foundation.intersection.html#535" class="Bound">l</a> <a id="537" href="foundation.intersection.html#537" class="Bound">l1</a> <a id="540" href="foundation.intersection.html#540" class="Bound">l2</a> <a id="543" class="Symbol">:</a> <a id="545" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="550" class="Symbol">}</a> <a id="552" class="Symbol">(</a><a id="553" href="foundation.intersection.html#553" class="Bound">X</a> <a id="555" class="Symbol">:</a> <a id="557" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="560" href="foundation.intersection.html#535" class="Bound">l</a><a id="561" class="Symbol">)</a>
  <a id="565" class="Keyword">where</a>

  <a id="574" href="foundation.intersection.html#574" class="Function">intersection-subtype</a> <a id="595" class="Symbol">:</a> <a id="597" href="foundation-core.subtypes.html#2197" class="Function">subtype</a> <a id="605" href="foundation.intersection.html#537" class="Bound">l1</a> <a id="608" href="foundation.intersection.html#553" class="Bound">X</a> <a id="610" class="Symbol">→</a> <a id="612" href="foundation-core.subtypes.html#2197" class="Function">subtype</a> <a id="620" href="foundation.intersection.html#540" class="Bound">l2</a> <a id="623" href="foundation.intersection.html#553" class="Bound">X</a> <a id="625" class="Symbol">→</a> <a id="627" href="foundation-core.subtypes.html#2197" class="Function">subtype</a> <a id="635" class="Symbol">(</a><a id="636" href="foundation.intersection.html#537" class="Bound">l1</a> <a id="639" href="Agda.Primitive.html#810" class="Primitive Operator">⊔</a> <a id="641" href="foundation.intersection.html#540" class="Bound">l2</a><a id="643" class="Symbol">)</a> <a id="645" href="foundation.intersection.html#553" class="Bound">X</a>
  <a id="649" href="foundation.intersection.html#574" class="Function">intersection-subtype</a> <a id="670" href="foundation.intersection.html#670" class="Bound">P</a> <a id="672" href="foundation.intersection.html#672" class="Bound">Q</a> <a id="674" href="foundation.intersection.html#674" class="Bound">x</a> <a id="676" class="Symbol">=</a> <a id="678" href="foundation.conjunction.html#693" class="Function">conj-Prop</a> <a id="688" class="Symbol">(</a><a id="689" href="foundation.intersection.html#670" class="Bound">P</a> <a id="691" href="foundation.intersection.html#674" class="Bound">x</a><a id="692" class="Symbol">)</a> <a id="694" class="Symbol">(</a><a id="695" href="foundation.intersection.html#672" class="Bound">Q</a> <a id="697" href="foundation.intersection.html#674" class="Bound">x</a><a id="698" class="Symbol">)</a>

  <a id="703" href="foundation.intersection.html#703" class="Function">intersection-decidable-subtype</a> <a id="734" class="Symbol">:</a> <a id="736" href="foundation.decidable-subtypes.html#1349" class="Function">decidable-subtype</a> <a id="754" href="foundation.intersection.html#537" class="Bound">l1</a> <a id="757" href="foundation.intersection.html#553" class="Bound">X</a> <a id="759" class="Symbol">→</a> <a id="761" href="foundation.decidable-subtypes.html#1349" class="Function">decidable-subtype</a> <a id="779" href="foundation.intersection.html#540" class="Bound">l2</a> <a id="782" href="foundation.intersection.html#553" class="Bound">X</a> <a id="784" class="Symbol">→</a>
    <a id="790" href="foundation.decidable-subtypes.html#1349" class="Function">decidable-subtype</a> <a id="808" class="Symbol">(</a><a id="809" href="foundation.intersection.html#537" class="Bound">l1</a> <a id="812" href="Agda.Primitive.html#810" class="Primitive Operator">⊔</a> <a id="814" href="foundation.intersection.html#540" class="Bound">l2</a><a id="816" class="Symbol">)</a> <a id="818" href="foundation.intersection.html#553" class="Bound">X</a>
  <a id="822" href="foundation.intersection.html#703" class="Function">intersection-decidable-subtype</a> <a id="853" href="foundation.intersection.html#853" class="Bound">P</a> <a id="855" href="foundation.intersection.html#855" class="Bound">Q</a> <a id="857" href="foundation.intersection.html#857" class="Bound">x</a> <a id="859" class="Symbol">=</a> <a id="861" href="foundation.conjunction.html#1031" class="Function">conj-decidable-Prop</a> <a id="881" class="Symbol">(</a><a id="882" href="foundation.intersection.html#853" class="Bound">P</a> <a id="884" href="foundation.intersection.html#857" class="Bound">x</a><a id="885" class="Symbol">)</a> <a id="887" class="Symbol">(</a><a id="888" href="foundation.intersection.html#855" class="Bound">Q</a> <a id="890" href="foundation.intersection.html#857" class="Bound">x</a><a id="891" class="Symbol">)</a>
</pre>