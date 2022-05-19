# Arithmetic functions

<pre class="Agda"><a id="33" class="Symbol">{-#</a> <a id="37" class="Keyword">OPTIONS</a> <a id="45" class="Pragma">--without-K</a> <a id="57" class="Pragma">--exact-split</a> <a id="71" class="Symbol">#-}</a>

<a id="76" class="Keyword">module</a> <a id="83" href="elementary-number-theory.arithmetic-functions.html" class="Module">elementary-number-theory.arithmetic-functions</a> <a id="129" class="Keyword">where</a>

<a id="136" class="Keyword">open</a> <a id="141" class="Keyword">import</a> <a id="148" href="elementary-number-theory.nonzero-natural-numbers.html" class="Module">elementary-number-theory.nonzero-natural-numbers</a> <a id="197" class="Keyword">using</a> <a id="203" class="Symbol">(</a><a id="204" href="elementary-number-theory.nonzero-natural-numbers.html#710" class="Function">nonzero-ℕ</a><a id="213" class="Symbol">)</a>

<a id="216" class="Keyword">open</a> <a id="221" class="Keyword">import</a> <a id="228" href="foundation.universe-levels.html" class="Module">foundation.universe-levels</a> <a id="255" class="Keyword">using</a> <a id="261" class="Symbol">(</a><a id="262" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="267" class="Symbol">;</a> <a id="269" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a><a id="271" class="Symbol">)</a>

<a id="274" class="Keyword">open</a> <a id="279" class="Keyword">import</a> <a id="286" href="ring-theory.rings.html" class="Module">ring-theory.rings</a> <a id="304" class="Keyword">using</a> <a id="310" class="Symbol">(</a><a id="311" href="ring-theory.rings.html#2466" class="Function">Ring</a><a id="315" class="Symbol">;</a> <a id="317" href="ring-theory.rings.html#2723" class="Function">type-Ring</a><a id="326" class="Symbol">)</a>
</pre>
## Idea

An arithmetic function is a function from the nonzero natural numbers into a (commutative) ring. The arithmetic functions form a ring under pointwise addition and dirichlet convolution.

## Definition

<pre class="Agda"><a id="552" class="Keyword">module</a> <a id="559" href="elementary-number-theory.arithmetic-functions.html#559" class="Module">_</a>
  <a id="563" class="Symbol">{</a><a id="564" href="elementary-number-theory.arithmetic-functions.html#564" class="Bound">l</a> <a id="566" class="Symbol">:</a> <a id="568" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="573" class="Symbol">}</a> <a id="575" class="Symbol">(</a><a id="576" href="elementary-number-theory.arithmetic-functions.html#576" class="Bound">R</a> <a id="578" class="Symbol">:</a> <a id="580" href="ring-theory.rings.html#2466" class="Function">Ring</a> <a id="585" href="elementary-number-theory.arithmetic-functions.html#564" class="Bound">l</a><a id="586" class="Symbol">)</a>
  <a id="590" class="Keyword">where</a>

  <a id="599" href="elementary-number-theory.arithmetic-functions.html#599" class="Function">type-arithmetic-functions-Ring</a> <a id="630" class="Symbol">:</a> <a id="632" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="635" href="elementary-number-theory.arithmetic-functions.html#564" class="Bound">l</a>
  <a id="639" href="elementary-number-theory.arithmetic-functions.html#599" class="Function">type-arithmetic-functions-Ring</a> <a id="670" class="Symbol">=</a> <a id="672" href="elementary-number-theory.nonzero-natural-numbers.html#710" class="Function">nonzero-ℕ</a> <a id="682" class="Symbol">→</a> <a id="684" href="ring-theory.rings.html#2723" class="Function">type-Ring</a> <a id="694" href="elementary-number-theory.arithmetic-functions.html#576" class="Bound">R</a>
</pre>