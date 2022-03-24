# Univalent mathematics in Agda

Welcome to the website of the `agda-unimath` formalization project.

[![build](https://github.com/UniMath/agda-unimath/actions/workflows/ci.yaml/badge.svg?branch=master)](https://github.com/UniMath/agda-unimath/actions/workflows/ci.yaml)

<pre class="Agda"><a id="281" class="Symbol">{-#</a> <a id="285" class="Keyword">OPTIONS</a> <a id="293" class="Pragma">--without-K</a> <a id="305" class="Pragma">--exact-split</a> <a id="319" class="Symbol">#-}</a>
</pre>
## Category theory

<pre class="Agda"><a id="356" class="Keyword">open</a> <a id="361" class="Keyword">import</a> <a id="368" href="category-theory.html" class="Module">category-theory</a>
<a id="384" class="Keyword">open</a> <a id="389" class="Keyword">import</a> <a id="396" href="category-theory.adjunctions-large-precategories.html" class="Module">category-theory.adjunctions-large-precategories</a>
<a id="444" class="Keyword">open</a> <a id="449" class="Keyword">import</a> <a id="456" href="category-theory.anafunctors.html" class="Module">category-theory.anafunctors</a>
<a id="484" class="Keyword">open</a> <a id="489" class="Keyword">import</a> <a id="496" href="category-theory.categories.html" class="Module">category-theory.categories</a>
<a id="523" class="Keyword">open</a> <a id="528" class="Keyword">import</a> <a id="535" href="category-theory.equivalences-categories.html" class="Module">category-theory.equivalences-categories</a>
<a id="575" class="Keyword">open</a> <a id="580" class="Keyword">import</a> <a id="587" href="category-theory.equivalences-large-precategories.html" class="Module">category-theory.equivalences-large-precategories</a>
<a id="636" class="Keyword">open</a> <a id="641" class="Keyword">import</a> <a id="648" href="category-theory.equivalences-precategories.html" class="Module">category-theory.equivalences-precategories</a>
<a id="691" class="Keyword">open</a> <a id="696" class="Keyword">import</a> <a id="703" href="category-theory.functors-categories.html" class="Module">category-theory.functors-categories</a>
<a id="739" class="Keyword">open</a> <a id="744" class="Keyword">import</a> <a id="751" href="category-theory.functors-large-precategories.html" class="Module">category-theory.functors-large-precategories</a>
<a id="796" class="Keyword">open</a> <a id="801" class="Keyword">import</a> <a id="808" href="category-theory.functors-precategories.html" class="Module">category-theory.functors-precategories</a>
<a id="847" class="Keyword">open</a> <a id="852" class="Keyword">import</a> <a id="859" href="category-theory.homotopies-natural-transformations-large-precategories.html" class="Module">category-theory.homotopies-natural-transformations-large-precategories</a>
<a id="930" class="Keyword">open</a> <a id="935" class="Keyword">import</a> <a id="942" href="category-theory.initial-objects-precategories.html" class="Module">category-theory.initial-objects-precategories</a>
<a id="988" class="Keyword">open</a> <a id="993" class="Keyword">import</a> <a id="1000" href="category-theory.isomorphisms-categories.html" class="Module">category-theory.isomorphisms-categories</a>
<a id="1040" class="Keyword">open</a> <a id="1045" class="Keyword">import</a> <a id="1052" href="category-theory.isomorphisms-large-precategories.html" class="Module">category-theory.isomorphisms-large-precategories</a>
<a id="1101" class="Keyword">open</a> <a id="1106" class="Keyword">import</a> <a id="1113" href="category-theory.isomorphisms-precategories.html" class="Module">category-theory.isomorphisms-precategories</a>
<a id="1156" class="Keyword">open</a> <a id="1161" class="Keyword">import</a> <a id="1168" href="category-theory.large-categories.html" class="Module">category-theory.large-categories</a>
<a id="1201" class="Keyword">open</a> <a id="1206" class="Keyword">import</a> <a id="1213" href="category-theory.large-precategories.html" class="Module">category-theory.large-precategories</a>
<a id="1249" class="Keyword">open</a> <a id="1254" class="Keyword">import</a> <a id="1261" href="category-theory.monomorphisms-large-precategories.html" class="Module">category-theory.monomorphisms-large-precategories</a>
<a id="1311" class="Keyword">open</a> <a id="1316" class="Keyword">import</a> <a id="1323" href="category-theory.natural-isomorphisms-categories.html" class="Module">category-theory.natural-isomorphisms-categories</a>
<a id="1371" class="Keyword">open</a> <a id="1376" class="Keyword">import</a> <a id="1383" href="category-theory.natural-isomorphisms-large-precategories.html" class="Module">category-theory.natural-isomorphisms-large-precategories</a>
<a id="1440" class="Keyword">open</a> <a id="1445" class="Keyword">import</a> <a id="1452" href="category-theory.natural-isomorphisms-precategories.html" class="Module">category-theory.natural-isomorphisms-precategories</a>
<a id="1503" class="Keyword">open</a> <a id="1508" class="Keyword">import</a> <a id="1515" href="category-theory.natural-transformations-categories.html" class="Module">category-theory.natural-transformations-categories</a>
<a id="1566" class="Keyword">open</a> <a id="1571" class="Keyword">import</a> <a id="1578" href="category-theory.natural-transformations-large-precategories.html" class="Module">category-theory.natural-transformations-large-precategories</a>
<a id="1638" class="Keyword">open</a> <a id="1643" class="Keyword">import</a> <a id="1650" href="category-theory.natural-transformations-precategories.html" class="Module">category-theory.natural-transformations-precategories</a>
<a id="1704" class="Keyword">open</a> <a id="1709" class="Keyword">import</a> <a id="1716" href="category-theory.precategories.html" class="Module">category-theory.precategories</a>
<a id="1746" class="Keyword">open</a> <a id="1751" class="Keyword">import</a> <a id="1758" href="category-theory.slice-precategories.html" class="Module">category-theory.slice-precategories</a>
<a id="1794" class="Keyword">open</a> <a id="1799" class="Keyword">import</a> <a id="1806" href="category-theory.terminal-objects-precategories.html" class="Module">category-theory.terminal-objects-precategories</a>
</pre>
## Elementary number theory

<pre class="Agda"><a id="1895" class="Keyword">open</a> <a id="1900" class="Keyword">import</a> <a id="1907" href="elementary-number-theory.html" class="Module">elementary-number-theory</a>
<a id="1932" class="Keyword">open</a> <a id="1937" class="Keyword">import</a> <a id="1944" href="elementary-number-theory.absolute-value-integers.html" class="Module">elementary-number-theory.absolute-value-integers</a>
<a id="1993" class="Keyword">open</a> <a id="1998" class="Keyword">import</a> <a id="2005" href="elementary-number-theory.addition-integers.html" class="Module">elementary-number-theory.addition-integers</a>
<a id="2048" class="Keyword">open</a> <a id="2053" class="Keyword">import</a> <a id="2060" href="elementary-number-theory.addition-natural-numbers.html" class="Module">elementary-number-theory.addition-natural-numbers</a>
<a id="2110" class="Keyword">open</a> <a id="2115" class="Keyword">import</a> <a id="2122" href="elementary-number-theory.arithmetic-functions.html" class="Module">elementary-number-theory.arithmetic-functions</a>
<a id="2168" class="Keyword">open</a> <a id="2173" class="Keyword">import</a> <a id="2180" href="elementary-number-theory.binomial-coefficients.html" class="Module">elementary-number-theory.binomial-coefficients</a>
<a id="2227" class="Keyword">open</a> <a id="2232" class="Keyword">import</a> <a id="2239" href="elementary-number-theory.bounded-sums-arithmetic-functions.html" class="Module">elementary-number-theory.bounded-sums-arithmetic-functions</a>
<a id="2298" class="Keyword">open</a> <a id="2303" class="Keyword">import</a> <a id="2310" href="elementary-number-theory.catalan-numbers.html" class="Module">elementary-number-theory.catalan-numbers</a>
<a id="2351" class="Keyword">open</a> <a id="2356" class="Keyword">import</a> <a id="2363" href="elementary-number-theory.collatz-bijection.html" class="Module">elementary-number-theory.collatz-bijection</a>
<a id="2406" class="Keyword">open</a> <a id="2411" class="Keyword">import</a> <a id="2418" href="elementary-number-theory.collatz-conjecture.html" class="Module">elementary-number-theory.collatz-conjecture</a>
<a id="2462" class="Keyword">open</a> <a id="2467" class="Keyword">import</a> <a id="2474" href="elementary-number-theory.congruence-integers.html" class="Module">elementary-number-theory.congruence-integers</a>
<a id="2519" class="Keyword">open</a> <a id="2524" class="Keyword">import</a> <a id="2531" href="elementary-number-theory.congruence-natural-numbers.html" class="Module">elementary-number-theory.congruence-natural-numbers</a>
<a id="2583" class="Keyword">open</a> <a id="2588" class="Keyword">import</a> <a id="2595" href="elementary-number-theory.decidable-dependent-function-types.html" class="Module">elementary-number-theory.decidable-dependent-function-types</a>
<a id="2655" class="Keyword">open</a> <a id="2660" class="Keyword">import</a> <a id="2667" href="elementary-number-theory.decidable-types.html" class="Module">elementary-number-theory.decidable-types</a>
<a id="2708" class="Keyword">open</a> <a id="2713" class="Keyword">import</a> <a id="2720" href="elementary-number-theory.difference-integers.html" class="Module">elementary-number-theory.difference-integers</a>
<a id="2765" class="Keyword">open</a> <a id="2770" class="Keyword">import</a> <a id="2777" href="elementary-number-theory.dirichlet-convolution.html" class="Module">elementary-number-theory.dirichlet-convolution</a>
<a id="2824" class="Keyword">open</a> <a id="2829" class="Keyword">import</a> <a id="2836" href="elementary-number-theory.distance-integers.html" class="Module">elementary-number-theory.distance-integers</a>
<a id="2879" class="Keyword">open</a> <a id="2884" class="Keyword">import</a> <a id="2891" href="elementary-number-theory.distance-natural-numbers.html" class="Module">elementary-number-theory.distance-natural-numbers</a>
<a id="2941" class="Keyword">open</a> <a id="2946" class="Keyword">import</a> <a id="2953" href="elementary-number-theory.divisibility-integers.html" class="Module">elementary-number-theory.divisibility-integers</a>
<a id="3000" class="Keyword">open</a> <a id="3005" class="Keyword">import</a> <a id="3012" href="elementary-number-theory.divisibility-modular-arithmetic.html" class="Module">elementary-number-theory.divisibility-modular-arithmetic</a>
<a id="3069" class="Keyword">open</a> <a id="3074" class="Keyword">import</a> <a id="3081" href="elementary-number-theory.divisibility-natural-numbers.html" class="Module">elementary-number-theory.divisibility-natural-numbers</a>
<a id="3135" class="Keyword">open</a> <a id="3140" class="Keyword">import</a> <a id="3147" href="elementary-number-theory.divisibility-standard-finite-types.html" class="Module">elementary-number-theory.divisibility-standard-finite-types</a>
<a id="3207" class="Keyword">open</a> <a id="3212" class="Keyword">import</a> <a id="3219" href="elementary-number-theory.equality-integers.html" class="Module">elementary-number-theory.equality-integers</a>
<a id="3262" class="Keyword">open</a> <a id="3267" class="Keyword">import</a> <a id="3274" href="elementary-number-theory.equality-natural-numbers.html" class="Module">elementary-number-theory.equality-natural-numbers</a>
<a id="3324" class="Keyword">open</a> <a id="3329" class="Keyword">import</a> <a id="3336" href="elementary-number-theory.euclidean-division-natural-numbers.html" class="Module">elementary-number-theory.euclidean-division-natural-numbers</a>
<a id="3396" class="Keyword">open</a> <a id="3401" class="Keyword">import</a> <a id="3408" href="elementary-number-theory.eulers-totient-function.html" class="Module">elementary-number-theory.eulers-totient-function</a>
<a id="3457" class="Keyword">open</a> <a id="3462" class="Keyword">import</a> <a id="3469" href="elementary-number-theory.exponentiation-natural-numbers.html" class="Module">elementary-number-theory.exponentiation-natural-numbers</a>
<a id="3525" class="Keyword">open</a> <a id="3530" class="Keyword">import</a> <a id="3537" href="elementary-number-theory.factorials.html" class="Module">elementary-number-theory.factorials</a>
<a id="3573" class="Keyword">open</a> <a id="3578" class="Keyword">import</a> <a id="3585" href="elementary-number-theory.falling-factorials.html" class="Module">elementary-number-theory.falling-factorials</a>
<a id="3629" class="Keyword">open</a> <a id="3634" class="Keyword">import</a> <a id="3641" href="elementary-number-theory.fibonacci-sequence.html" class="Module">elementary-number-theory.fibonacci-sequence</a>
<a id="3685" class="Keyword">open</a> <a id="3690" class="Keyword">import</a> <a id="3697" href="elementary-number-theory.finitary-natural-numbers.html" class="Module">elementary-number-theory.finitary-natural-numbers</a>
<a id="3747" class="Keyword">open</a> <a id="3752" class="Keyword">import</a> <a id="3759" href="elementary-number-theory.finitely-cyclic-maps.html" class="Module">elementary-number-theory.finitely-cyclic-maps</a>
<a id="3805" class="Keyword">open</a> <a id="3810" class="Keyword">import</a> <a id="3817" href="elementary-number-theory.fractions.html" class="Module">elementary-number-theory.fractions</a>
<a id="3852" class="Keyword">open</a> <a id="3857" class="Keyword">import</a> <a id="3864" href="elementary-number-theory.goldbach-conjecture.html" class="Module">elementary-number-theory.goldbach-conjecture</a>
<a id="3909" class="Keyword">open</a> <a id="3914" class="Keyword">import</a> <a id="3921" href="elementary-number-theory.greatest-common-divisor-integers.html" class="Module">elementary-number-theory.greatest-common-divisor-integers</a>
<a id="3979" class="Keyword">open</a> <a id="3984" class="Keyword">import</a> <a id="3991" href="elementary-number-theory.greatest-common-divisor-natural-numbers.html" class="Module">elementary-number-theory.greatest-common-divisor-natural-numbers</a>
<a id="4056" class="Keyword">open</a> <a id="4061" class="Keyword">import</a> <a id="4068" href="elementary-number-theory.group-of-integers.html" class="Module">elementary-number-theory.group-of-integers</a>
<a id="4111" class="Keyword">open</a> <a id="4116" class="Keyword">import</a> <a id="4123" href="elementary-number-theory.groups-of-modular-arithmetic.html" class="Module">elementary-number-theory.groups-of-modular-arithmetic</a>
<a id="4177" class="Keyword">open</a> <a id="4182" class="Keyword">import</a> <a id="4189" href="elementary-number-theory.inequality-integers.html" class="Module">elementary-number-theory.inequality-integers</a>
<a id="4234" class="Keyword">open</a> <a id="4239" class="Keyword">import</a> <a id="4246" href="elementary-number-theory.inequality-natural-numbers.html" class="Module">elementary-number-theory.inequality-natural-numbers</a>
<a id="4298" class="Keyword">open</a> <a id="4303" class="Keyword">import</a> <a id="4310" href="elementary-number-theory.inequality-standard-finite-types.html" class="Module">elementary-number-theory.inequality-standard-finite-types</a>
<a id="4368" class="Keyword">open</a> <a id="4373" class="Keyword">import</a> <a id="4380" href="elementary-number-theory.infinitude-of-primes.html" class="Module">elementary-number-theory.infinitude-of-primes</a>
<a id="4426" class="Keyword">open</a> <a id="4431" class="Keyword">import</a> <a id="4438" href="elementary-number-theory.integers.html" class="Module">elementary-number-theory.integers</a>
<a id="4472" class="Keyword">open</a> <a id="4477" class="Keyword">import</a> <a id="4484" href="elementary-number-theory.iterating-functions.html" class="Module">elementary-number-theory.iterating-functions</a>
<a id="4529" class="Keyword">open</a> <a id="4534" class="Keyword">import</a> <a id="4541" href="elementary-number-theory.lower-bounds-natural-numbers.html" class="Module">elementary-number-theory.lower-bounds-natural-numbers</a>
<a id="4595" class="Keyword">open</a> <a id="4600" class="Keyword">import</a> <a id="4607" href="elementary-number-theory.maximum-natural-numbers.html" class="Module">elementary-number-theory.maximum-natural-numbers</a>
<a id="4656" class="Keyword">open</a> <a id="4661" class="Keyword">import</a> <a id="4668" href="elementary-number-theory.mersenne-primes.html" class="Module">elementary-number-theory.mersenne-primes</a>
<a id="4709" class="Keyword">open</a> <a id="4714" class="Keyword">import</a> <a id="4721" href="elementary-number-theory.minimum-natural-numbers.html" class="Module">elementary-number-theory.minimum-natural-numbers</a>
<a id="4770" class="Keyword">open</a> <a id="4775" class="Keyword">import</a> <a id="4782" href="elementary-number-theory.modular-arithmetic-standard-finite-types.html" class="Module">elementary-number-theory.modular-arithmetic-standard-finite-types</a>
<a id="4848" class="Keyword">open</a> <a id="4853" class="Keyword">import</a> <a id="4860" href="elementary-number-theory.modular-arithmetic.html" class="Module">elementary-number-theory.modular-arithmetic</a>
<a id="4904" class="Keyword">open</a> <a id="4909" class="Keyword">import</a> <a id="4916" href="elementary-number-theory.multiplication-integers.html" class="Module">elementary-number-theory.multiplication-integers</a>
<a id="4965" class="Keyword">open</a> <a id="4970" class="Keyword">import</a> <a id="4977" href="elementary-number-theory.multiplication-natural-numbers.html" class="Module">elementary-number-theory.multiplication-natural-numbers</a>
<a id="5033" class="Keyword">open</a> <a id="5038" class="Keyword">import</a> <a id="5045" href="elementary-number-theory.natural-numbers.html" class="Module">elementary-number-theory.natural-numbers</a>
<a id="5086" class="Keyword">open</a> <a id="5091" class="Keyword">import</a> <a id="5098" href="elementary-number-theory.nonzero-natural-numbers.html" class="Module">elementary-number-theory.nonzero-natural-numbers</a>
<a id="5147" class="Keyword">open</a> <a id="5152" class="Keyword">import</a> <a id="5159" href="elementary-number-theory.ordinal-induction-natural-numbers.html" class="Module">elementary-number-theory.ordinal-induction-natural-numbers</a>
<a id="5218" class="Keyword">open</a> <a id="5223" class="Keyword">import</a> <a id="5230" href="elementary-number-theory.prime-numbers.html" class="Module">elementary-number-theory.prime-numbers</a>
<a id="5269" class="Keyword">open</a> <a id="5274" class="Keyword">import</a> <a id="5281" href="elementary-number-theory.products-of-natural-numbers.html" class="Module">elementary-number-theory.products-of-natural-numbers</a>
<a id="5334" class="Keyword">open</a> <a id="5339" class="Keyword">import</a> <a id="5346" href="elementary-number-theory.proper-divisors-natural-numbers.html" class="Module">elementary-number-theory.proper-divisors-natural-numbers</a>
<a id="5403" class="Keyword">open</a> <a id="5408" class="Keyword">import</a> <a id="5415" href="elementary-number-theory.rational-numbers.html" class="Module">elementary-number-theory.rational-numbers</a>
<a id="5457" class="Keyword">open</a> <a id="5462" class="Keyword">import</a> <a id="5469" href="elementary-number-theory.relatively-prime-integers.html" class="Module">elementary-number-theory.relatively-prime-integers</a>
<a id="5520" class="Keyword">open</a> <a id="5525" class="Keyword">import</a> <a id="5532" href="elementary-number-theory.relatively-prime-natural-numbers.html" class="Module">elementary-number-theory.relatively-prime-natural-numbers</a>
<a id="5590" class="Keyword">open</a> <a id="5595" class="Keyword">import</a> <a id="5602" href="elementary-number-theory.repeating-element-standard-finite-type.html" class="Module">elementary-number-theory.repeating-element-standard-finite-type</a>
<a id="5666" class="Keyword">open</a> <a id="5671" class="Keyword">import</a> <a id="5678" href="elementary-number-theory.retracts-of-natural-numbers.html" class="Module">elementary-number-theory.retracts-of-natural-numbers</a>
<a id="5731" class="Keyword">open</a> <a id="5736" class="Keyword">import</a> <a id="5743" href="elementary-number-theory.square-free-natural-numbers.html" class="Module">elementary-number-theory.square-free-natural-numbers</a>
<a id="5796" class="Keyword">open</a> <a id="5801" class="Keyword">import</a> <a id="5808" href="elementary-number-theory.stirling-numbers-of-the-second-kind.html" class="Module">elementary-number-theory.stirling-numbers-of-the-second-kind</a>
<a id="5869" class="Keyword">open</a> <a id="5874" class="Keyword">import</a> <a id="5881" href="elementary-number-theory.strong-induction-natural-numbers.html" class="Module">elementary-number-theory.strong-induction-natural-numbers</a>
<a id="5939" class="Keyword">open</a> <a id="5944" class="Keyword">import</a> <a id="5951" href="elementary-number-theory.sums-of-natural-numbers.html" class="Module">elementary-number-theory.sums-of-natural-numbers</a>
<a id="6000" class="Keyword">open</a> <a id="6005" class="Keyword">import</a> <a id="6012" href="elementary-number-theory.triangular-numbers.html" class="Module">elementary-number-theory.triangular-numbers</a>
<a id="6056" class="Keyword">open</a> <a id="6061" class="Keyword">import</a> <a id="6068" href="elementary-number-theory.twin-prime-conjecture.html" class="Module">elementary-number-theory.twin-prime-conjecture</a>
<a id="6115" class="Keyword">open</a> <a id="6120" class="Keyword">import</a> <a id="6127" href="elementary-number-theory.unit-elements-standard-finite-types.html" class="Module">elementary-number-theory.unit-elements-standard-finite-types</a>
<a id="6188" class="Keyword">open</a> <a id="6193" class="Keyword">import</a> <a id="6200" href="elementary-number-theory.unit-similarity-standard-finite-types.html" class="Module">elementary-number-theory.unit-similarity-standard-finite-types</a>
<a id="6263" class="Keyword">open</a> <a id="6268" class="Keyword">import</a> <a id="6275" href="elementary-number-theory.universal-property-natural-numbers.html" class="Module">elementary-number-theory.universal-property-natural-numbers</a>
<a id="6335" class="Keyword">open</a> <a id="6340" class="Keyword">import</a> <a id="6347" href="elementary-number-theory.upper-bounds-natural-numbers.html" class="Module">elementary-number-theory.upper-bounds-natural-numbers</a>
<a id="6401" class="Keyword">open</a> <a id="6406" class="Keyword">import</a> <a id="6413" href="elementary-number-theory.well-ordering-principle-natural-numbers.html" class="Module">elementary-number-theory.well-ordering-principle-natural-numbers</a>
<a id="6478" class="Keyword">open</a> <a id="6483" class="Keyword">import</a> <a id="6490" href="elementary-number-theory.well-ordering-principle-standard-finite-types.html" class="Module">elementary-number-theory.well-ordering-principle-standard-finite-types</a>
</pre>
## Finite group theory

<pre class="Agda"><a id="6598" class="Keyword">open</a> <a id="6603" class="Keyword">import</a> <a id="6610" href="finite-group-theory.html" class="Module">finite-group-theory</a>
<a id="6630" class="Keyword">open</a> <a id="6635" class="Keyword">import</a> <a id="6642" href="finite-group-theory.abstract-quaternion-group.html" class="Module">finite-group-theory.abstract-quaternion-group</a>
<a id="6688" class="Keyword">open</a> <a id="6693" class="Keyword">import</a> <a id="6700" href="finite-group-theory.concrete-quaternion-group.html" class="Module">finite-group-theory.concrete-quaternion-group</a>
<a id="6746" class="Keyword">open</a> <a id="6751" class="Keyword">import</a> <a id="6758" href="finite-group-theory.finite-groups.html" class="Module">finite-group-theory.finite-groups</a>
<a id="6792" class="Keyword">open</a> <a id="6797" class="Keyword">import</a> <a id="6804" href="finite-group-theory.orbits-permutations.html" class="Module">finite-group-theory.orbits-permutations</a>
<a id="6844" class="Keyword">open</a> <a id="6849" class="Keyword">import</a> <a id="6856" href="finite-group-theory.permutations.html" class="Module">finite-group-theory.permutations</a>
<a id="6889" class="Keyword">open</a> <a id="6894" class="Keyword">import</a> <a id="6901" href="finite-group-theory.sign-homomorphism.html" class="Module">finite-group-theory.sign-homomorphism</a>
<a id="6939" class="Keyword">open</a> <a id="6944" class="Keyword">import</a> <a id="6951" href="finite-group-theory.transpositions.html" class="Module">finite-group-theory.transpositions</a>
</pre>
## Foundation

<pre class="Agda"><a id="7014" class="Keyword">open</a> <a id="7019" class="Keyword">import</a> <a id="7026" href="foundation.html" class="Module">foundation</a>
<a id="7037" class="Keyword">open</a> <a id="7042" class="Keyword">import</a> <a id="7049" href="foundation.0-maps.html" class="Module">foundation.0-maps</a>
<a id="7067" class="Keyword">open</a> <a id="7072" class="Keyword">import</a> <a id="7079" href="foundation.1-types.html" class="Module">foundation.1-types</a>
<a id="7098" class="Keyword">open</a> <a id="7103" class="Keyword">import</a> <a id="7110" href="foundation.2-types.html" class="Module">foundation.2-types</a>
<a id="7129" class="Keyword">open</a> <a id="7134" class="Keyword">import</a> <a id="7141" href="foundation.algebras-polynomial-endofunctors.html" class="Module">foundation.algebras-polynomial-endofunctors</a>
<a id="7185" class="Keyword">open</a> <a id="7190" class="Keyword">import</a> <a id="7197" href="foundation.automorphisms.html" class="Module">foundation.automorphisms</a>
<a id="7222" class="Keyword">open</a> <a id="7227" class="Keyword">import</a> <a id="7234" href="foundation.axiom-of-choice.html" class="Module">foundation.axiom-of-choice</a>
<a id="7261" class="Keyword">open</a> <a id="7266" class="Keyword">import</a> <a id="7273" href="foundation.binary-embeddings.html" class="Module">foundation.binary-embeddings</a>
<a id="7302" class="Keyword">open</a> <a id="7307" class="Keyword">import</a> <a id="7314" href="foundation.binary-equivalences.html" class="Module">foundation.binary-equivalences</a>
<a id="7345" class="Keyword">open</a> <a id="7350" class="Keyword">import</a> <a id="7357" href="foundation.binary-relations.html" class="Module">foundation.binary-relations</a>
<a id="7385" class="Keyword">open</a> <a id="7390" class="Keyword">import</a> <a id="7397" href="foundation.boolean-reflection.html" class="Module">foundation.boolean-reflection</a>
<a id="7427" class="Keyword">open</a> <a id="7432" class="Keyword">import</a> <a id="7439" href="foundation.booleans.html" class="Module">foundation.booleans</a>
<a id="7459" class="Keyword">open</a> <a id="7464" class="Keyword">import</a> <a id="7471" href="foundation.cantors-diagonal-argument.html" class="Module">foundation.cantors-diagonal-argument</a>
<a id="7508" class="Keyword">open</a> <a id="7513" class="Keyword">import</a> <a id="7520" href="foundation.cartesian-product-types.html" class="Module">foundation.cartesian-product-types</a>
<a id="7555" class="Keyword">open</a> <a id="7560" class="Keyword">import</a> <a id="7567" href="foundation.choice-of-representatives-equivalence-relation.html" class="Module">foundation.choice-of-representatives-equivalence-relation</a>
<a id="7625" class="Keyword">open</a> <a id="7630" class="Keyword">import</a> <a id="7637" href="foundation.coherently-invertible-maps.html" class="Module">foundation.coherently-invertible-maps</a>
<a id="7675" class="Keyword">open</a> <a id="7680" class="Keyword">import</a> <a id="7687" href="foundation.commuting-squares.html" class="Module">foundation.commuting-squares</a>
<a id="7716" class="Keyword">open</a> <a id="7721" class="Keyword">import</a> <a id="7728" href="foundation.complements.html" class="Module">foundation.complements</a>
<a id="7751" class="Keyword">open</a> <a id="7756" class="Keyword">import</a> <a id="7763" href="foundation.conjunction.html" class="Module">foundation.conjunction</a>
<a id="7786" class="Keyword">open</a> <a id="7791" class="Keyword">import</a> <a id="7798" href="foundation.connected-components-universes.html" class="Module">foundation.connected-components-universes</a>
<a id="7840" class="Keyword">open</a> <a id="7845" class="Keyword">import</a> <a id="7852" href="foundation.connected-components.html" class="Module">foundation.connected-components</a>
<a id="7884" class="Keyword">open</a> <a id="7889" class="Keyword">import</a> <a id="7896" href="foundation.connected-types.html" class="Module">foundation.connected-types</a>
<a id="7923" class="Keyword">open</a> <a id="7928" class="Keyword">import</a> <a id="7935" href="foundation.constant-maps.html" class="Module">foundation.constant-maps</a>
<a id="7960" class="Keyword">open</a> <a id="7965" class="Keyword">import</a> <a id="7972" href="foundation.contractible-maps.html" class="Module">foundation.contractible-maps</a>
<a id="8001" class="Keyword">open</a> <a id="8006" class="Keyword">import</a> <a id="8013" href="foundation.contractible-types.html" class="Module">foundation.contractible-types</a>
<a id="8043" class="Keyword">open</a> <a id="8048" class="Keyword">import</a> <a id="8055" href="foundation.coproduct-types.html" class="Module">foundation.coproduct-types</a>
<a id="8082" class="Keyword">open</a> <a id="8087" class="Keyword">import</a> <a id="8094" href="foundation.coslice.html" class="Module">foundation.coslice</a>
<a id="8113" class="Keyword">open</a> <a id="8118" class="Keyword">import</a> <a id="8125" href="foundation.decidable-dependent-function-types.html" class="Module">foundation.decidable-dependent-function-types</a>
<a id="8171" class="Keyword">open</a> <a id="8176" class="Keyword">import</a> <a id="8183" href="foundation.decidable-dependent-pair-types.html" class="Module">foundation.decidable-dependent-pair-types</a>
<a id="8225" class="Keyword">open</a> <a id="8230" class="Keyword">import</a> <a id="8237" href="foundation.decidable-embeddings.html" class="Module">foundation.decidable-embeddings</a>
<a id="8269" class="Keyword">open</a> <a id="8274" class="Keyword">import</a> <a id="8281" href="foundation.decidable-equality.html" class="Module">foundation.decidable-equality</a>
<a id="8311" class="Keyword">open</a> <a id="8316" class="Keyword">import</a> <a id="8323" href="foundation.decidable-maps.html" class="Module">foundation.decidable-maps</a>
<a id="8349" class="Keyword">open</a> <a id="8354" class="Keyword">import</a> <a id="8361" href="foundation.decidable-propositions.html" class="Module">foundation.decidable-propositions</a>
<a id="8395" class="Keyword">open</a> <a id="8400" class="Keyword">import</a> <a id="8407" href="foundation.decidable-subtypes.html" class="Module">foundation.decidable-subtypes</a>
<a id="8437" class="Keyword">open</a> <a id="8442" class="Keyword">import</a> <a id="8449" href="foundation.decidable-types.html" class="Module">foundation.decidable-types</a>
<a id="8476" class="Keyword">open</a> <a id="8481" class="Keyword">import</a> <a id="8488" href="foundation.dependent-pair-types.html" class="Module">foundation.dependent-pair-types</a>
<a id="8520" class="Keyword">open</a> <a id="8525" class="Keyword">import</a> <a id="8532" href="foundation.diagonal-maps-of-types.html" class="Module">foundation.diagonal-maps-of-types</a>
<a id="8566" class="Keyword">open</a> <a id="8571" class="Keyword">import</a> <a id="8578" href="foundation.disjunction.html" class="Module">foundation.disjunction</a>
<a id="8601" class="Keyword">open</a> <a id="8606" class="Keyword">import</a> <a id="8613" href="foundation.distributivity-of-dependent-functions-over-coproduct-types.html" class="Module">foundation.distributivity-of-dependent-functions-over-coproduct-types</a>
<a id="8683" class="Keyword">open</a> <a id="8688" class="Keyword">import</a> <a id="8695" href="foundation.distributivity-of-dependent-functions-over-dependent-pairs.html" class="Module">foundation.distributivity-of-dependent-functions-over-dependent-pairs</a>
<a id="8765" class="Keyword">open</a> <a id="8770" class="Keyword">import</a> <a id="8777" href="foundation.double-negation.html" class="Module">foundation.double-negation</a>
<a id="8804" class="Keyword">open</a> <a id="8809" class="Keyword">import</a> <a id="8816" href="foundation.effective-maps-equivalence-relations.html" class="Module">foundation.effective-maps-equivalence-relations</a>
<a id="8864" class="Keyword">open</a> <a id="8869" class="Keyword">import</a> <a id="8876" href="foundation.elementhood-relation-w-types.html" class="Module">foundation.elementhood-relation-w-types</a>
<a id="8916" class="Keyword">open</a> <a id="8921" class="Keyword">import</a> <a id="8928" href="foundation.embeddings.html" class="Module">foundation.embeddings</a>
<a id="8950" class="Keyword">open</a> <a id="8955" class="Keyword">import</a> <a id="8962" href="foundation.empty-types.html" class="Module">foundation.empty-types</a>
<a id="8985" class="Keyword">open</a> <a id="8990" class="Keyword">import</a> <a id="8997" href="foundation.epimorphisms-with-respect-to-sets.html" class="Module">foundation.epimorphisms-with-respect-to-sets</a>
<a id="9042" class="Keyword">open</a> <a id="9047" class="Keyword">import</a> <a id="9054" href="foundation.equality-cartesian-product-types.html" class="Module">foundation.equality-cartesian-product-types</a>
<a id="9098" class="Keyword">open</a> <a id="9103" class="Keyword">import</a> <a id="9110" href="foundation.equality-coproduct-types.html" class="Module">foundation.equality-coproduct-types</a>
<a id="9146" class="Keyword">open</a> <a id="9151" class="Keyword">import</a> <a id="9158" href="foundation.equality-dependent-function-types.html" class="Module">foundation.equality-dependent-function-types</a>
<a id="9203" class="Keyword">open</a> <a id="9208" class="Keyword">import</a> <a id="9215" href="foundation.equality-dependent-pair-types.html" class="Module">foundation.equality-dependent-pair-types</a>
<a id="9256" class="Keyword">open</a> <a id="9261" class="Keyword">import</a> <a id="9268" href="foundation.equality-fibers-of-maps.html" class="Module">foundation.equality-fibers-of-maps</a>
<a id="9303" class="Keyword">open</a> <a id="9308" class="Keyword">import</a> <a id="9315" href="foundation.equivalence-classes.html" class="Module">foundation.equivalence-classes</a>
<a id="9346" class="Keyword">open</a> <a id="9351" class="Keyword">import</a> <a id="9358" href="foundation.equivalence-induction.html" class="Module">foundation.equivalence-induction</a>
<a id="9391" class="Keyword">open</a> <a id="9396" class="Keyword">import</a> <a id="9403" href="foundation.equivalence-relations.html" class="Module">foundation.equivalence-relations</a>
<a id="9436" class="Keyword">open</a> <a id="9441" class="Keyword">import</a> <a id="9448" href="foundation.equivalences-maybe.html" class="Module">foundation.equivalences-maybe</a>
<a id="9478" class="Keyword">open</a> <a id="9483" class="Keyword">import</a> <a id="9490" href="foundation.equivalences.html" class="Module">foundation.equivalences</a>
<a id="9514" class="Keyword">open</a> <a id="9519" class="Keyword">import</a> <a id="9526" href="foundation.existential-quantification.html" class="Module">foundation.existential-quantification</a>
<a id="9564" class="Keyword">open</a> <a id="9569" class="Keyword">import</a> <a id="9576" href="foundation.extensional-w-types.html" class="Module">foundation.extensional-w-types</a>
<a id="9607" class="Keyword">open</a> <a id="9612" class="Keyword">import</a> <a id="9619" href="foundation.faithful-maps.html" class="Module">foundation.faithful-maps</a>
<a id="9644" class="Keyword">open</a> <a id="9649" class="Keyword">import</a> <a id="9656" href="foundation.fiber-inclusions.html" class="Module">foundation.fiber-inclusions</a>
<a id="9684" class="Keyword">open</a> <a id="9689" class="Keyword">import</a> <a id="9696" href="foundation.fibered-maps.html" class="Module">foundation.fibered-maps</a>
<a id="9720" class="Keyword">open</a> <a id="9725" class="Keyword">import</a> <a id="9732" href="foundation.fibers-of-maps.html" class="Module">foundation.fibers-of-maps</a>
<a id="9758" class="Keyword">open</a> <a id="9763" class="Keyword">import</a> <a id="9770" href="foundation.function-extensionality.html" class="Module">foundation.function-extensionality</a>
<a id="9805" class="Keyword">open</a> <a id="9810" class="Keyword">import</a> <a id="9817" href="foundation.functions.html" class="Module">foundation.functions</a>
<a id="9838" class="Keyword">open</a> <a id="9843" class="Keyword">import</a> <a id="9850" href="foundation.functoriality-cartesian-product-types.html" class="Module">foundation.functoriality-cartesian-product-types</a>
<a id="9899" class="Keyword">open</a> <a id="9904" class="Keyword">import</a> <a id="9911" href="foundation.functoriality-coproduct-types.html" class="Module">foundation.functoriality-coproduct-types</a>
<a id="9952" class="Keyword">open</a> <a id="9957" class="Keyword">import</a> <a id="9964" href="foundation.functoriality-dependent-function-types.html" class="Module">foundation.functoriality-dependent-function-types</a>
<a id="10014" class="Keyword">open</a> <a id="10019" class="Keyword">import</a> <a id="10026" href="foundation.functoriality-dependent-pair-types.html" class="Module">foundation.functoriality-dependent-pair-types</a>
<a id="10072" class="Keyword">open</a> <a id="10077" class="Keyword">import</a> <a id="10084" href="foundation.functoriality-function-types.html" class="Module">foundation.functoriality-function-types</a>
<a id="10124" class="Keyword">open</a> <a id="10129" class="Keyword">import</a> <a id="10136" href="foundation.functoriality-propositional-truncation.html" class="Module">foundation.functoriality-propositional-truncation</a>
<a id="10186" class="Keyword">open</a> <a id="10191" class="Keyword">import</a> <a id="10198" href="foundation.functoriality-set-quotients.html" class="Module">foundation.functoriality-set-quotients</a>
<a id="10237" class="Keyword">open</a> <a id="10242" class="Keyword">import</a> <a id="10249" href="foundation.functoriality-set-truncation.html" class="Module">foundation.functoriality-set-truncation</a>
<a id="10289" class="Keyword">open</a> <a id="10294" class="Keyword">import</a> <a id="10301" href="foundation.functoriality-w-types.html" class="Module">foundation.functoriality-w-types</a>
<a id="10334" class="Keyword">open</a> <a id="10339" class="Keyword">import</a> <a id="10346" href="foundation.fundamental-theorem-of-identity-types.html" class="Module">foundation.fundamental-theorem-of-identity-types</a>
<a id="10395" class="Keyword">open</a> <a id="10400" class="Keyword">import</a> <a id="10407" href="foundation.global-choice.html" class="Module">foundation.global-choice</a>
<a id="10432" class="Keyword">open</a> <a id="10437" class="Keyword">import</a> <a id="10444" href="foundation.homotopies.html" class="Module">foundation.homotopies</a>
<a id="10466" class="Keyword">open</a> <a id="10471" class="Keyword">import</a> <a id="10478" href="foundation.identity-systems.html" class="Module">foundation.identity-systems</a>
<a id="10506" class="Keyword">open</a> <a id="10511" class="Keyword">import</a> <a id="10518" href="foundation.identity-types.html" class="Module">foundation.identity-types</a>
<a id="10544" class="Keyword">open</a> <a id="10549" class="Keyword">import</a> <a id="10556" href="foundation.images.html" class="Module">foundation.images</a>
<a id="10574" class="Keyword">open</a> <a id="10579" class="Keyword">import</a> <a id="10586" href="foundation.impredicative-encodings.html" class="Module">foundation.impredicative-encodings</a>
<a id="10621" class="Keyword">open</a> <a id="10626" class="Keyword">import</a> <a id="10633" href="foundation.indexed-w-types.html" class="Module">foundation.indexed-w-types</a>
<a id="10660" class="Keyword">open</a> <a id="10665" class="Keyword">import</a> <a id="10672" href="foundation.induction-principle-propositional-truncation.html" class="Module">foundation.induction-principle-propositional-truncation</a>
<a id="10728" class="Keyword">open</a> <a id="10733" class="Keyword">import</a> <a id="10740" href="foundation.induction-w-types.html" class="Module">foundation.induction-w-types</a>
<a id="10769" class="Keyword">open</a> <a id="10774" class="Keyword">import</a> <a id="10781" href="foundation.inequality-w-types.html" class="Module">foundation.inequality-w-types</a>
<a id="10811" class="Keyword">open</a> <a id="10816" class="Keyword">import</a> <a id="10823" href="foundation.injective-maps.html" class="Module">foundation.injective-maps</a>
<a id="10849" class="Keyword">open</a> <a id="10854" class="Keyword">import</a> <a id="10861" href="foundation.interchange-law.html" class="Module">foundation.interchange-law</a>
<a id="10888" class="Keyword">open</a> <a id="10893" class="Keyword">import</a> <a id="10900" href="foundation.involutions.html" class="Module">foundation.involutions</a>
<a id="10923" class="Keyword">open</a> <a id="10928" class="Keyword">import</a> <a id="10935" href="foundation.isolated-points.html" class="Module">foundation.isolated-points</a>
<a id="10962" class="Keyword">open</a> <a id="10967" class="Keyword">import</a> <a id="10974" href="foundation.isomorphisms-of-sets.html" class="Module">foundation.isomorphisms-of-sets</a>
<a id="11006" class="Keyword">open</a> <a id="11011" class="Keyword">import</a> <a id="11018" href="foundation.law-of-excluded-middle.html" class="Module">foundation.law-of-excluded-middle</a>
<a id="11052" class="Keyword">open</a> <a id="11057" class="Keyword">import</a> <a id="11064" href="foundation.lawveres-fixed-point-theorem.html" class="Module">foundation.lawveres-fixed-point-theorem</a>
<a id="11104" class="Keyword">open</a> <a id="11109" class="Keyword">import</a> <a id="11116" href="foundation.locally-small-types.html" class="Module">foundation.locally-small-types</a>
<a id="11147" class="Keyword">open</a> <a id="11152" class="Keyword">import</a> <a id="11159" href="foundation.logical-equivalences.html" class="Module">foundation.logical-equivalences</a>
<a id="11191" class="Keyword">open</a> <a id="11196" class="Keyword">import</a> <a id="11203" href="foundation.lower-types-w-types.html" class="Module">foundation.lower-types-w-types</a>
<a id="11234" class="Keyword">open</a> <a id="11239" class="Keyword">import</a> <a id="11246" href="foundation.maybe.html" class="Module">foundation.maybe</a>
<a id="11263" class="Keyword">open</a> <a id="11268" class="Keyword">import</a> <a id="11275" href="foundation.mere-equality.html" class="Module">foundation.mere-equality</a>
<a id="11300" class="Keyword">open</a> <a id="11305" class="Keyword">import</a> <a id="11312" href="foundation.mere-equivalences.html" class="Module">foundation.mere-equivalences</a>
<a id="11341" class="Keyword">open</a> <a id="11346" class="Keyword">import</a> <a id="11353" href="foundation.monomorphisms.html" class="Module">foundation.monomorphisms</a>
<a id="11378" class="Keyword">open</a> <a id="11383" class="Keyword">import</a> <a id="11390" href="foundation.multisets.html" class="Module">foundation.multisets</a>
<a id="11411" class="Keyword">open</a> <a id="11416" class="Keyword">import</a> <a id="11423" href="foundation.negation.html" class="Module">foundation.negation</a>
<a id="11443" class="Keyword">open</a> <a id="11448" class="Keyword">import</a> <a id="11455" href="foundation.non-contractible-types.html" class="Module">foundation.non-contractible-types</a>
<a id="11489" class="Keyword">open</a> <a id="11494" class="Keyword">import</a> <a id="11501" href="foundation.path-algebra.html" class="Module">foundation.path-algebra</a>
<a id="11525" class="Keyword">open</a> <a id="11530" class="Keyword">import</a> <a id="11537" href="foundation.path-split-maps.html" class="Module">foundation.path-split-maps</a>
<a id="11564" class="Keyword">open</a> <a id="11569" class="Keyword">import</a> <a id="11576" href="foundation.polynomial-endofunctors.html" class="Module">foundation.polynomial-endofunctors</a>
<a id="11611" class="Keyword">open</a> <a id="11616" class="Keyword">import</a> <a id="11623" href="foundation.propositional-extensionality.html" class="Module">foundation.propositional-extensionality</a>
<a id="11663" class="Keyword">open</a> <a id="11668" class="Keyword">import</a> <a id="11675" href="foundation.propositional-maps.html" class="Module">foundation.propositional-maps</a>
<a id="11705" class="Keyword">open</a> <a id="11710" class="Keyword">import</a> <a id="11717" href="foundation.propositional-truncations.html" class="Module">foundation.propositional-truncations</a>
<a id="11754" class="Keyword">open</a> <a id="11759" class="Keyword">import</a> <a id="11766" href="foundation.propositions.html" class="Module">foundation.propositions</a>
<a id="11790" class="Keyword">open</a> <a id="11795" class="Keyword">import</a> <a id="11802" href="foundation.pullbacks.html" class="Module">foundation.pullbacks</a>
<a id="11823" class="Keyword">open</a> <a id="11828" class="Keyword">import</a> <a id="11835" href="foundation.raising-universe-levels.html" class="Module">foundation.raising-universe-levels</a>
<a id="11870" class="Keyword">open</a> <a id="11875" class="Keyword">import</a> <a id="11882" href="foundation.ranks-of-elements-w-types.html" class="Module">foundation.ranks-of-elements-w-types</a>
<a id="11919" class="Keyword">open</a> <a id="11924" class="Keyword">import</a> <a id="11931" href="foundation.reflecting-maps-equivalence-relations.html" class="Module">foundation.reflecting-maps-equivalence-relations</a>
<a id="11980" class="Keyword">open</a> <a id="11985" class="Keyword">import</a> <a id="11992" href="foundation.replacement.html" class="Module">foundation.replacement</a>
<a id="12015" class="Keyword">open</a> <a id="12020" class="Keyword">import</a> <a id="12027" href="foundation.retractions.html" class="Module">foundation.retractions</a>
<a id="12050" class="Keyword">open</a> <a id="12055" class="Keyword">import</a> <a id="12062" href="foundation.russells-paradox.html" class="Module">foundation.russells-paradox</a>
<a id="12090" class="Keyword">open</a> <a id="12095" class="Keyword">import</a> <a id="12102" href="foundation.sections.html" class="Module">foundation.sections</a>
<a id="12122" class="Keyword">open</a> <a id="12127" class="Keyword">import</a> <a id="12134" href="foundation.set-presented-types.html" class="Module">foundation.set-presented-types</a>
<a id="12165" class="Keyword">open</a> <a id="12170" class="Keyword">import</a> <a id="12177" href="foundation.set-truncations.html" class="Module">foundation.set-truncations</a>
<a id="12204" class="Keyword">open</a> <a id="12209" class="Keyword">import</a> <a id="12216" href="foundation.sets.html" class="Module">foundation.sets</a>
<a id="12232" class="Keyword">open</a> <a id="12237" class="Keyword">import</a> <a id="12244" href="foundation.singleton-induction.html" class="Module">foundation.singleton-induction</a>
<a id="12275" class="Keyword">open</a> <a id="12280" class="Keyword">import</a> <a id="12287" href="foundation.slice.html" class="Module">foundation.slice</a>
<a id="12304" class="Keyword">open</a> <a id="12309" class="Keyword">import</a> <a id="12316" href="foundation.small-maps.html" class="Module">foundation.small-maps</a>
<a id="12338" class="Keyword">open</a> <a id="12343" class="Keyword">import</a> <a id="12350" href="foundation.small-multisets.html" class="Module">foundation.small-multisets</a>
<a id="12377" class="Keyword">open</a> <a id="12382" class="Keyword">import</a> <a id="12389" href="foundation.small-types.html" class="Module">foundation.small-types</a>
<a id="12412" class="Keyword">open</a> <a id="12417" class="Keyword">import</a> <a id="12424" href="foundation.small-universes.html" class="Module">foundation.small-universes</a>
<a id="12451" class="Keyword">open</a> <a id="12456" class="Keyword">import</a> <a id="12463" href="foundation.split-surjective-maps.html" class="Module">foundation.split-surjective-maps</a>
<a id="12496" class="Keyword">open</a> <a id="12501" class="Keyword">import</a> <a id="12508" href="foundation.structure-identity-principle.html" class="Module">foundation.structure-identity-principle</a>
<a id="12548" class="Keyword">open</a> <a id="12553" class="Keyword">import</a> <a id="12560" href="foundation.structure.html" class="Module">foundation.structure</a>
<a id="12581" class="Keyword">open</a> <a id="12586" class="Keyword">import</a> <a id="12593" href="foundation.subterminal-types.html" class="Module">foundation.subterminal-types</a>
<a id="12622" class="Keyword">open</a> <a id="12627" class="Keyword">import</a> <a id="12634" href="foundation.subtype-identity-principle.html" class="Module">foundation.subtype-identity-principle</a>
<a id="12672" class="Keyword">open</a> <a id="12677" class="Keyword">import</a> <a id="12684" href="foundation.subtypes.html" class="Module">foundation.subtypes</a>
<a id="12704" class="Keyword">open</a> <a id="12709" class="Keyword">import</a> <a id="12716" href="foundation.subuniverses.html" class="Module">foundation.subuniverses</a>
<a id="12740" class="Keyword">open</a> <a id="12745" class="Keyword">import</a> <a id="12752" href="foundation.surjective-maps.html" class="Module">foundation.surjective-maps</a>
<a id="12779" class="Keyword">open</a> <a id="12784" class="Keyword">import</a> <a id="12791" href="foundation.truncated-equality.html" class="Module">foundation.truncated-equality</a>
<a id="12821" class="Keyword">open</a> <a id="12826" class="Keyword">import</a> <a id="12833" href="foundation.truncated-maps.html" class="Module">foundation.truncated-maps</a>
<a id="12859" class="Keyword">open</a> <a id="12864" class="Keyword">import</a> <a id="12871" href="foundation.truncated-types.html" class="Module">foundation.truncated-types</a>
<a id="12898" class="Keyword">open</a> <a id="12903" class="Keyword">import</a> <a id="12910" href="foundation.truncation-levels.html" class="Module">foundation.truncation-levels</a>
<a id="12939" class="Keyword">open</a> <a id="12944" class="Keyword">import</a> <a id="12951" href="foundation.truncations.html" class="Module">foundation.truncations</a>
<a id="12974" class="Keyword">open</a> <a id="12979" class="Keyword">import</a> <a id="12986" href="foundation.type-arithmetic-cartesian-product-types.html" class="Module">foundation.type-arithmetic-cartesian-product-types</a>
<a id="13037" class="Keyword">open</a> <a id="13042" class="Keyword">import</a> <a id="13049" href="foundation.type-arithmetic-coproduct-types.html" class="Module">foundation.type-arithmetic-coproduct-types</a>
<a id="13092" class="Keyword">open</a> <a id="13097" class="Keyword">import</a> <a id="13104" href="foundation.type-arithmetic-dependent-pair-types.html" class="Module">foundation.type-arithmetic-dependent-pair-types</a>
<a id="13152" class="Keyword">open</a> <a id="13157" class="Keyword">import</a> <a id="13164" href="foundation.type-arithmetic-empty-type.html" class="Module">foundation.type-arithmetic-empty-type</a>
<a id="13202" class="Keyword">open</a> <a id="13207" class="Keyword">import</a> <a id="13214" href="foundation.type-arithmetic-unit-type.html" class="Module">foundation.type-arithmetic-unit-type</a>
<a id="13251" class="Keyword">open</a> <a id="13256" class="Keyword">import</a> <a id="13263" href="foundation.uniqueness-image.html" class="Module">foundation.uniqueness-image</a>
<a id="13291" class="Keyword">open</a> <a id="13296" class="Keyword">import</a> <a id="13303" href="foundation.uniqueness-set-quotients.html" class="Module">foundation.uniqueness-set-quotients</a>
<a id="13339" class="Keyword">open</a> <a id="13344" class="Keyword">import</a> <a id="13351" href="foundation.uniqueness-set-truncations.html" class="Module">foundation.uniqueness-set-truncations</a>
<a id="13389" class="Keyword">open</a> <a id="13394" class="Keyword">import</a> <a id="13401" href="foundation.uniqueness-truncation.html" class="Module">foundation.uniqueness-truncation</a>
<a id="13434" class="Keyword">open</a> <a id="13439" class="Keyword">import</a> <a id="13446" href="foundation.unit-type.html" class="Module">foundation.unit-type</a>
<a id="13467" class="Keyword">open</a> <a id="13472" class="Keyword">import</a> <a id="13479" href="foundation.univalence-implies-function-extensionality.html" class="Module">foundation.univalence-implies-function-extensionality</a>
<a id="13533" class="Keyword">open</a> <a id="13538" class="Keyword">import</a> <a id="13545" href="foundation.univalence.html" class="Module">foundation.univalence</a>
<a id="13567" class="Keyword">open</a> <a id="13572" class="Keyword">import</a> <a id="13579" href="foundation.univalent-type-families.html" class="Module">foundation.univalent-type-families</a>
<a id="13614" class="Keyword">open</a> <a id="13619" class="Keyword">import</a> <a id="13626" href="foundation.universal-multiset.html" class="Module">foundation.universal-multiset</a>
<a id="13656" class="Keyword">open</a> <a id="13661" class="Keyword">import</a> <a id="13668" href="foundation.universal-property-booleans.html" class="Module">foundation.universal-property-booleans</a>
<a id="13707" class="Keyword">open</a> <a id="13712" class="Keyword">import</a> <a id="13719" href="foundation.universal-property-cartesian-product-types.html" class="Module">foundation.universal-property-cartesian-product-types</a>
<a id="13773" class="Keyword">open</a> <a id="13778" class="Keyword">import</a> <a id="13785" href="foundation.universal-property-coproduct-types.html" class="Module">foundation.universal-property-coproduct-types</a>
<a id="13831" class="Keyword">open</a> <a id="13836" class="Keyword">import</a> <a id="13843" href="foundation.universal-property-dependent-pair-types.html" class="Module">foundation.universal-property-dependent-pair-types</a>
<a id="13894" class="Keyword">open</a> <a id="13899" class="Keyword">import</a> <a id="13906" href="foundation.universal-property-empty-type.html" class="Module">foundation.universal-property-empty-type</a>
<a id="13947" class="Keyword">open</a> <a id="13952" class="Keyword">import</a> <a id="13959" href="foundation.universal-property-fiber-products.html" class="Module">foundation.universal-property-fiber-products</a>
<a id="14004" class="Keyword">open</a> <a id="14009" class="Keyword">import</a> <a id="14016" href="foundation.universal-property-identity-types.html" class="Module">foundation.universal-property-identity-types</a>
<a id="14061" class="Keyword">open</a> <a id="14066" class="Keyword">import</a> <a id="14073" href="foundation.universal-property-image.html" class="Module">foundation.universal-property-image</a>
<a id="14109" class="Keyword">open</a> <a id="14114" class="Keyword">import</a> <a id="14121" href="foundation.universal-property-maybe.html" class="Module">foundation.universal-property-maybe</a>
<a id="14157" class="Keyword">open</a> <a id="14162" class="Keyword">import</a> <a id="14169" href="foundation.universal-property-propositional-truncation-into-sets.html" class="Module">foundation.universal-property-propositional-truncation-into-sets</a>
<a id="14234" class="Keyword">open</a> <a id="14239" class="Keyword">import</a> <a id="14246" href="foundation.universal-property-propositional-truncation.html" class="Module">foundation.universal-property-propositional-truncation</a>
<a id="14301" class="Keyword">open</a> <a id="14306" class="Keyword">import</a> <a id="14313" href="foundation.universal-property-pullbacks.html" class="Module">foundation.universal-property-pullbacks</a>
<a id="14353" class="Keyword">open</a> <a id="14358" class="Keyword">import</a> <a id="14365" href="foundation.universal-property-set-quotients.html" class="Module">foundation.universal-property-set-quotients</a>
<a id="14409" class="Keyword">open</a> <a id="14414" class="Keyword">import</a> <a id="14421" href="foundation.universal-property-set-truncation.html" class="Module">foundation.universal-property-set-truncation</a>
<a id="14466" class="Keyword">open</a> <a id="14471" class="Keyword">import</a> <a id="14478" href="foundation.universal-property-truncation.html" class="Module">foundation.universal-property-truncation</a>
<a id="14519" class="Keyword">open</a> <a id="14524" class="Keyword">import</a> <a id="14531" href="foundation.universal-property-unit-type.html" class="Module">foundation.universal-property-unit-type</a>
<a id="14571" class="Keyword">open</a> <a id="14576" class="Keyword">import</a> <a id="14583" href="foundation.universe-levels.html" class="Module">foundation.universe-levels</a>
<a id="14610" class="Keyword">open</a> <a id="14615" class="Keyword">import</a> <a id="14622" href="foundation.unordered-pairs.html" class="Module">foundation.unordered-pairs</a>
<a id="14649" class="Keyword">open</a> <a id="14654" class="Keyword">import</a> <a id="14661" href="foundation.w-types.html" class="Module">foundation.w-types</a>
<a id="14680" class="Keyword">open</a> <a id="14685" class="Keyword">import</a> <a id="14692" href="foundation.weak-function-extensionality.html" class="Module">foundation.weak-function-extensionality</a>
<a id="14732" class="Keyword">open</a> <a id="14737" class="Keyword">import</a> <a id="14744" href="foundation.weakly-constant-maps.html" class="Module">foundation.weakly-constant-maps</a>
</pre>
## Foundation Core

<pre class="Agda"><a id="14809" class="Keyword">open</a> <a id="14814" class="Keyword">import</a> <a id="14821" href="foundation-core.0-maps.html" class="Module">foundation-core.0-maps</a>
<a id="14844" class="Keyword">open</a> <a id="14849" class="Keyword">import</a> <a id="14856" href="foundation-core.1-types.html" class="Module">foundation-core.1-types</a>
<a id="14880" class="Keyword">open</a> <a id="14885" class="Keyword">import</a> <a id="14892" href="foundation-core.cartesian-product-types.html" class="Module">foundation-core.cartesian-product-types</a>
<a id="14932" class="Keyword">open</a> <a id="14937" class="Keyword">import</a> <a id="14944" href="foundation-core.coherently-invertible-maps.html" class="Module">foundation-core.coherently-invertible-maps</a>
<a id="14987" class="Keyword">open</a> <a id="14992" class="Keyword">import</a> <a id="14999" href="foundation-core.commuting-squares.html" class="Module">foundation-core.commuting-squares</a>
<a id="15033" class="Keyword">open</a> <a id="15038" class="Keyword">import</a> <a id="15045" href="foundation-core.constant-maps.html" class="Module">foundation-core.constant-maps</a>
<a id="15075" class="Keyword">open</a> <a id="15080" class="Keyword">import</a> <a id="15087" href="foundation-core.contractible-maps.html" class="Module">foundation-core.contractible-maps</a>
<a id="15121" class="Keyword">open</a> <a id="15126" class="Keyword">import</a> <a id="15133" href="foundation-core.contractible-types.html" class="Module">foundation-core.contractible-types</a>
<a id="15168" class="Keyword">open</a> <a id="15173" class="Keyword">import</a> <a id="15180" href="foundation-core.dependent-pair-types.html" class="Module">foundation-core.dependent-pair-types</a>
<a id="15217" class="Keyword">open</a> <a id="15222" class="Keyword">import</a> <a id="15229" href="foundation-core.embeddings.html" class="Module">foundation-core.embeddings</a>
<a id="15256" class="Keyword">open</a> <a id="15261" class="Keyword">import</a> <a id="15268" href="foundation-core.empty-types.html" class="Module">foundation-core.empty-types</a>
<a id="15296" class="Keyword">open</a> <a id="15301" class="Keyword">import</a> <a id="15308" href="foundation-core.equality-cartesian-product-types.html" class="Module">foundation-core.equality-cartesian-product-types</a>
<a id="15357" class="Keyword">open</a> <a id="15362" class="Keyword">import</a> <a id="15369" href="foundation-core.equality-dependent-pair-types.html" class="Module">foundation-core.equality-dependent-pair-types</a>
<a id="15415" class="Keyword">open</a> <a id="15420" class="Keyword">import</a> <a id="15427" href="foundation-core.equality-fibers-of-maps.html" class="Module">foundation-core.equality-fibers-of-maps</a>
<a id="15467" class="Keyword">open</a> <a id="15472" class="Keyword">import</a> <a id="15479" href="foundation-core.equivalence-induction.html" class="Module">foundation-core.equivalence-induction</a>
<a id="15517" class="Keyword">open</a> <a id="15522" class="Keyword">import</a> <a id="15529" href="foundation-core.equivalences.html" class="Module">foundation-core.equivalences</a>
<a id="15558" class="Keyword">open</a> <a id="15563" class="Keyword">import</a> <a id="15570" href="foundation-core.faithful-maps.html" class="Module">foundation-core.faithful-maps</a>
<a id="15600" class="Keyword">open</a> <a id="15605" class="Keyword">import</a> <a id="15612" href="foundation-core.fibers-of-maps.html" class="Module">foundation-core.fibers-of-maps</a>
<a id="15643" class="Keyword">open</a> <a id="15648" class="Keyword">import</a> <a id="15655" href="foundation-core.functions.html" class="Module">foundation-core.functions</a>
<a id="15681" class="Keyword">open</a> <a id="15686" class="Keyword">import</a> <a id="15693" href="foundation-core.functoriality-dependent-pair-types.html" class="Module">foundation-core.functoriality-dependent-pair-types</a>
<a id="15744" class="Keyword">open</a> <a id="15749" class="Keyword">import</a> <a id="15756" href="foundation-core.fundamental-theorem-of-identity-types.html" class="Module">foundation-core.fundamental-theorem-of-identity-types</a>
<a id="15810" class="Keyword">open</a> <a id="15815" class="Keyword">import</a> <a id="15822" href="foundation-core.homotopies.html" class="Module">foundation-core.homotopies</a>
<a id="15849" class="Keyword">open</a> <a id="15854" class="Keyword">import</a> <a id="15861" href="foundation-core.identity-systems.html" class="Module">foundation-core.identity-systems</a>
<a id="15894" class="Keyword">open</a> <a id="15899" class="Keyword">import</a> <a id="15906" href="foundation-core.identity-types.html" class="Module">foundation-core.identity-types</a>
<a id="15937" class="Keyword">open</a> <a id="15942" class="Keyword">import</a> <a id="15949" href="foundation-core.logical-equivalences.html" class="Module">foundation-core.logical-equivalences</a>
<a id="15986" class="Keyword">open</a> <a id="15991" class="Keyword">import</a> <a id="15998" href="foundation-core.negation.html" class="Module">foundation-core.negation</a>
<a id="16023" class="Keyword">open</a> <a id="16028" class="Keyword">import</a> <a id="16035" href="foundation-core.path-split-maps.html" class="Module">foundation-core.path-split-maps</a>
<a id="16067" class="Keyword">open</a> <a id="16072" class="Keyword">import</a> <a id="16079" href="foundation-core.propositional-maps.html" class="Module">foundation-core.propositional-maps</a>
<a id="16114" class="Keyword">open</a> <a id="16119" class="Keyword">import</a> <a id="16126" href="foundation-core.propositions.html" class="Module">foundation-core.propositions</a>
<a id="16155" class="Keyword">open</a> <a id="16160" class="Keyword">import</a> <a id="16167" href="foundation-core.retractions.html" class="Module">foundation-core.retractions</a>
<a id="16195" class="Keyword">open</a> <a id="16200" class="Keyword">import</a> <a id="16207" href="foundation-core.sections.html" class="Module">foundation-core.sections</a>
<a id="16232" class="Keyword">open</a> <a id="16237" class="Keyword">import</a> <a id="16244" href="foundation-core.sets.html" class="Module">foundation-core.sets</a>
<a id="16265" class="Keyword">open</a> <a id="16270" class="Keyword">import</a> <a id="16277" href="foundation-core.singleton-induction.html" class="Module">foundation-core.singleton-induction</a>
<a id="16313" class="Keyword">open</a> <a id="16318" class="Keyword">import</a> <a id="16325" href="foundation-core.subtype-identity-principle.html" class="Module">foundation-core.subtype-identity-principle</a>
<a id="16368" class="Keyword">open</a> <a id="16373" class="Keyword">import</a> <a id="16380" href="foundation-core.subtypes.html" class="Module">foundation-core.subtypes</a>
<a id="16405" class="Keyword">open</a> <a id="16410" class="Keyword">import</a> <a id="16417" href="foundation-core.truncated-maps.html" class="Module">foundation-core.truncated-maps</a>
<a id="16448" class="Keyword">open</a> <a id="16453" class="Keyword">import</a> <a id="16460" href="foundation-core.truncated-types.html" class="Module">foundation-core.truncated-types</a>
<a id="16492" class="Keyword">open</a> <a id="16497" class="Keyword">import</a> <a id="16504" href="foundation-core.truncation-levels.html" class="Module">foundation-core.truncation-levels</a>
<a id="16538" class="Keyword">open</a> <a id="16543" class="Keyword">import</a> <a id="16550" href="foundation-core.type-arithmetic-cartesian-product-types.html" class="Module">foundation-core.type-arithmetic-cartesian-product-types</a>
<a id="16606" class="Keyword">open</a> <a id="16611" class="Keyword">import</a> <a id="16618" href="foundation-core.type-arithmetic-dependent-pair-types.html" class="Module">foundation-core.type-arithmetic-dependent-pair-types</a>
<a id="16671" class="Keyword">open</a> <a id="16676" class="Keyword">import</a> <a id="16683" href="foundation-core.univalence.html" class="Module">foundation-core.univalence</a>
<a id="16710" class="Keyword">open</a> <a id="16715" class="Keyword">import</a> <a id="16722" href="foundation-core.universe-levels.html" class="Module">foundation-core.universe-levels</a>
</pre>
## Graph theory

<pre class="Agda"><a id="16784" class="Keyword">open</a> <a id="16789" class="Keyword">import</a> <a id="16796" href="graph-theory.html" class="Module">graph-theory</a>
<a id="16809" class="Keyword">open</a> <a id="16814" class="Keyword">import</a> <a id="16821" href="graph-theory.connected-undirected-graphs.html" class="Module">graph-theory.connected-undirected-graphs</a>
<a id="16862" class="Keyword">open</a> <a id="16867" class="Keyword">import</a> <a id="16874" href="graph-theory.directed-graphs.html" class="Module">graph-theory.directed-graphs</a>
<a id="16903" class="Keyword">open</a> <a id="16908" class="Keyword">import</a> <a id="16915" href="graph-theory.edge-coloured-undirected-graphs.html" class="Module">graph-theory.edge-coloured-undirected-graphs</a>
<a id="16960" class="Keyword">open</a> <a id="16965" class="Keyword">import</a> <a id="16972" href="graph-theory.equivalences-undirected-graphs.html" class="Module">graph-theory.equivalences-undirected-graphs</a>
<a id="17016" class="Keyword">open</a> <a id="17021" class="Keyword">import</a> <a id="17028" href="graph-theory.finite-graphs.html" class="Module">graph-theory.finite-graphs</a>
<a id="17055" class="Keyword">open</a> <a id="17060" class="Keyword">import</a> <a id="17067" href="graph-theory.incidence-undirected-graphs.html" class="Module">graph-theory.incidence-undirected-graphs</a>
<a id="17108" class="Keyword">open</a> <a id="17113" class="Keyword">import</a> <a id="17120" href="graph-theory.mere-equivalences-undirected-graphs.html" class="Module">graph-theory.mere-equivalences-undirected-graphs</a>
<a id="17169" class="Keyword">open</a> <a id="17174" class="Keyword">import</a> <a id="17181" href="graph-theory.morphisms-directed-graphs.html" class="Module">graph-theory.morphisms-directed-graphs</a>
<a id="17220" class="Keyword">open</a> <a id="17225" class="Keyword">import</a> <a id="17232" href="graph-theory.morphisms-undirected-graphs.html" class="Module">graph-theory.morphisms-undirected-graphs</a>
<a id="17273" class="Keyword">open</a> <a id="17278" class="Keyword">import</a> <a id="17285" href="graph-theory.orientations-undirected-graphs.html" class="Module">graph-theory.orientations-undirected-graphs</a>
<a id="17329" class="Keyword">open</a> <a id="17334" class="Keyword">import</a> <a id="17341" href="graph-theory.paths-undirected-graphs.html" class="Module">graph-theory.paths-undirected-graphs</a>
<a id="17378" class="Keyword">open</a> <a id="17383" class="Keyword">import</a> <a id="17390" href="graph-theory.polygons.html" class="Module">graph-theory.polygons</a>
<a id="17412" class="Keyword">open</a> <a id="17417" class="Keyword">import</a> <a id="17424" href="graph-theory.reflexive-graphs.html" class="Module">graph-theory.reflexive-graphs</a>
<a id="17454" class="Keyword">open</a> <a id="17459" class="Keyword">import</a> <a id="17466" href="graph-theory.regular-undirected-graphs.html" class="Module">graph-theory.regular-undirected-graphs</a>
<a id="17505" class="Keyword">open</a> <a id="17510" class="Keyword">import</a> <a id="17517" href="graph-theory.simple-undirected-graphs.html" class="Module">graph-theory.simple-undirected-graphs</a>
<a id="17555" class="Keyword">open</a> <a id="17560" class="Keyword">import</a> <a id="17567" href="graph-theory.undirected-graphs.html" class="Module">graph-theory.undirected-graphs</a>
</pre>
## Group theory

<pre class="Agda"><a id="17628" class="Keyword">open</a> <a id="17633" class="Keyword">import</a> <a id="17640" href="group-theory.html" class="Module">group-theory</a>
<a id="17653" class="Keyword">open</a> <a id="17658" class="Keyword">import</a> <a id="17665" href="group-theory.abelian-groups.html" class="Module">group-theory.abelian-groups</a>
<a id="17693" class="Keyword">open</a> <a id="17698" class="Keyword">import</a> <a id="17705" href="group-theory.abelian-subgroups.html" class="Module">group-theory.abelian-subgroups</a>
<a id="17736" class="Keyword">open</a> <a id="17741" class="Keyword">import</a> <a id="17748" href="group-theory.abstract-group-torsors.html" class="Module">group-theory.abstract-group-torsors</a>
<a id="17784" class="Keyword">open</a> <a id="17789" class="Keyword">import</a> <a id="17796" href="group-theory.category-of-groups.html" class="Module">group-theory.category-of-groups</a>
<a id="17828" class="Keyword">open</a> <a id="17833" class="Keyword">import</a> <a id="17840" href="group-theory.category-of-semigroups.html" class="Module">group-theory.category-of-semigroups</a>
<a id="17876" class="Keyword">open</a> <a id="17881" class="Keyword">import</a> <a id="17888" href="group-theory.cayleys-theorem.html" class="Module">group-theory.cayleys-theorem</a>
<a id="17917" class="Keyword">open</a> <a id="17922" class="Keyword">import</a> <a id="17929" href="group-theory.concrete-group-actions.html" class="Module">group-theory.concrete-group-actions</a>
<a id="17965" class="Keyword">open</a> <a id="17970" class="Keyword">import</a> <a id="17977" href="group-theory.concrete-groups.html" class="Module">group-theory.concrete-groups</a>
<a id="18006" class="Keyword">open</a> <a id="18011" class="Keyword">import</a> <a id="18018" href="group-theory.concrete-subgroups.html" class="Module">group-theory.concrete-subgroups</a>
<a id="18050" class="Keyword">open</a> <a id="18055" class="Keyword">import</a> <a id="18062" href="group-theory.conjugation.html" class="Module">group-theory.conjugation</a>
<a id="18087" class="Keyword">open</a> <a id="18092" class="Keyword">import</a> <a id="18099" href="group-theory.embeddings-groups.html" class="Module">group-theory.embeddings-groups</a>
<a id="18130" class="Keyword">open</a> <a id="18135" class="Keyword">import</a> <a id="18142" href="group-theory.equivalences-group-actions.html" class="Module">group-theory.equivalences-group-actions</a>
<a id="18182" class="Keyword">open</a> <a id="18187" class="Keyword">import</a> <a id="18194" href="group-theory.equivalences-semigroups.html" class="Module">group-theory.equivalences-semigroups</a>
<a id="18231" class="Keyword">open</a> <a id="18236" class="Keyword">import</a> <a id="18243" href="group-theory.examples-higher-groups.html" class="Module">group-theory.examples-higher-groups</a>
<a id="18279" class="Keyword">open</a> <a id="18284" class="Keyword">import</a> <a id="18291" href="group-theory.furstenberg-groups.html" class="Module">group-theory.furstenberg-groups</a>
<a id="18323" class="Keyword">open</a> <a id="18328" class="Keyword">import</a> <a id="18335" href="group-theory.group-actions.html" class="Module">group-theory.group-actions</a>
<a id="18362" class="Keyword">open</a> <a id="18367" class="Keyword">import</a> <a id="18374" href="group-theory.groups.html" class="Module">group-theory.groups</a>
<a id="18394" class="Keyword">open</a> <a id="18399" class="Keyword">import</a> <a id="18406" href="group-theory.higher-groups.html" class="Module">group-theory.higher-groups</a>
<a id="18433" class="Keyword">open</a> <a id="18438" class="Keyword">import</a> <a id="18445" href="group-theory.homomorphisms-abelian-groups.html" class="Module">group-theory.homomorphisms-abelian-groups</a>
<a id="18487" class="Keyword">open</a> <a id="18492" class="Keyword">import</a> <a id="18499" href="group-theory.homomorphisms-group-actions.html" class="Module">group-theory.homomorphisms-group-actions</a>
<a id="18540" class="Keyword">open</a> <a id="18545" class="Keyword">import</a> <a id="18552" href="group-theory.homomorphisms-groups.html" class="Module">group-theory.homomorphisms-groups</a>
<a id="18586" class="Keyword">open</a> <a id="18591" class="Keyword">import</a> <a id="18598" href="group-theory.homomorphisms-monoids.html" class="Module">group-theory.homomorphisms-monoids</a>
<a id="18633" class="Keyword">open</a> <a id="18638" class="Keyword">import</a> <a id="18645" href="group-theory.homomorphisms-semigroups.html" class="Module">group-theory.homomorphisms-semigroups</a>
<a id="18683" class="Keyword">open</a> <a id="18688" class="Keyword">import</a> <a id="18695" href="group-theory.invertible-elements-monoids.html" class="Module">group-theory.invertible-elements-monoids</a>
<a id="18736" class="Keyword">open</a> <a id="18741" class="Keyword">import</a> <a id="18748" href="group-theory.isomorphisms-abelian-groups.html" class="Module">group-theory.isomorphisms-abelian-groups</a>
<a id="18789" class="Keyword">open</a> <a id="18794" class="Keyword">import</a> <a id="18801" href="group-theory.isomorphisms-group-actions.html" class="Module">group-theory.isomorphisms-group-actions</a>
<a id="18841" class="Keyword">open</a> <a id="18846" class="Keyword">import</a> <a id="18853" href="group-theory.isomorphisms-groups.html" class="Module">group-theory.isomorphisms-groups</a>
<a id="18886" class="Keyword">open</a> <a id="18891" class="Keyword">import</a> <a id="18898" href="group-theory.isomorphisms-semigroups.html" class="Module">group-theory.isomorphisms-semigroups</a>
<a id="18935" class="Keyword">open</a> <a id="18940" class="Keyword">import</a> <a id="18947" href="group-theory.mere-equivalences-group-actions.html" class="Module">group-theory.mere-equivalences-group-actions</a>
<a id="18992" class="Keyword">open</a> <a id="18997" class="Keyword">import</a> <a id="19004" href="group-theory.monoids.html" class="Module">group-theory.monoids</a>
<a id="19025" class="Keyword">open</a> <a id="19030" class="Keyword">import</a> <a id="19037" href="group-theory.orbits-group-actions.html" class="Module">group-theory.orbits-group-actions</a>
<a id="19071" class="Keyword">open</a> <a id="19076" class="Keyword">import</a> <a id="19083" href="group-theory.precategory-of-group-actions.html" class="Module">group-theory.precategory-of-group-actions</a>
<a id="19125" class="Keyword">open</a> <a id="19130" class="Keyword">import</a> <a id="19137" href="group-theory.precategory-of-groups.html" class="Module">group-theory.precategory-of-groups</a>
<a id="19172" class="Keyword">open</a> <a id="19177" class="Keyword">import</a> <a id="19184" href="group-theory.precategory-of-semigroups.html" class="Module">group-theory.precategory-of-semigroups</a>
<a id="19223" class="Keyword">open</a> <a id="19228" class="Keyword">import</a> <a id="19235" href="group-theory.principal-group-actions.html" class="Module">group-theory.principal-group-actions</a>
<a id="19272" class="Keyword">open</a> <a id="19277" class="Keyword">import</a> <a id="19284" href="group-theory.semigroups.html" class="Module">group-theory.semigroups</a>
<a id="19308" class="Keyword">open</a> <a id="19313" class="Keyword">import</a> <a id="19320" href="group-theory.sheargroups.html" class="Module">group-theory.sheargroups</a>
<a id="19345" class="Keyword">open</a> <a id="19350" class="Keyword">import</a> <a id="19357" href="group-theory.stabilizer-groups.html" class="Module">group-theory.stabilizer-groups</a>
<a id="19388" class="Keyword">open</a> <a id="19393" class="Keyword">import</a> <a id="19400" href="group-theory.subgroups.html" class="Module">group-theory.subgroups</a>
<a id="19423" class="Keyword">open</a> <a id="19428" class="Keyword">import</a> <a id="19435" href="group-theory.substitution-functor-group-actions.html" class="Module">group-theory.substitution-functor-group-actions</a>
<a id="19483" class="Keyword">open</a> <a id="19488" class="Keyword">import</a> <a id="19495" href="group-theory.symmetric-groups.html" class="Module">group-theory.symmetric-groups</a>
<a id="19525" class="Keyword">open</a> <a id="19530" class="Keyword">import</a> <a id="19537" href="group-theory.transitive-group-actions.html" class="Module">group-theory.transitive-group-actions</a>
</pre>
## Linear algebra

<pre class="Agda"><a id="19607" class="Keyword">open</a> <a id="19612" class="Keyword">import</a> <a id="19619" href="linear-algebra.html" class="Module">linear-algebra</a>
<a id="19634" class="Keyword">open</a> <a id="19639" class="Keyword">import</a> <a id="19646" href="linear-algebra.constant-matrices.html" class="Module">linear-algebra.constant-matrices</a>
<a id="19679" class="Keyword">open</a> <a id="19684" class="Keyword">import</a> <a id="19691" href="linear-algebra.constant-vectors.html" class="Module">linear-algebra.constant-vectors</a>
<a id="19723" class="Keyword">open</a> <a id="19728" class="Keyword">import</a> <a id="19735" href="linear-algebra.diagonal-matrices-on-rings.html" class="Module">linear-algebra.diagonal-matrices-on-rings</a>
<a id="19777" class="Keyword">open</a> <a id="19782" class="Keyword">import</a> <a id="19789" href="linear-algebra.functoriality-matrices.html" class="Module">linear-algebra.functoriality-matrices</a>
<a id="19827" class="Keyword">open</a> <a id="19832" class="Keyword">import</a> <a id="19839" href="linear-algebra.functoriality-vectors.html" class="Module">linear-algebra.functoriality-vectors</a>
<a id="19876" class="Keyword">open</a> <a id="19881" class="Keyword">import</a> <a id="19888" href="linear-algebra.matrices-on-rings.html" class="Module">linear-algebra.matrices-on-rings</a>
<a id="19921" class="Keyword">open</a> <a id="19926" class="Keyword">import</a> <a id="19933" href="linear-algebra.matrices.html" class="Module">linear-algebra.matrices</a>
<a id="19957" class="Keyword">open</a> <a id="19962" class="Keyword">import</a> <a id="19969" href="linear-algebra.multiplication-matrices.html" class="Module">linear-algebra.multiplication-matrices</a>
<a id="20008" class="Keyword">open</a> <a id="20013" class="Keyword">import</a> <a id="20020" href="linear-algebra.scalar-multiplication-matrices.html" class="Module">linear-algebra.scalar-multiplication-matrices</a>
<a id="20066" class="Keyword">open</a> <a id="20071" class="Keyword">import</a> <a id="20078" href="linear-algebra.scalar-multiplication-vectors.html" class="Module">linear-algebra.scalar-multiplication-vectors</a>
<a id="20123" class="Keyword">open</a> <a id="20128" class="Keyword">import</a> <a id="20135" href="linear-algebra.transposition-matrices.html" class="Module">linear-algebra.transposition-matrices</a>
<a id="20173" class="Keyword">open</a> <a id="20178" class="Keyword">import</a> <a id="20185" href="linear-algebra.vectors-on-rings.html" class="Module">linear-algebra.vectors-on-rings</a>
<a id="20217" class="Keyword">open</a> <a id="20222" class="Keyword">import</a> <a id="20229" href="linear-algebra.vectors.html" class="Module">linear-algebra.vectors</a>
</pre>
## Order theory

<pre class="Agda"><a id="20282" class="Keyword">open</a> <a id="20287" class="Keyword">import</a> <a id="20294" href="order-theory.html" class="Module">order-theory</a>
<a id="20307" class="Keyword">open</a> <a id="20312" class="Keyword">import</a> <a id="20319" href="order-theory.chains-posets.html" class="Module">order-theory.chains-posets</a>
<a id="20346" class="Keyword">open</a> <a id="20351" class="Keyword">import</a> <a id="20358" href="order-theory.chains-preorders.html" class="Module">order-theory.chains-preorders</a>
<a id="20388" class="Keyword">open</a> <a id="20393" class="Keyword">import</a> <a id="20400" href="order-theory.decidable-subposets.html" class="Module">order-theory.decidable-subposets</a>
<a id="20433" class="Keyword">open</a> <a id="20438" class="Keyword">import</a> <a id="20445" href="order-theory.decidable-subpreorders.html" class="Module">order-theory.decidable-subpreorders</a>
<a id="20481" class="Keyword">open</a> <a id="20486" class="Keyword">import</a> <a id="20493" href="order-theory.finite-posets.html" class="Module">order-theory.finite-posets</a>
<a id="20520" class="Keyword">open</a> <a id="20525" class="Keyword">import</a> <a id="20532" href="order-theory.finite-preorders.html" class="Module">order-theory.finite-preorders</a>
<a id="20562" class="Keyword">open</a> <a id="20567" class="Keyword">import</a> <a id="20574" href="order-theory.finitely-graded-posets.html" class="Module">order-theory.finitely-graded-posets</a>
<a id="20610" class="Keyword">open</a> <a id="20615" class="Keyword">import</a> <a id="20622" href="order-theory.interval-subposets.html" class="Module">order-theory.interval-subposets</a>
<a id="20654" class="Keyword">open</a> <a id="20659" class="Keyword">import</a> <a id="20666" href="order-theory.largest-elements-posets.html" class="Module">order-theory.largest-elements-posets</a>
<a id="20703" class="Keyword">open</a> <a id="20708" class="Keyword">import</a> <a id="20715" href="order-theory.largest-elements-preorders.html" class="Module">order-theory.largest-elements-preorders</a>
<a id="20755" class="Keyword">open</a> <a id="20760" class="Keyword">import</a> <a id="20767" href="order-theory.least-elements-posets.html" class="Module">order-theory.least-elements-posets</a>
<a id="20802" class="Keyword">open</a> <a id="20807" class="Keyword">import</a> <a id="20814" href="order-theory.least-elements-preorders.html" class="Module">order-theory.least-elements-preorders</a>
<a id="20852" class="Keyword">open</a> <a id="20857" class="Keyword">import</a> <a id="20864" href="order-theory.locally-finite-posets.html" class="Module">order-theory.locally-finite-posets</a>
<a id="20899" class="Keyword">open</a> <a id="20904" class="Keyword">import</a> <a id="20911" href="order-theory.maximal-chains-posets.html" class="Module">order-theory.maximal-chains-posets</a>
<a id="20946" class="Keyword">open</a> <a id="20951" class="Keyword">import</a> <a id="20958" href="order-theory.maximal-chains-preorders.html" class="Module">order-theory.maximal-chains-preorders</a>
<a id="20996" class="Keyword">open</a> <a id="21001" class="Keyword">import</a> <a id="21008" href="order-theory.planar-binary-trees.html" class="Module">order-theory.planar-binary-trees</a>
<a id="21041" class="Keyword">open</a> <a id="21046" class="Keyword">import</a> <a id="21053" href="order-theory.posets.html" class="Module">order-theory.posets</a>
<a id="21073" class="Keyword">open</a> <a id="21078" class="Keyword">import</a> <a id="21085" href="order-theory.preorders.html" class="Module">order-theory.preorders</a>
<a id="21108" class="Keyword">open</a> <a id="21113" class="Keyword">import</a> <a id="21120" href="order-theory.subposets.html" class="Module">order-theory.subposets</a>
<a id="21143" class="Keyword">open</a> <a id="21148" class="Keyword">import</a> <a id="21155" href="order-theory.subpreorders.html" class="Module">order-theory.subpreorders</a>
<a id="21181" class="Keyword">open</a> <a id="21186" class="Keyword">import</a> <a id="21193" href="order-theory.total-posets.html" class="Module">order-theory.total-posets</a>
<a id="21219" class="Keyword">open</a> <a id="21224" class="Keyword">import</a> <a id="21231" href="order-theory.total-preorders.html" class="Module">order-theory.total-preorders</a>
</pre>
## Polytopes

<pre class="Agda"><a id="21287" class="Keyword">open</a> <a id="21292" class="Keyword">import</a> <a id="21299" href="polytopes.html" class="Module">polytopes</a>
<a id="21309" class="Keyword">open</a> <a id="21314" class="Keyword">import</a> <a id="21321" href="polytopes.abstract-polytopes.html" class="Module">polytopes.abstract-polytopes</a>
</pre>
## Ring theory

<pre class="Agda"><a id="21379" class="Keyword">open</a> <a id="21384" class="Keyword">import</a> <a id="21391" href="ring-theory.html" class="Module">ring-theory</a>
<a id="21403" class="Keyword">open</a> <a id="21408" class="Keyword">import</a> <a id="21415" href="ring-theory.commutative-rings.html" class="Module">ring-theory.commutative-rings</a>
<a id="21445" class="Keyword">open</a> <a id="21450" class="Keyword">import</a> <a id="21457" href="ring-theory.discrete-fields.html" class="Module">ring-theory.discrete-fields</a>
<a id="21485" class="Keyword">open</a> <a id="21490" class="Keyword">import</a> <a id="21497" href="ring-theory.division-rings.html" class="Module">ring-theory.division-rings</a>
<a id="21524" class="Keyword">open</a> <a id="21529" class="Keyword">import</a> <a id="21536" href="ring-theory.eisenstein-integers.html" class="Module">ring-theory.eisenstein-integers</a>
<a id="21568" class="Keyword">open</a> <a id="21573" class="Keyword">import</a> <a id="21580" href="ring-theory.gaussian-integers.html" class="Module">ring-theory.gaussian-integers</a>
<a id="21610" class="Keyword">open</a> <a id="21615" class="Keyword">import</a> <a id="21622" href="ring-theory.homomorphisms-commutative-rings.html" class="Module">ring-theory.homomorphisms-commutative-rings</a>
<a id="21666" class="Keyword">open</a> <a id="21671" class="Keyword">import</a> <a id="21678" href="ring-theory.homomorphisms-rings.html" class="Module">ring-theory.homomorphisms-rings</a>
<a id="21710" class="Keyword">open</a> <a id="21715" class="Keyword">import</a> <a id="21722" href="ring-theory.ideals.html" class="Module">ring-theory.ideals</a>
<a id="21741" class="Keyword">open</a> <a id="21746" class="Keyword">import</a> <a id="21753" href="ring-theory.invertible-elements-rings.html" class="Module">ring-theory.invertible-elements-rings</a>
<a id="21791" class="Keyword">open</a> <a id="21796" class="Keyword">import</a> <a id="21803" href="ring-theory.isomorphisms-commutative-rings.html" class="Module">ring-theory.isomorphisms-commutative-rings</a>
<a id="21846" class="Keyword">open</a> <a id="21851" class="Keyword">import</a> <a id="21858" href="ring-theory.isomorphisms-rings.html" class="Module">ring-theory.isomorphisms-rings</a>
<a id="21889" class="Keyword">open</a> <a id="21894" class="Keyword">import</a> <a id="21901" href="ring-theory.localizations-rings.html" class="Module">ring-theory.localizations-rings</a>
<a id="21933" class="Keyword">open</a> <a id="21938" class="Keyword">import</a> <a id="21945" href="ring-theory.nontrivial-rings.html" class="Module">ring-theory.nontrivial-rings</a>
<a id="21974" class="Keyword">open</a> <a id="21979" class="Keyword">import</a> <a id="21986" href="ring-theory.rings.html" class="Module">ring-theory.rings</a>
</pre>
## Synthetic homotopy theory

<pre class="Agda"><a id="22047" class="Keyword">open</a> <a id="22052" class="Keyword">import</a> <a id="22059" href="synthetic-homotopy-theory.html" class="Module">synthetic-homotopy-theory</a>
<a id="22085" class="Keyword">open</a> <a id="22090" class="Keyword">import</a> <a id="22097" href="synthetic-homotopy-theory.23-pullbacks.html" class="Module">synthetic-homotopy-theory.23-pullbacks</a>
<a id="22136" class="Keyword">open</a> <a id="22141" class="Keyword">import</a> <a id="22148" href="synthetic-homotopy-theory.24-pushouts.html" class="Module">synthetic-homotopy-theory.24-pushouts</a>
<a id="22186" class="Keyword">open</a> <a id="22191" class="Keyword">import</a> <a id="22198" href="synthetic-homotopy-theory.25-cubical-diagrams.html" class="Module">synthetic-homotopy-theory.25-cubical-diagrams</a>
<a id="22244" class="Keyword">open</a> <a id="22249" class="Keyword">import</a> <a id="22256" href="synthetic-homotopy-theory.26-descent.html" class="Module">synthetic-homotopy-theory.26-descent</a>
<a id="22293" class="Keyword">open</a> <a id="22298" class="Keyword">import</a> <a id="22305" href="synthetic-homotopy-theory.26-id-pushout.html" class="Module">synthetic-homotopy-theory.26-id-pushout</a>
<a id="22345" class="Keyword">open</a> <a id="22350" class="Keyword">import</a> <a id="22357" href="synthetic-homotopy-theory.27-sequences.html" class="Module">synthetic-homotopy-theory.27-sequences</a>
<a id="22396" class="Keyword">open</a> <a id="22401" class="Keyword">import</a> <a id="22408" href="synthetic-homotopy-theory.circle.html" class="Module">synthetic-homotopy-theory.circle</a>
<a id="22441" class="Keyword">open</a> <a id="22446" class="Keyword">import</a> <a id="22453" href="synthetic-homotopy-theory.cyclic-types.html" class="Module">synthetic-homotopy-theory.cyclic-types</a>
<a id="22492" class="Keyword">open</a> <a id="22497" class="Keyword">import</a> <a id="22504" href="synthetic-homotopy-theory.double-loop-spaces.html" class="Module">synthetic-homotopy-theory.double-loop-spaces</a>
<a id="22549" class="Keyword">open</a> <a id="22554" class="Keyword">import</a> <a id="22561" href="synthetic-homotopy-theory.functoriality-loop-spaces.html" class="Module">synthetic-homotopy-theory.functoriality-loop-spaces</a>
<a id="22613" class="Keyword">open</a> <a id="22618" class="Keyword">import</a> <a id="22625" href="synthetic-homotopy-theory.groups-of-loops-in-1-types.html" class="Module">synthetic-homotopy-theory.groups-of-loops-in-1-types</a>
<a id="22678" class="Keyword">open</a> <a id="22683" class="Keyword">import</a> <a id="22690" href="synthetic-homotopy-theory.infinite-cyclic-types.html" class="Module">synthetic-homotopy-theory.infinite-cyclic-types</a>
<a id="22738" class="Keyword">open</a> <a id="22743" class="Keyword">import</a> <a id="22750" href="synthetic-homotopy-theory.interval-type.html" class="Module">synthetic-homotopy-theory.interval-type</a>
<a id="22790" class="Keyword">open</a> <a id="22795" class="Keyword">import</a> <a id="22802" href="synthetic-homotopy-theory.iterated-loop-spaces.html" class="Module">synthetic-homotopy-theory.iterated-loop-spaces</a>
<a id="22849" class="Keyword">open</a> <a id="22854" class="Keyword">import</a> <a id="22861" href="synthetic-homotopy-theory.loop-spaces.html" class="Module">synthetic-homotopy-theory.loop-spaces</a>
<a id="22899" class="Keyword">open</a> <a id="22904" class="Keyword">import</a> <a id="22911" href="synthetic-homotopy-theory.pointed-dependent-functions.html" class="Module">synthetic-homotopy-theory.pointed-dependent-functions</a>
<a id="22965" class="Keyword">open</a> <a id="22970" class="Keyword">import</a> <a id="22977" href="synthetic-homotopy-theory.pointed-equivalences.html" class="Module">synthetic-homotopy-theory.pointed-equivalences</a>
<a id="23024" class="Keyword">open</a> <a id="23029" class="Keyword">import</a> <a id="23036" href="synthetic-homotopy-theory.pointed-families-of-types.html" class="Module">synthetic-homotopy-theory.pointed-families-of-types</a>
<a id="23088" class="Keyword">open</a> <a id="23093" class="Keyword">import</a> <a id="23100" href="synthetic-homotopy-theory.pointed-homotopies.html" class="Module">synthetic-homotopy-theory.pointed-homotopies</a>
<a id="23145" class="Keyword">open</a> <a id="23150" class="Keyword">import</a> <a id="23157" href="synthetic-homotopy-theory.pointed-maps.html" class="Module">synthetic-homotopy-theory.pointed-maps</a>
<a id="23196" class="Keyword">open</a> <a id="23201" class="Keyword">import</a> <a id="23208" href="synthetic-homotopy-theory.pointed-types.html" class="Module">synthetic-homotopy-theory.pointed-types</a>
<a id="23248" class="Keyword">open</a> <a id="23253" class="Keyword">import</a> <a id="23260" href="synthetic-homotopy-theory.spaces.html" class="Module">synthetic-homotopy-theory.spaces</a>
<a id="23293" class="Keyword">open</a> <a id="23298" class="Keyword">import</a> <a id="23305" href="synthetic-homotopy-theory.triple-loop-spaces.html" class="Module">synthetic-homotopy-theory.triple-loop-spaces</a>
<a id="23350" class="Keyword">open</a> <a id="23355" class="Keyword">import</a> <a id="23362" href="synthetic-homotopy-theory.universal-cover-circle.html" class="Module">synthetic-homotopy-theory.universal-cover-circle</a>
</pre>
## Tutorials

<pre class="Agda"><a id="23438" class="Keyword">open</a> <a id="23443" class="Keyword">import</a> <a id="23450" href="tutorials.basic-agda.html" class="Module">tutorials.basic-agda</a>
</pre>
## Univalent combinatorics

<pre class="Agda"><a id="23512" class="Keyword">open</a> <a id="23517" class="Keyword">import</a> <a id="23524" href="univalent-combinatorics.html" class="Module">univalent-combinatorics</a>
<a id="23548" class="Keyword">open</a> <a id="23553" class="Keyword">import</a> <a id="23560" href="univalent-combinatorics.2-element-subtypes.html" class="Module">univalent-combinatorics.2-element-subtypes</a>
<a id="23603" class="Keyword">open</a> <a id="23608" class="Keyword">import</a> <a id="23615" href="univalent-combinatorics.2-element-types.html" class="Module">univalent-combinatorics.2-element-types</a>
<a id="23655" class="Keyword">open</a> <a id="23660" class="Keyword">import</a> <a id="23667" href="univalent-combinatorics.binomial-types.html" class="Module">univalent-combinatorics.binomial-types</a>
<a id="23706" class="Keyword">open</a> <a id="23711" class="Keyword">import</a> <a id="23718" href="univalent-combinatorics.cartesian-product-types.html" class="Module">univalent-combinatorics.cartesian-product-types</a>
<a id="23766" class="Keyword">open</a> <a id="23771" class="Keyword">import</a> <a id="23778" href="univalent-combinatorics.classical-finite-types.html" class="Module">univalent-combinatorics.classical-finite-types</a>
<a id="23825" class="Keyword">open</a> <a id="23830" class="Keyword">import</a> <a id="23837" href="univalent-combinatorics.complements-isolated-points.html" class="Module">univalent-combinatorics.complements-isolated-points</a>
<a id="23889" class="Keyword">open</a> <a id="23894" class="Keyword">import</a> <a id="23901" href="univalent-combinatorics.coproduct-types.html" class="Module">univalent-combinatorics.coproduct-types</a>
<a id="23941" class="Keyword">open</a> <a id="23946" class="Keyword">import</a> <a id="23953" href="univalent-combinatorics.counting-decidable-subtypes.html" class="Module">univalent-combinatorics.counting-decidable-subtypes</a>
<a id="24005" class="Keyword">open</a> <a id="24010" class="Keyword">import</a> <a id="24017" href="univalent-combinatorics.counting-dependent-function-types.html" class="Module">univalent-combinatorics.counting-dependent-function-types</a>
<a id="24075" class="Keyword">open</a> <a id="24080" class="Keyword">import</a> <a id="24087" href="univalent-combinatorics.counting-dependent-pair-types.html" class="Module">univalent-combinatorics.counting-dependent-pair-types</a>
<a id="24141" class="Keyword">open</a> <a id="24146" class="Keyword">import</a> <a id="24153" href="univalent-combinatorics.counting-fibers-of-maps.html" class="Module">univalent-combinatorics.counting-fibers-of-maps</a>
<a id="24201" class="Keyword">open</a> <a id="24206" class="Keyword">import</a> <a id="24213" href="univalent-combinatorics.counting-function-types.html" class="Module">univalent-combinatorics.counting-function-types</a>
<a id="24261" class="Keyword">open</a> <a id="24266" class="Keyword">import</a> <a id="24273" href="univalent-combinatorics.counting-maybe.html" class="Module">univalent-combinatorics.counting-maybe</a>
<a id="24312" class="Keyword">open</a> <a id="24317" class="Keyword">import</a> <a id="24324" href="univalent-combinatorics.counting.html" class="Module">univalent-combinatorics.counting</a>
<a id="24357" class="Keyword">open</a> <a id="24362" class="Keyword">import</a> <a id="24369" href="univalent-combinatorics.cubes.html" class="Module">univalent-combinatorics.cubes</a>
<a id="24399" class="Keyword">open</a> <a id="24404" class="Keyword">import</a> <a id="24411" href="univalent-combinatorics.decidable-dependent-function-types.html" class="Module">univalent-combinatorics.decidable-dependent-function-types</a>
<a id="24470" class="Keyword">open</a> <a id="24475" class="Keyword">import</a> <a id="24482" href="univalent-combinatorics.decidable-dependent-pair-types.html" class="Module">univalent-combinatorics.decidable-dependent-pair-types</a>
<a id="24537" class="Keyword">open</a> <a id="24542" class="Keyword">import</a> <a id="24549" href="univalent-combinatorics.decidable-subtypes.html" class="Module">univalent-combinatorics.decidable-subtypes</a>
<a id="24592" class="Keyword">open</a> <a id="24597" class="Keyword">import</a> <a id="24604" href="univalent-combinatorics.dependent-product-finite-types.html" class="Module">univalent-combinatorics.dependent-product-finite-types</a>
<a id="24659" class="Keyword">open</a> <a id="24664" class="Keyword">import</a> <a id="24671" href="univalent-combinatorics.dependent-sum-finite-types.html" class="Module">univalent-combinatorics.dependent-sum-finite-types</a>
<a id="24722" class="Keyword">open</a> <a id="24727" class="Keyword">import</a> <a id="24734" href="univalent-combinatorics.distributivity-of-set-truncation-over-finite-products.html" class="Module">univalent-combinatorics.distributivity-of-set-truncation-over-finite-products</a>
<a id="24812" class="Keyword">open</a> <a id="24817" class="Keyword">import</a> <a id="24824" href="univalent-combinatorics.double-counting.html" class="Module">univalent-combinatorics.double-counting</a>
<a id="24864" class="Keyword">open</a> <a id="24869" class="Keyword">import</a> <a id="24876" href="univalent-combinatorics.embeddings-standard-finite-types.html" class="Module">univalent-combinatorics.embeddings-standard-finite-types</a>
<a id="24933" class="Keyword">open</a> <a id="24938" class="Keyword">import</a> <a id="24945" href="univalent-combinatorics.embeddings.html" class="Module">univalent-combinatorics.embeddings</a>
<a id="24980" class="Keyword">open</a> <a id="24985" class="Keyword">import</a> <a id="24992" href="univalent-combinatorics.equality-finite-types.html" class="Module">univalent-combinatorics.equality-finite-types</a>
<a id="25038" class="Keyword">open</a> <a id="25043" class="Keyword">import</a> <a id="25050" href="univalent-combinatorics.equality-standard-finite-types.html" class="Module">univalent-combinatorics.equality-standard-finite-types</a>
<a id="25105" class="Keyword">open</a> <a id="25110" class="Keyword">import</a> <a id="25117" href="univalent-combinatorics.equivalences-cubes.html" class="Module">univalent-combinatorics.equivalences-cubes</a>
<a id="25160" class="Keyword">open</a> <a id="25165" class="Keyword">import</a> <a id="25172" href="univalent-combinatorics.equivalences-standard-finite-types.html" class="Module">univalent-combinatorics.equivalences-standard-finite-types</a>
<a id="25231" class="Keyword">open</a> <a id="25236" class="Keyword">import</a> <a id="25243" href="univalent-combinatorics.equivalences.html" class="Module">univalent-combinatorics.equivalences</a>
<a id="25280" class="Keyword">open</a> <a id="25285" class="Keyword">import</a> <a id="25292" href="univalent-combinatorics.fibers-of-maps-between-finite-types.html" class="Module">univalent-combinatorics.fibers-of-maps-between-finite-types</a>
<a id="25352" class="Keyword">open</a> <a id="25357" class="Keyword">import</a> <a id="25364" href="univalent-combinatorics.finite-choice.html" class="Module">univalent-combinatorics.finite-choice</a>
<a id="25402" class="Keyword">open</a> <a id="25407" class="Keyword">import</a> <a id="25414" href="univalent-combinatorics.finite-connected-components.html" class="Module">univalent-combinatorics.finite-connected-components</a>
<a id="25466" class="Keyword">open</a> <a id="25471" class="Keyword">import</a> <a id="25478" href="univalent-combinatorics.finite-function-types.html" class="Module">univalent-combinatorics.finite-function-types</a>
<a id="25524" class="Keyword">open</a> <a id="25529" class="Keyword">import</a> <a id="25536" href="univalent-combinatorics.finite-presentations.html" class="Module">univalent-combinatorics.finite-presentations</a>
<a id="25581" class="Keyword">open</a> <a id="25586" class="Keyword">import</a> <a id="25593" href="univalent-combinatorics.finite-types.html" class="Module">univalent-combinatorics.finite-types</a>
<a id="25630" class="Keyword">open</a> <a id="25635" class="Keyword">import</a> <a id="25642" href="univalent-combinatorics.finitely-presented-types.html" class="Module">univalent-combinatorics.finitely-presented-types</a>
<a id="25691" class="Keyword">open</a> <a id="25696" class="Keyword">import</a> <a id="25703" href="univalent-combinatorics.image-of-maps.html" class="Module">univalent-combinatorics.image-of-maps</a>
<a id="25741" class="Keyword">open</a> <a id="25746" class="Keyword">import</a> <a id="25753" href="univalent-combinatorics.inequality-types-with-counting.html" class="Module">univalent-combinatorics.inequality-types-with-counting</a>
<a id="25808" class="Keyword">open</a> <a id="25813" class="Keyword">import</a> <a id="25820" href="univalent-combinatorics.injective-maps.html" class="Module">univalent-combinatorics.injective-maps</a>
<a id="25859" class="Keyword">open</a> <a id="25864" class="Keyword">import</a> <a id="25871" href="univalent-combinatorics.lists.html" class="Module">univalent-combinatorics.lists</a>
<a id="25901" class="Keyword">open</a> <a id="25906" class="Keyword">import</a> <a id="25913" href="univalent-combinatorics.maybe.html" class="Module">univalent-combinatorics.maybe</a>
<a id="25943" class="Keyword">open</a> <a id="25948" class="Keyword">import</a> <a id="25955" href="univalent-combinatorics.orientations-cubes.html" class="Module">univalent-combinatorics.orientations-cubes</a>
<a id="25998" class="Keyword">open</a> <a id="26003" class="Keyword">import</a> <a id="26010" href="univalent-combinatorics.pi-finite-types.html" class="Module">univalent-combinatorics.pi-finite-types</a>
<a id="26050" class="Keyword">open</a> <a id="26055" class="Keyword">import</a> <a id="26062" href="univalent-combinatorics.pigeonhole-principle.html" class="Module">univalent-combinatorics.pigeonhole-principle</a>
<a id="26107" class="Keyword">open</a> <a id="26112" class="Keyword">import</a> <a id="26119" href="univalent-combinatorics.presented-pi-finite-types.html" class="Module">univalent-combinatorics.presented-pi-finite-types</a>
<a id="26169" class="Keyword">open</a> <a id="26174" class="Keyword">import</a> <a id="26181" href="univalent-combinatorics.ramsey-theory.html" class="Module">univalent-combinatorics.ramsey-theory</a>
<a id="26219" class="Keyword">open</a> <a id="26224" class="Keyword">import</a> <a id="26231" href="univalent-combinatorics.retracts-of-finite-types.html" class="Module">univalent-combinatorics.retracts-of-finite-types</a>
<a id="26280" class="Keyword">open</a> <a id="26285" class="Keyword">import</a> <a id="26292" href="univalent-combinatorics.skipping-element-standard-finite-types.html" class="Module">univalent-combinatorics.skipping-element-standard-finite-types</a>
<a id="26355" class="Keyword">open</a> <a id="26360" class="Keyword">import</a> <a id="26367" href="univalent-combinatorics.species.html" class="Module">univalent-combinatorics.species</a>
<a id="26399" class="Keyword">open</a> <a id="26404" class="Keyword">import</a> <a id="26411" href="univalent-combinatorics.standard-finite-pruned-trees.html" class="Module">univalent-combinatorics.standard-finite-pruned-trees</a>
<a id="26464" class="Keyword">open</a> <a id="26469" class="Keyword">import</a> <a id="26476" href="univalent-combinatorics.standard-finite-trees.html" class="Module">univalent-combinatorics.standard-finite-trees</a>
<a id="26522" class="Keyword">open</a> <a id="26527" class="Keyword">import</a> <a id="26534" href="univalent-combinatorics.standard-finite-types.html" class="Module">univalent-combinatorics.standard-finite-types</a>
<a id="26580" class="Keyword">open</a> <a id="26585" class="Keyword">import</a> <a id="26592" href="univalent-combinatorics.sums-of-natural-numbers.html" class="Module">univalent-combinatorics.sums-of-natural-numbers</a>
<a id="26640" class="Keyword">open</a> <a id="26645" class="Keyword">import</a> <a id="26652" href="univalent-combinatorics.surjective-maps.html" class="Module">univalent-combinatorics.surjective-maps</a>
</pre>
## Wild algebra

<pre class="Agda"><a id="26722" class="Keyword">open</a> <a id="26727" class="Keyword">import</a> <a id="26734" href="wild-algebra.html" class="Module">wild-algebra</a>
<a id="26747" class="Keyword">open</a> <a id="26752" class="Keyword">import</a> <a id="26759" href="wild-algebra.magmas.html" class="Module">wild-algebra.magmas</a>
<a id="26779" class="Keyword">open</a> <a id="26784" class="Keyword">import</a> <a id="26791" href="wild-algebra.universal-property-lists-wild-monoids.html" class="Module">wild-algebra.universal-property-lists-wild-monoids</a>
<a id="26842" class="Keyword">open</a> <a id="26847" class="Keyword">import</a> <a id="26854" href="wild-algebra.wild-groups.html" class="Module">wild-algebra.wild-groups</a>
<a id="26879" class="Keyword">open</a> <a id="26884" class="Keyword">import</a> <a id="26891" href="wild-algebra.wild-monoids.html" class="Module">wild-algebra.wild-monoids</a>
<a id="26917" class="Keyword">open</a> <a id="26922" class="Keyword">import</a> <a id="26929" href="wild-algebra.wild-unital-magmas.html" class="Module">wild-algebra.wild-unital-magmas</a>
</pre>
## Everything

See the list of all Agda modules [here](everything.html).

