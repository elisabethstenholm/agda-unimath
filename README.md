# Univalent mathematics in Agda

Welcome to the website of the `agda-unimath` formalization project.

[![build](https://github.com/UniMath/agda-unimath/actions/workflows/ci.yaml/badge.svg?branch=master)](https://github.com/UniMath/agda-unimath/actions/workflows/ci.yaml)

<pre class="Agda"><a id="281" class="Symbol">{-#</a> <a id="285" class="Keyword">OPTIONS</a> <a id="293" class="Pragma">--without-K</a> <a id="305" class="Pragma">--exact-split</a> <a id="319" class="Pragma">--guardedness</a> <a id="333" class="Symbol">#-}</a>
</pre>
## Category theory

<pre class="Agda"><a id="370" class="Keyword">open</a> <a id="375" class="Keyword">import</a> <a id="382" href="category-theory.html" class="Module">category-theory</a>
<a id="398" class="Keyword">open</a> <a id="403" class="Keyword">import</a> <a id="410" href="category-theory.adjunctions-large-precategories.html" class="Module">category-theory.adjunctions-large-precategories</a>
<a id="458" class="Keyword">open</a> <a id="463" class="Keyword">import</a> <a id="470" href="category-theory.anafunctors.html" class="Module">category-theory.anafunctors</a>
<a id="498" class="Keyword">open</a> <a id="503" class="Keyword">import</a> <a id="510" href="category-theory.categories.html" class="Module">category-theory.categories</a>
<a id="537" class="Keyword">open</a> <a id="542" class="Keyword">import</a> <a id="549" href="category-theory.equivalences-categories.html" class="Module">category-theory.equivalences-categories</a>
<a id="589" class="Keyword">open</a> <a id="594" class="Keyword">import</a> <a id="601" href="category-theory.equivalences-large-precategories.html" class="Module">category-theory.equivalences-large-precategories</a>
<a id="650" class="Keyword">open</a> <a id="655" class="Keyword">import</a> <a id="662" href="category-theory.equivalences-precategories.html" class="Module">category-theory.equivalences-precategories</a>
<a id="705" class="Keyword">open</a> <a id="710" class="Keyword">import</a> <a id="717" href="category-theory.functors-categories.html" class="Module">category-theory.functors-categories</a>
<a id="753" class="Keyword">open</a> <a id="758" class="Keyword">import</a> <a id="765" href="category-theory.functors-large-precategories.html" class="Module">category-theory.functors-large-precategories</a>
<a id="810" class="Keyword">open</a> <a id="815" class="Keyword">import</a> <a id="822" href="category-theory.functors-precategories.html" class="Module">category-theory.functors-precategories</a>
<a id="861" class="Keyword">open</a> <a id="866" class="Keyword">import</a> <a id="873" href="category-theory.homotopies-natural-transformations-large-precategories.html" class="Module">category-theory.homotopies-natural-transformations-large-precategories</a>
<a id="944" class="Keyword">open</a> <a id="949" class="Keyword">import</a> <a id="956" href="category-theory.initial-objects-precategories.html" class="Module">category-theory.initial-objects-precategories</a>
<a id="1002" class="Keyword">open</a> <a id="1007" class="Keyword">import</a> <a id="1014" href="category-theory.isomorphisms-categories.html" class="Module">category-theory.isomorphisms-categories</a>
<a id="1054" class="Keyword">open</a> <a id="1059" class="Keyword">import</a> <a id="1066" href="category-theory.isomorphisms-large-precategories.html" class="Module">category-theory.isomorphisms-large-precategories</a>
<a id="1115" class="Keyword">open</a> <a id="1120" class="Keyword">import</a> <a id="1127" href="category-theory.isomorphisms-precategories.html" class="Module">category-theory.isomorphisms-precategories</a>
<a id="1170" class="Keyword">open</a> <a id="1175" class="Keyword">import</a> <a id="1182" href="category-theory.large-categories.html" class="Module">category-theory.large-categories</a>
<a id="1215" class="Keyword">open</a> <a id="1220" class="Keyword">import</a> <a id="1227" href="category-theory.large-precategories.html" class="Module">category-theory.large-precategories</a>
<a id="1263" class="Keyword">open</a> <a id="1268" class="Keyword">import</a> <a id="1275" href="category-theory.monomorphisms-large-precategories.html" class="Module">category-theory.monomorphisms-large-precategories</a>
<a id="1325" class="Keyword">open</a> <a id="1330" class="Keyword">import</a> <a id="1337" href="category-theory.natural-isomorphisms-categories.html" class="Module">category-theory.natural-isomorphisms-categories</a>
<a id="1385" class="Keyword">open</a> <a id="1390" class="Keyword">import</a> <a id="1397" href="category-theory.natural-isomorphisms-large-precategories.html" class="Module">category-theory.natural-isomorphisms-large-precategories</a>
<a id="1454" class="Keyword">open</a> <a id="1459" class="Keyword">import</a> <a id="1466" href="category-theory.natural-isomorphisms-precategories.html" class="Module">category-theory.natural-isomorphisms-precategories</a>
<a id="1517" class="Keyword">open</a> <a id="1522" class="Keyword">import</a> <a id="1529" href="category-theory.natural-transformations-categories.html" class="Module">category-theory.natural-transformations-categories</a>
<a id="1580" class="Keyword">open</a> <a id="1585" class="Keyword">import</a> <a id="1592" href="category-theory.natural-transformations-large-precategories.html" class="Module">category-theory.natural-transformations-large-precategories</a>
<a id="1652" class="Keyword">open</a> <a id="1657" class="Keyword">import</a> <a id="1664" href="category-theory.natural-transformations-precategories.html" class="Module">category-theory.natural-transformations-precategories</a>
<a id="1718" class="Keyword">open</a> <a id="1723" class="Keyword">import</a> <a id="1730" href="category-theory.precategories.html" class="Module">category-theory.precategories</a>
<a id="1760" class="Keyword">open</a> <a id="1765" class="Keyword">import</a> <a id="1772" href="category-theory.slice-precategories.html" class="Module">category-theory.slice-precategories</a>
<a id="1808" class="Keyword">open</a> <a id="1813" class="Keyword">import</a> <a id="1820" href="category-theory.terminal-objects-precategories.html" class="Module">category-theory.terminal-objects-precategories</a>
</pre>
## Elementary number theory

<pre class="Agda"><a id="1909" class="Keyword">open</a> <a id="1914" class="Keyword">import</a> <a id="1921" href="elementary-number-theory.html" class="Module">elementary-number-theory</a>
<a id="1946" class="Keyword">open</a> <a id="1951" class="Keyword">import</a> <a id="1958" href="elementary-number-theory.absolute-value-integers.html" class="Module">elementary-number-theory.absolute-value-integers</a>
<a id="2007" class="Keyword">open</a> <a id="2012" class="Keyword">import</a> <a id="2019" href="elementary-number-theory.addition-integers.html" class="Module">elementary-number-theory.addition-integers</a>
<a id="2062" class="Keyword">open</a> <a id="2067" class="Keyword">import</a> <a id="2074" href="elementary-number-theory.addition-natural-numbers.html" class="Module">elementary-number-theory.addition-natural-numbers</a>
<a id="2124" class="Keyword">open</a> <a id="2129" class="Keyword">import</a> <a id="2136" href="elementary-number-theory.arithmetic-functions.html" class="Module">elementary-number-theory.arithmetic-functions</a>
<a id="2182" class="Keyword">open</a> <a id="2187" class="Keyword">import</a> <a id="2194" href="elementary-number-theory.binomial-coefficients.html" class="Module">elementary-number-theory.binomial-coefficients</a>
<a id="2241" class="Keyword">open</a> <a id="2246" class="Keyword">import</a> <a id="2253" href="elementary-number-theory.bounded-sums-arithmetic-functions.html" class="Module">elementary-number-theory.bounded-sums-arithmetic-functions</a>
<a id="2312" class="Keyword">open</a> <a id="2317" class="Keyword">import</a> <a id="2324" href="elementary-number-theory.catalan-numbers.html" class="Module">elementary-number-theory.catalan-numbers</a>
<a id="2365" class="Keyword">open</a> <a id="2370" class="Keyword">import</a> <a id="2377" href="elementary-number-theory.collatz-bijection.html" class="Module">elementary-number-theory.collatz-bijection</a>
<a id="2420" class="Keyword">open</a> <a id="2425" class="Keyword">import</a> <a id="2432" href="elementary-number-theory.collatz-conjecture.html" class="Module">elementary-number-theory.collatz-conjecture</a>
<a id="2476" class="Keyword">open</a> <a id="2481" class="Keyword">import</a> <a id="2488" href="elementary-number-theory.congruence-integers.html" class="Module">elementary-number-theory.congruence-integers</a>
<a id="2533" class="Keyword">open</a> <a id="2538" class="Keyword">import</a> <a id="2545" href="elementary-number-theory.congruence-natural-numbers.html" class="Module">elementary-number-theory.congruence-natural-numbers</a>
<a id="2597" class="Keyword">open</a> <a id="2602" class="Keyword">import</a> <a id="2609" href="elementary-number-theory.decidable-dependent-function-types.html" class="Module">elementary-number-theory.decidable-dependent-function-types</a>
<a id="2669" class="Keyword">open</a> <a id="2674" class="Keyword">import</a> <a id="2681" href="elementary-number-theory.decidable-types.html" class="Module">elementary-number-theory.decidable-types</a>
<a id="2722" class="Keyword">open</a> <a id="2727" class="Keyword">import</a> <a id="2734" href="elementary-number-theory.difference-integers.html" class="Module">elementary-number-theory.difference-integers</a>
<a id="2779" class="Keyword">open</a> <a id="2784" class="Keyword">import</a> <a id="2791" href="elementary-number-theory.dirichlet-convolution.html" class="Module">elementary-number-theory.dirichlet-convolution</a>
<a id="2838" class="Keyword">open</a> <a id="2843" class="Keyword">import</a> <a id="2850" href="elementary-number-theory.distance-integers.html" class="Module">elementary-number-theory.distance-integers</a>
<a id="2893" class="Keyword">open</a> <a id="2898" class="Keyword">import</a> <a id="2905" href="elementary-number-theory.distance-natural-numbers.html" class="Module">elementary-number-theory.distance-natural-numbers</a>
<a id="2955" class="Keyword">open</a> <a id="2960" class="Keyword">import</a> <a id="2967" href="elementary-number-theory.divisibility-integers.html" class="Module">elementary-number-theory.divisibility-integers</a>
<a id="3014" class="Keyword">open</a> <a id="3019" class="Keyword">import</a> <a id="3026" href="elementary-number-theory.divisibility-modular-arithmetic.html" class="Module">elementary-number-theory.divisibility-modular-arithmetic</a>
<a id="3083" class="Keyword">open</a> <a id="3088" class="Keyword">import</a> <a id="3095" href="elementary-number-theory.divisibility-natural-numbers.html" class="Module">elementary-number-theory.divisibility-natural-numbers</a>
<a id="3149" class="Keyword">open</a> <a id="3154" class="Keyword">import</a> <a id="3161" href="elementary-number-theory.divisibility-standard-finite-types.html" class="Module">elementary-number-theory.divisibility-standard-finite-types</a>
<a id="3221" class="Keyword">open</a> <a id="3226" class="Keyword">import</a> <a id="3233" href="elementary-number-theory.equality-integers.html" class="Module">elementary-number-theory.equality-integers</a>
<a id="3276" class="Keyword">open</a> <a id="3281" class="Keyword">import</a> <a id="3288" href="elementary-number-theory.equality-natural-numbers.html" class="Module">elementary-number-theory.equality-natural-numbers</a>
<a id="3338" class="Keyword">open</a> <a id="3343" class="Keyword">import</a> <a id="3350" href="elementary-number-theory.euclidean-division-natural-numbers.html" class="Module">elementary-number-theory.euclidean-division-natural-numbers</a>
<a id="3410" class="Keyword">open</a> <a id="3415" class="Keyword">import</a> <a id="3422" href="elementary-number-theory.eulers-totient-function.html" class="Module">elementary-number-theory.eulers-totient-function</a>
<a id="3471" class="Keyword">open</a> <a id="3476" class="Keyword">import</a> <a id="3483" href="elementary-number-theory.exponentiation-natural-numbers.html" class="Module">elementary-number-theory.exponentiation-natural-numbers</a>
<a id="3539" class="Keyword">open</a> <a id="3544" class="Keyword">import</a> <a id="3551" href="elementary-number-theory.factorials.html" class="Module">elementary-number-theory.factorials</a>
<a id="3587" class="Keyword">open</a> <a id="3592" class="Keyword">import</a> <a id="3599" href="elementary-number-theory.falling-factorials.html" class="Module">elementary-number-theory.falling-factorials</a>
<a id="3643" class="Keyword">open</a> <a id="3648" class="Keyword">import</a> <a id="3655" href="elementary-number-theory.fibonacci-sequence.html" class="Module">elementary-number-theory.fibonacci-sequence</a>
<a id="3699" class="Keyword">open</a> <a id="3704" class="Keyword">import</a> <a id="3711" href="elementary-number-theory.finitary-natural-numbers.html" class="Module">elementary-number-theory.finitary-natural-numbers</a>
<a id="3761" class="Keyword">open</a> <a id="3766" class="Keyword">import</a> <a id="3773" href="elementary-number-theory.finitely-cyclic-maps.html" class="Module">elementary-number-theory.finitely-cyclic-maps</a>
<a id="3819" class="Keyword">open</a> <a id="3824" class="Keyword">import</a> <a id="3831" href="elementary-number-theory.fractions.html" class="Module">elementary-number-theory.fractions</a>
<a id="3866" class="Keyword">open</a> <a id="3871" class="Keyword">import</a> <a id="3878" href="elementary-number-theory.goldbach-conjecture.html" class="Module">elementary-number-theory.goldbach-conjecture</a>
<a id="3923" class="Keyword">open</a> <a id="3928" class="Keyword">import</a> <a id="3935" href="elementary-number-theory.greatest-common-divisor-integers.html" class="Module">elementary-number-theory.greatest-common-divisor-integers</a>
<a id="3993" class="Keyword">open</a> <a id="3998" class="Keyword">import</a> <a id="4005" href="elementary-number-theory.greatest-common-divisor-natural-numbers.html" class="Module">elementary-number-theory.greatest-common-divisor-natural-numbers</a>
<a id="4070" class="Keyword">open</a> <a id="4075" class="Keyword">import</a> <a id="4082" href="elementary-number-theory.group-of-integers.html" class="Module">elementary-number-theory.group-of-integers</a>
<a id="4125" class="Keyword">open</a> <a id="4130" class="Keyword">import</a> <a id="4137" href="elementary-number-theory.groups-of-modular-arithmetic.html" class="Module">elementary-number-theory.groups-of-modular-arithmetic</a>
<a id="4191" class="Keyword">open</a> <a id="4196" class="Keyword">import</a> <a id="4203" href="elementary-number-theory.inequality-integers.html" class="Module">elementary-number-theory.inequality-integers</a>
<a id="4248" class="Keyword">open</a> <a id="4253" class="Keyword">import</a> <a id="4260" href="elementary-number-theory.inequality-natural-numbers.html" class="Module">elementary-number-theory.inequality-natural-numbers</a>
<a id="4312" class="Keyword">open</a> <a id="4317" class="Keyword">import</a> <a id="4324" href="elementary-number-theory.inequality-standard-finite-types.html" class="Module">elementary-number-theory.inequality-standard-finite-types</a>
<a id="4382" class="Keyword">open</a> <a id="4387" class="Keyword">import</a> <a id="4394" href="elementary-number-theory.infinitude-of-primes.html" class="Module">elementary-number-theory.infinitude-of-primes</a>
<a id="4440" class="Keyword">open</a> <a id="4445" class="Keyword">import</a> <a id="4452" href="elementary-number-theory.integers.html" class="Module">elementary-number-theory.integers</a>
<a id="4486" class="Keyword">open</a> <a id="4491" class="Keyword">import</a> <a id="4498" href="elementary-number-theory.iterating-functions.html" class="Module">elementary-number-theory.iterating-functions</a>
<a id="4543" class="Keyword">open</a> <a id="4548" class="Keyword">import</a> <a id="4555" href="elementary-number-theory.lower-bounds-natural-numbers.html" class="Module">elementary-number-theory.lower-bounds-natural-numbers</a>
<a id="4609" class="Keyword">open</a> <a id="4614" class="Keyword">import</a> <a id="4621" href="elementary-number-theory.maximum-natural-numbers.html" class="Module">elementary-number-theory.maximum-natural-numbers</a>
<a id="4670" class="Keyword">open</a> <a id="4675" class="Keyword">import</a> <a id="4682" href="elementary-number-theory.mersenne-primes.html" class="Module">elementary-number-theory.mersenne-primes</a>
<a id="4723" class="Keyword">open</a> <a id="4728" class="Keyword">import</a> <a id="4735" href="elementary-number-theory.minimum-natural-numbers.html" class="Module">elementary-number-theory.minimum-natural-numbers</a>
<a id="4784" class="Keyword">open</a> <a id="4789" class="Keyword">import</a> <a id="4796" href="elementary-number-theory.modular-arithmetic-standard-finite-types.html" class="Module">elementary-number-theory.modular-arithmetic-standard-finite-types</a>
<a id="4862" class="Keyword">open</a> <a id="4867" class="Keyword">import</a> <a id="4874" href="elementary-number-theory.modular-arithmetic.html" class="Module">elementary-number-theory.modular-arithmetic</a>
<a id="4918" class="Keyword">open</a> <a id="4923" class="Keyword">import</a> <a id="4930" href="elementary-number-theory.multiplication-integers.html" class="Module">elementary-number-theory.multiplication-integers</a>
<a id="4979" class="Keyword">open</a> <a id="4984" class="Keyword">import</a> <a id="4991" href="elementary-number-theory.multiplication-natural-numbers.html" class="Module">elementary-number-theory.multiplication-natural-numbers</a>
<a id="5047" class="Keyword">open</a> <a id="5052" class="Keyword">import</a> <a id="5059" href="elementary-number-theory.natural-numbers.html" class="Module">elementary-number-theory.natural-numbers</a>
<a id="5100" class="Keyword">open</a> <a id="5105" class="Keyword">import</a> <a id="5112" href="elementary-number-theory.nonzero-natural-numbers.html" class="Module">elementary-number-theory.nonzero-natural-numbers</a>
<a id="5161" class="Keyword">open</a> <a id="5166" class="Keyword">import</a> <a id="5173" href="elementary-number-theory.ordinal-induction-natural-numbers.html" class="Module">elementary-number-theory.ordinal-induction-natural-numbers</a>
<a id="5232" class="Keyword">open</a> <a id="5237" class="Keyword">import</a> <a id="5244" href="elementary-number-theory.prime-numbers.html" class="Module">elementary-number-theory.prime-numbers</a>
<a id="5283" class="Keyword">open</a> <a id="5288" class="Keyword">import</a> <a id="5295" href="elementary-number-theory.products-of-natural-numbers.html" class="Module">elementary-number-theory.products-of-natural-numbers</a>
<a id="5348" class="Keyword">open</a> <a id="5353" class="Keyword">import</a> <a id="5360" href="elementary-number-theory.proper-divisors-natural-numbers.html" class="Module">elementary-number-theory.proper-divisors-natural-numbers</a>
<a id="5417" class="Keyword">open</a> <a id="5422" class="Keyword">import</a> <a id="5429" href="elementary-number-theory.rational-numbers.html" class="Module">elementary-number-theory.rational-numbers</a>
<a id="5471" class="Keyword">open</a> <a id="5476" class="Keyword">import</a> <a id="5483" href="elementary-number-theory.relatively-prime-integers.html" class="Module">elementary-number-theory.relatively-prime-integers</a>
<a id="5534" class="Keyword">open</a> <a id="5539" class="Keyword">import</a> <a id="5546" href="elementary-number-theory.relatively-prime-natural-numbers.html" class="Module">elementary-number-theory.relatively-prime-natural-numbers</a>
<a id="5604" class="Keyword">open</a> <a id="5609" class="Keyword">import</a> <a id="5616" href="elementary-number-theory.repeating-element-standard-finite-type.html" class="Module">elementary-number-theory.repeating-element-standard-finite-type</a>
<a id="5680" class="Keyword">open</a> <a id="5685" class="Keyword">import</a> <a id="5692" href="elementary-number-theory.retracts-of-natural-numbers.html" class="Module">elementary-number-theory.retracts-of-natural-numbers</a>
<a id="5745" class="Keyword">open</a> <a id="5750" class="Keyword">import</a> <a id="5757" href="elementary-number-theory.square-free-natural-numbers.html" class="Module">elementary-number-theory.square-free-natural-numbers</a>
<a id="5810" class="Keyword">open</a> <a id="5815" class="Keyword">import</a> <a id="5822" href="elementary-number-theory.stirling-numbers-of-the-second-kind.html" class="Module">elementary-number-theory.stirling-numbers-of-the-second-kind</a>
<a id="5883" class="Keyword">open</a> <a id="5888" class="Keyword">import</a> <a id="5895" href="elementary-number-theory.strong-induction-natural-numbers.html" class="Module">elementary-number-theory.strong-induction-natural-numbers</a>
<a id="5953" class="Keyword">open</a> <a id="5958" class="Keyword">import</a> <a id="5965" href="elementary-number-theory.sums-of-natural-numbers.html" class="Module">elementary-number-theory.sums-of-natural-numbers</a>
<a id="6014" class="Keyword">open</a> <a id="6019" class="Keyword">import</a> <a id="6026" href="elementary-number-theory.triangular-numbers.html" class="Module">elementary-number-theory.triangular-numbers</a>
<a id="6070" class="Keyword">open</a> <a id="6075" class="Keyword">import</a> <a id="6082" href="elementary-number-theory.telephone-numbers.html" class="Module">elementary-number-theory.telephone-numbers</a>
<a id="6125" class="Keyword">open</a> <a id="6130" class="Keyword">import</a> <a id="6137" href="elementary-number-theory.twin-prime-conjecture.html" class="Module">elementary-number-theory.twin-prime-conjecture</a>
<a id="6184" class="Keyword">open</a> <a id="6189" class="Keyword">import</a> <a id="6196" href="elementary-number-theory.unit-elements-standard-finite-types.html" class="Module">elementary-number-theory.unit-elements-standard-finite-types</a>
<a id="6257" class="Keyword">open</a> <a id="6262" class="Keyword">import</a> <a id="6269" href="elementary-number-theory.unit-similarity-standard-finite-types.html" class="Module">elementary-number-theory.unit-similarity-standard-finite-types</a>
<a id="6332" class="Keyword">open</a> <a id="6337" class="Keyword">import</a> <a id="6344" href="elementary-number-theory.universal-property-natural-numbers.html" class="Module">elementary-number-theory.universal-property-natural-numbers</a>
<a id="6404" class="Keyword">open</a> <a id="6409" class="Keyword">import</a> <a id="6416" href="elementary-number-theory.upper-bounds-natural-numbers.html" class="Module">elementary-number-theory.upper-bounds-natural-numbers</a>
<a id="6470" class="Keyword">open</a> <a id="6475" class="Keyword">import</a> <a id="6482" href="elementary-number-theory.well-ordering-principle-natural-numbers.html" class="Module">elementary-number-theory.well-ordering-principle-natural-numbers</a>
<a id="6547" class="Keyword">open</a> <a id="6552" class="Keyword">import</a> <a id="6559" href="elementary-number-theory.well-ordering-principle-standard-finite-types.html" class="Module">elementary-number-theory.well-ordering-principle-standard-finite-types</a>
</pre>
## Finite group theory

<pre class="Agda"><a id="6667" class="Keyword">open</a> <a id="6672" class="Keyword">import</a> <a id="6679" href="finite-group-theory.html" class="Module">finite-group-theory</a>
<a id="6699" class="Keyword">open</a> <a id="6704" class="Keyword">import</a> <a id="6711" href="finite-group-theory.abstract-quaternion-group.html" class="Module">finite-group-theory.abstract-quaternion-group</a>
<a id="6757" class="Keyword">open</a> <a id="6762" class="Keyword">import</a> <a id="6769" href="finite-group-theory.concrete-quaternion-group.html" class="Module">finite-group-theory.concrete-quaternion-group</a>
<a id="6815" class="Keyword">open</a> <a id="6820" class="Keyword">import</a> <a id="6827" href="finite-group-theory.finite-groups.html" class="Module">finite-group-theory.finite-groups</a>
<a id="6861" class="Keyword">open</a> <a id="6866" class="Keyword">import</a> <a id="6873" href="finite-group-theory.finite-monoids.html" class="Module">finite-group-theory.finite-monoids</a>
<a id="6908" class="Keyword">open</a> <a id="6913" class="Keyword">import</a> <a id="6920" href="finite-group-theory.finite-semigroups.html" class="Module">finite-group-theory.finite-semigroups</a>
<a id="6958" class="Keyword">open</a> <a id="6963" class="Keyword">import</a> <a id="6970" href="finite-group-theory.groups-of-order-2.html" class="Module">finite-group-theory.groups-of-order-2</a>
<a id="7008" class="Keyword">open</a> <a id="7013" class="Keyword">import</a> <a id="7020" href="finite-group-theory.orbits-permutations.html" class="Module">finite-group-theory.orbits-permutations</a>
<a id="7060" class="Keyword">open</a> <a id="7065" class="Keyword">import</a> <a id="7072" href="finite-group-theory.permutations.html" class="Module">finite-group-theory.permutations</a>
<a id="7105" class="Keyword">open</a> <a id="7110" class="Keyword">import</a> <a id="7117" href="finite-group-theory.sign-homomorphism.html" class="Module">finite-group-theory.sign-homomorphism</a>
<a id="7155" class="Keyword">open</a> <a id="7160" class="Keyword">import</a> <a id="7167" href="finite-group-theory.transpositions.html" class="Module">finite-group-theory.transpositions</a>
</pre>
## Foundation

<pre class="Agda"><a id="7230" class="Keyword">open</a> <a id="7235" class="Keyword">import</a> <a id="7242" href="foundation.html" class="Module">foundation</a>
<a id="7253" class="Keyword">open</a> <a id="7258" class="Keyword">import</a> <a id="7265" href="foundation.0-maps.html" class="Module">foundation.0-maps</a>
<a id="7283" class="Keyword">open</a> <a id="7288" class="Keyword">import</a> <a id="7295" href="foundation.1-types.html" class="Module">foundation.1-types</a>
<a id="7314" class="Keyword">open</a> <a id="7319" class="Keyword">import</a> <a id="7326" href="foundation.2-types.html" class="Module">foundation.2-types</a>
<a id="7345" class="Keyword">open</a> <a id="7350" class="Keyword">import</a> <a id="7357" href="foundation.algebras-polynomial-endofunctors.html" class="Module">foundation.algebras-polynomial-endofunctors</a>
<a id="7401" class="Keyword">open</a> <a id="7406" class="Keyword">import</a> <a id="7413" href="foundation.automorphisms.html" class="Module">foundation.automorphisms</a>
<a id="7438" class="Keyword">open</a> <a id="7443" class="Keyword">import</a> <a id="7450" href="foundation.axiom-of-choice.html" class="Module">foundation.axiom-of-choice</a>
<a id="7477" class="Keyword">open</a> <a id="7482" class="Keyword">import</a> <a id="7489" href="foundation.binary-embeddings.html" class="Module">foundation.binary-embeddings</a>
<a id="7518" class="Keyword">open</a> <a id="7523" class="Keyword">import</a> <a id="7530" href="foundation.binary-equivalences.html" class="Module">foundation.binary-equivalences</a>
<a id="7561" class="Keyword">open</a> <a id="7566" class="Keyword">import</a> <a id="7573" href="foundation.binary-relations.html" class="Module">foundation.binary-relations</a>
<a id="7601" class="Keyword">open</a> <a id="7606" class="Keyword">import</a> <a id="7613" href="foundation.boolean-reflection.html" class="Module">foundation.boolean-reflection</a>
<a id="7643" class="Keyword">open</a> <a id="7648" class="Keyword">import</a> <a id="7655" href="foundation.booleans.html" class="Module">foundation.booleans</a>
<a id="7675" class="Keyword">open</a> <a id="7680" class="Keyword">import</a> <a id="7687" href="foundation.cantors-diagonal-argument.html" class="Module">foundation.cantors-diagonal-argument</a>
<a id="7724" class="Keyword">open</a> <a id="7729" class="Keyword">import</a> <a id="7736" href="foundation.cartesian-product-types.html" class="Module">foundation.cartesian-product-types</a>
<a id="7771" class="Keyword">open</a> <a id="7776" class="Keyword">import</a> <a id="7783" href="foundation.choice-of-representatives-equivalence-relation.html" class="Module">foundation.choice-of-representatives-equivalence-relation</a>
<a id="7841" class="Keyword">open</a> <a id="7846" class="Keyword">import</a> <a id="7853" href="foundation.coherently-invertible-maps.html" class="Module">foundation.coherently-invertible-maps</a>
<a id="7891" class="Keyword">open</a> <a id="7896" class="Keyword">import</a> <a id="7903" href="foundation.commuting-squares.html" class="Module">foundation.commuting-squares</a>
<a id="7932" class="Keyword">open</a> <a id="7937" class="Keyword">import</a> <a id="7944" href="foundation.complements.html" class="Module">foundation.complements</a>
<a id="7967" class="Keyword">open</a> <a id="7972" class="Keyword">import</a> <a id="7979" href="foundation.conjunction.html" class="Module">foundation.conjunction</a>
<a id="8002" class="Keyword">open</a> <a id="8007" class="Keyword">import</a> <a id="8014" href="foundation.connected-components-universes.html" class="Module">foundation.connected-components-universes</a>
<a id="8056" class="Keyword">open</a> <a id="8061" class="Keyword">import</a> <a id="8068" href="foundation.connected-components.html" class="Module">foundation.connected-components</a>
<a id="8100" class="Keyword">open</a> <a id="8105" class="Keyword">import</a> <a id="8112" href="foundation.connected-types.html" class="Module">foundation.connected-types</a>
<a id="8139" class="Keyword">open</a> <a id="8144" class="Keyword">import</a> <a id="8151" href="foundation.constant-maps.html" class="Module">foundation.constant-maps</a>
<a id="8176" class="Keyword">open</a> <a id="8181" class="Keyword">import</a> <a id="8188" href="foundation.contractible-maps.html" class="Module">foundation.contractible-maps</a>
<a id="8217" class="Keyword">open</a> <a id="8222" class="Keyword">import</a> <a id="8229" href="foundation.contractible-types.html" class="Module">foundation.contractible-types</a>
<a id="8259" class="Keyword">open</a> <a id="8264" class="Keyword">import</a> <a id="8271" href="foundation.coproduct-types.html" class="Module">foundation.coproduct-types</a>
<a id="8298" class="Keyword">open</a> <a id="8303" class="Keyword">import</a> <a id="8310" href="foundation.coslice.html" class="Module">foundation.coslice</a>
<a id="8329" class="Keyword">open</a> <a id="8334" class="Keyword">import</a> <a id="8341" href="foundation.decidable-dependent-function-types.html" class="Module">foundation.decidable-dependent-function-types</a>
<a id="8387" class="Keyword">open</a> <a id="8392" class="Keyword">import</a> <a id="8399" href="foundation.decidable-dependent-pair-types.html" class="Module">foundation.decidable-dependent-pair-types</a>
<a id="8441" class="Keyword">open</a> <a id="8446" class="Keyword">import</a> <a id="8453" href="foundation.decidable-embeddings.html" class="Module">foundation.decidable-embeddings</a>
<a id="8485" class="Keyword">open</a> <a id="8490" class="Keyword">import</a> <a id="8497" href="foundation.decidable-equality.html" class="Module">foundation.decidable-equality</a>
<a id="8527" class="Keyword">open</a> <a id="8532" class="Keyword">import</a> <a id="8539" href="foundation.decidable-maps.html" class="Module">foundation.decidable-maps</a>
<a id="8565" class="Keyword">open</a> <a id="8570" class="Keyword">import</a> <a id="8577" href="foundation.decidable-propositions.html" class="Module">foundation.decidable-propositions</a>
<a id="8611" class="Keyword">open</a> <a id="8616" class="Keyword">import</a> <a id="8623" href="foundation.decidable-subtypes.html" class="Module">foundation.decidable-subtypes</a>
<a id="8653" class="Keyword">open</a> <a id="8658" class="Keyword">import</a> <a id="8665" href="foundation.decidable-types.html" class="Module">foundation.decidable-types</a>
<a id="8692" class="Keyword">open</a> <a id="8697" class="Keyword">import</a> <a id="8704" href="foundation.dependent-pair-types.html" class="Module">foundation.dependent-pair-types</a>
<a id="8736" class="Keyword">open</a> <a id="8741" class="Keyword">import</a> <a id="8748" href="foundation.diagonal-maps-of-types.html" class="Module">foundation.diagonal-maps-of-types</a>
<a id="8782" class="Keyword">open</a> <a id="8787" class="Keyword">import</a> <a id="8794" href="foundation.disjunction.html" class="Module">foundation.disjunction</a>
<a id="8817" class="Keyword">open</a> <a id="8822" class="Keyword">import</a> <a id="8829" href="foundation.distributivity-of-dependent-functions-over-coproduct-types.html" class="Module">foundation.distributivity-of-dependent-functions-over-coproduct-types</a>
<a id="8899" class="Keyword">open</a> <a id="8904" class="Keyword">import</a> <a id="8911" href="foundation.distributivity-of-dependent-functions-over-dependent-pairs.html" class="Module">foundation.distributivity-of-dependent-functions-over-dependent-pairs</a>
<a id="8981" class="Keyword">open</a> <a id="8986" class="Keyword">import</a> <a id="8993" href="foundation.double-negation.html" class="Module">foundation.double-negation</a>
<a id="9020" class="Keyword">open</a> <a id="9025" class="Keyword">import</a> <a id="9032" href="foundation.dubuc-penon-compact-types.html" class="Module">foundation.dubuc-penon-compact-types</a>
<a id="9069" class="Keyword">open</a> <a id="9074" class="Keyword">import</a> <a id="9081" href="foundation.effective-maps-equivalence-relations.html" class="Module">foundation.effective-maps-equivalence-relations</a>
<a id="9129" class="Keyword">open</a> <a id="9134" class="Keyword">import</a> <a id="9141" href="foundation.elementhood-relation-w-types.html" class="Module">foundation.elementhood-relation-w-types</a>
<a id="9181" class="Keyword">open</a> <a id="9186" class="Keyword">import</a> <a id="9193" href="foundation.embeddings.html" class="Module">foundation.embeddings</a>
<a id="9215" class="Keyword">open</a> <a id="9220" class="Keyword">import</a> <a id="9227" href="foundation.empty-types.html" class="Module">foundation.empty-types</a>
<a id="9250" class="Keyword">open</a> <a id="9255" class="Keyword">import</a> <a id="9262" href="foundation.epimorphisms-with-respect-to-sets.html" class="Module">foundation.epimorphisms-with-respect-to-sets</a>
<a id="9307" class="Keyword">open</a> <a id="9312" class="Keyword">import</a> <a id="9319" href="foundation.equality-cartesian-product-types.html" class="Module">foundation.equality-cartesian-product-types</a>
<a id="9363" class="Keyword">open</a> <a id="9368" class="Keyword">import</a> <a id="9375" href="foundation.equality-coproduct-types.html" class="Module">foundation.equality-coproduct-types</a>
<a id="9411" class="Keyword">open</a> <a id="9416" class="Keyword">import</a> <a id="9423" href="foundation.equality-dependent-function-types.html" class="Module">foundation.equality-dependent-function-types</a>
<a id="9468" class="Keyword">open</a> <a id="9473" class="Keyword">import</a> <a id="9480" href="foundation.equality-dependent-pair-types.html" class="Module">foundation.equality-dependent-pair-types</a>
<a id="9521" class="Keyword">open</a> <a id="9526" class="Keyword">import</a> <a id="9533" href="foundation.equality-fibers-of-maps.html" class="Module">foundation.equality-fibers-of-maps</a>
<a id="9568" class="Keyword">open</a> <a id="9573" class="Keyword">import</a> <a id="9580" href="foundation.equivalence-classes.html" class="Module">foundation.equivalence-classes</a>
<a id="9611" class="Keyword">open</a> <a id="9616" class="Keyword">import</a> <a id="9623" href="foundation.equivalence-induction.html" class="Module">foundation.equivalence-induction</a>
<a id="9656" class="Keyword">open</a> <a id="9661" class="Keyword">import</a> <a id="9668" href="foundation.equivalence-relations.html" class="Module">foundation.equivalence-relations</a>
<a id="9701" class="Keyword">open</a> <a id="9706" class="Keyword">import</a> <a id="9713" href="foundation.equivalences-maybe.html" class="Module">foundation.equivalences-maybe</a>
<a id="9743" class="Keyword">open</a> <a id="9748" class="Keyword">import</a> <a id="9755" href="foundation.equivalences.html" class="Module">foundation.equivalences</a>
<a id="9779" class="Keyword">open</a> <a id="9784" class="Keyword">import</a> <a id="9791" href="foundation.existential-quantification.html" class="Module">foundation.existential-quantification</a>
<a id="9829" class="Keyword">open</a> <a id="9834" class="Keyword">import</a> <a id="9841" href="foundation.extensional-w-types.html" class="Module">foundation.extensional-w-types</a>
<a id="9872" class="Keyword">open</a> <a id="9877" class="Keyword">import</a> <a id="9884" href="foundation.faithful-maps.html" class="Module">foundation.faithful-maps</a>
<a id="9909" class="Keyword">open</a> <a id="9914" class="Keyword">import</a> <a id="9921" href="foundation.fiber-inclusions.html" class="Module">foundation.fiber-inclusions</a>
<a id="9949" class="Keyword">open</a> <a id="9954" class="Keyword">import</a> <a id="9961" href="foundation.fibered-maps.html" class="Module">foundation.fibered-maps</a>
<a id="9985" class="Keyword">open</a> <a id="9990" class="Keyword">import</a> <a id="9997" href="foundation.fibers-of-maps.html" class="Module">foundation.fibers-of-maps</a>
<a id="10023" class="Keyword">open</a> <a id="10028" class="Keyword">import</a> <a id="10035" href="foundation.function-extensionality.html" class="Module">foundation.function-extensionality</a>
<a id="10070" class="Keyword">open</a> <a id="10075" class="Keyword">import</a> <a id="10082" href="foundation.functions.html" class="Module">foundation.functions</a>
<a id="10103" class="Keyword">open</a> <a id="10108" class="Keyword">import</a> <a id="10115" href="foundation.functoriality-cartesian-product-types.html" class="Module">foundation.functoriality-cartesian-product-types</a>
<a id="10164" class="Keyword">open</a> <a id="10169" class="Keyword">import</a> <a id="10176" href="foundation.functoriality-coproduct-types.html" class="Module">foundation.functoriality-coproduct-types</a>
<a id="10217" class="Keyword">open</a> <a id="10222" class="Keyword">import</a> <a id="10229" href="foundation.functoriality-dependent-function-types.html" class="Module">foundation.functoriality-dependent-function-types</a>
<a id="10279" class="Keyword">open</a> <a id="10284" class="Keyword">import</a> <a id="10291" href="foundation.functoriality-dependent-pair-types.html" class="Module">foundation.functoriality-dependent-pair-types</a>
<a id="10337" class="Keyword">open</a> <a id="10342" class="Keyword">import</a> <a id="10349" href="foundation.functoriality-function-types.html" class="Module">foundation.functoriality-function-types</a>
<a id="10389" class="Keyword">open</a> <a id="10394" class="Keyword">import</a> <a id="10401" href="foundation.functoriality-propositional-truncation.html" class="Module">foundation.functoriality-propositional-truncation</a>
<a id="10451" class="Keyword">open</a> <a id="10456" class="Keyword">import</a> <a id="10463" href="foundation.functoriality-set-quotients.html" class="Module">foundation.functoriality-set-quotients</a>
<a id="10502" class="Keyword">open</a> <a id="10507" class="Keyword">import</a> <a id="10514" href="foundation.functoriality-set-truncation.html" class="Module">foundation.functoriality-set-truncation</a>
<a id="10554" class="Keyword">open</a> <a id="10559" class="Keyword">import</a> <a id="10566" href="foundation.functoriality-w-types.html" class="Module">foundation.functoriality-w-types</a>
<a id="10599" class="Keyword">open</a> <a id="10604" class="Keyword">import</a> <a id="10611" href="foundation.fundamental-theorem-of-identity-types.html" class="Module">foundation.fundamental-theorem-of-identity-types</a>
<a id="10660" class="Keyword">open</a> <a id="10665" class="Keyword">import</a> <a id="10672" href="foundation.global-choice.html" class="Module">foundation.global-choice</a>
<a id="10697" class="Keyword">open</a> <a id="10702" class="Keyword">import</a> <a id="10709" href="foundation.hilberts-epsilon-operators.html" class="Module">foundation.hilberts-epsilon-operators</a>
<a id="10747" class="Keyword">open</a> <a id="10752" class="Keyword">import</a> <a id="10759" href="foundation.homotopies.html" class="Module">foundation.homotopies</a>
<a id="10781" class="Keyword">open</a> <a id="10786" class="Keyword">import</a> <a id="10793" href="foundation.identity-systems.html" class="Module">foundation.identity-systems</a>
<a id="10821" class="Keyword">open</a> <a id="10826" class="Keyword">import</a> <a id="10833" href="foundation.identity-types.html" class="Module">foundation.identity-types</a>
<a id="10859" class="Keyword">open</a> <a id="10864" class="Keyword">import</a> <a id="10871" href="foundation.images.html" class="Module">foundation.images</a>
<a id="10889" class="Keyword">open</a> <a id="10894" class="Keyword">import</a> <a id="10901" href="foundation.impredicative-encodings.html" class="Module">foundation.impredicative-encodings</a>
<a id="10936" class="Keyword">open</a> <a id="10941" class="Keyword">import</a> <a id="10948" href="foundation.indexed-w-types.html" class="Module">foundation.indexed-w-types</a>
<a id="10975" class="Keyword">open</a> <a id="10980" class="Keyword">import</a> <a id="10987" href="foundation.induction-principle-propositional-truncation.html" class="Module">foundation.induction-principle-propositional-truncation</a>
<a id="11043" class="Keyword">open</a> <a id="11048" class="Keyword">import</a> <a id="11055" href="foundation.induction-w-types.html" class="Module">foundation.induction-w-types</a>
<a id="11084" class="Keyword">open</a> <a id="11089" class="Keyword">import</a> <a id="11096" href="foundation.inequality-w-types.html" class="Module">foundation.inequality-w-types</a>
<a id="11126" class="Keyword">open</a> <a id="11131" class="Keyword">import</a> <a id="11138" href="foundation.injective-maps.html" class="Module">foundation.injective-maps</a>
<a id="11164" class="Keyword">open</a> <a id="11169" class="Keyword">import</a> <a id="11176" href="foundation.interchange-law.html" class="Module">foundation.interchange-law</a>
<a id="11203" class="Keyword">open</a> <a id="11208" class="Keyword">import</a> <a id="11215" href="foundation.involutions.html" class="Module">foundation.involutions</a>
<a id="11238" class="Keyword">open</a> <a id="11243" class="Keyword">import</a> <a id="11250" href="foundation.isolated-points.html" class="Module">foundation.isolated-points</a>
<a id="11277" class="Keyword">open</a> <a id="11282" class="Keyword">import</a> <a id="11289" href="foundation.isomorphisms-of-sets.html" class="Module">foundation.isomorphisms-of-sets</a>
<a id="11321" class="Keyword">open</a> <a id="11326" class="Keyword">import</a> <a id="11333" href="foundation.law-of-excluded-middle.html" class="Module">foundation.law-of-excluded-middle</a>
<a id="11367" class="Keyword">open</a> <a id="11372" class="Keyword">import</a> <a id="11379" href="foundation.lawveres-fixed-point-theorem.html" class="Module">foundation.lawveres-fixed-point-theorem</a>
<a id="11419" class="Keyword">open</a> <a id="11424" class="Keyword">import</a> <a id="11431" href="foundation.locally-small-types.html" class="Module">foundation.locally-small-types</a>
<a id="11462" class="Keyword">open</a> <a id="11467" class="Keyword">import</a> <a id="11474" href="foundation.logical-equivalences.html" class="Module">foundation.logical-equivalences</a>
<a id="11506" class="Keyword">open</a> <a id="11511" class="Keyword">import</a> <a id="11518" href="foundation.lower-types-w-types.html" class="Module">foundation.lower-types-w-types</a>
<a id="11549" class="Keyword">open</a> <a id="11554" class="Keyword">import</a> <a id="11561" href="foundation.maybe.html" class="Module">foundation.maybe</a>
<a id="11578" class="Keyword">open</a> <a id="11583" class="Keyword">import</a> <a id="11590" href="foundation.mere-equality.html" class="Module">foundation.mere-equality</a>
<a id="11615" class="Keyword">open</a> <a id="11620" class="Keyword">import</a> <a id="11627" href="foundation.mere-equivalences.html" class="Module">foundation.mere-equivalences</a>
<a id="11656" class="Keyword">open</a> <a id="11661" class="Keyword">import</a> <a id="11668" href="foundation.monomorphisms.html" class="Module">foundation.monomorphisms</a>
<a id="11693" class="Keyword">open</a> <a id="11698" class="Keyword">import</a> <a id="11705" href="foundation.multisets.html" class="Module">foundation.multisets</a>
<a id="11726" class="Keyword">open</a> <a id="11731" class="Keyword">import</a> <a id="11738" href="foundation.negation.html" class="Module">foundation.negation</a>
<a id="11758" class="Keyword">open</a> <a id="11763" class="Keyword">import</a> <a id="11770" href="foundation.non-contractible-types.html" class="Module">foundation.non-contractible-types</a>
<a id="11804" class="Keyword">open</a> <a id="11809" class="Keyword">import</a> <a id="11816" href="foundation.pairs-of-distinct-elements.html" class="Module">foundation.pairs-of-distinct-elements</a>
<a id="11854" class="Keyword">open</a> <a id="11859" class="Keyword">import</a> <a id="11866" href="foundation.path-algebra.html" class="Module">foundation.path-algebra</a>
<a id="11890" class="Keyword">open</a> <a id="11895" class="Keyword">import</a> <a id="11902" href="foundation.path-split-maps.html" class="Module">foundation.path-split-maps</a>
<a id="11929" class="Keyword">open</a> <a id="11934" class="Keyword">import</a> <a id="11941" href="foundation.polynomial-endofunctors.html" class="Module">foundation.polynomial-endofunctors</a>
<a id="11976" class="Keyword">open</a> <a id="11981" class="Keyword">import</a> <a id="11988" href="foundation.principle-of-omniscience.html" class="Module">foundation.principle-of-omniscience</a>
<a id="12024" class="Keyword">open</a> <a id="12029" class="Keyword">import</a> <a id="12036" href="foundation.propositional-extensionality.html" class="Module">foundation.propositional-extensionality</a>
<a id="12076" class="Keyword">open</a> <a id="12081" class="Keyword">import</a> <a id="12088" href="foundation.propositional-maps.html" class="Module">foundation.propositional-maps</a>
<a id="12118" class="Keyword">open</a> <a id="12123" class="Keyword">import</a> <a id="12130" href="foundation.propositional-truncations.html" class="Module">foundation.propositional-truncations</a>
<a id="12167" class="Keyword">open</a> <a id="12172" class="Keyword">import</a> <a id="12179" href="foundation.propositions.html" class="Module">foundation.propositions</a>
<a id="12203" class="Keyword">open</a> <a id="12208" class="Keyword">import</a> <a id="12215" href="foundation.pullbacks.html" class="Module">foundation.pullbacks</a>
<a id="12236" class="Keyword">open</a> <a id="12241" class="Keyword">import</a> <a id="12248" href="foundation.raising-universe-levels.html" class="Module">foundation.raising-universe-levels</a>
<a id="12283" class="Keyword">open</a> <a id="12288" class="Keyword">import</a> <a id="12295" href="foundation.ranks-of-elements-w-types.html" class="Module">foundation.ranks-of-elements-w-types</a>
<a id="12332" class="Keyword">open</a> <a id="12337" class="Keyword">import</a> <a id="12344" href="foundation.reflecting-maps-equivalence-relations.html" class="Module">foundation.reflecting-maps-equivalence-relations</a>
<a id="12393" class="Keyword">open</a> <a id="12398" class="Keyword">import</a> <a id="12405" href="foundation.replacement.html" class="Module">foundation.replacement</a>
<a id="12428" class="Keyword">open</a> <a id="12433" class="Keyword">import</a> <a id="12440" href="foundation.retractions.html" class="Module">foundation.retractions</a>
<a id="12463" class="Keyword">open</a> <a id="12468" class="Keyword">import</a> <a id="12475" href="foundation.russells-paradox.html" class="Module">foundation.russells-paradox</a>
<a id="12503" class="Keyword">open</a> <a id="12508" class="Keyword">import</a> <a id="12515" href="foundation.sections.html" class="Module">foundation.sections</a>
<a id="12535" class="Keyword">open</a> <a id="12540" class="Keyword">import</a> <a id="12547" href="foundation.set-presented-types.html" class="Module">foundation.set-presented-types</a>
<a id="12578" class="Keyword">open</a> <a id="12583" class="Keyword">import</a> <a id="12590" href="foundation.set-truncations.html" class="Module">foundation.set-truncations</a>
<a id="12617" class="Keyword">open</a> <a id="12622" class="Keyword">import</a> <a id="12629" href="foundation.sets.html" class="Module">foundation.sets</a>
<a id="12645" class="Keyword">open</a> <a id="12650" class="Keyword">import</a> <a id="12657" href="foundation.singleton-induction.html" class="Module">foundation.singleton-induction</a>
<a id="12688" class="Keyword">open</a> <a id="12693" class="Keyword">import</a> <a id="12700" href="foundation.slice.html" class="Module">foundation.slice</a>
<a id="12717" class="Keyword">open</a> <a id="12722" class="Keyword">import</a> <a id="12729" href="foundation.small-maps.html" class="Module">foundation.small-maps</a>
<a id="12751" class="Keyword">open</a> <a id="12756" class="Keyword">import</a> <a id="12763" href="foundation.small-multisets.html" class="Module">foundation.small-multisets</a>
<a id="12790" class="Keyword">open</a> <a id="12795" class="Keyword">import</a> <a id="12802" href="foundation.small-types.html" class="Module">foundation.small-types</a>
<a id="12825" class="Keyword">open</a> <a id="12830" class="Keyword">import</a> <a id="12837" href="foundation.small-universes.html" class="Module">foundation.small-universes</a>
<a id="12864" class="Keyword">open</a> <a id="12869" class="Keyword">import</a> <a id="12876" href="foundation.split-surjective-maps.html" class="Module">foundation.split-surjective-maps</a>
<a id="12909" class="Keyword">open</a> <a id="12914" class="Keyword">import</a> <a id="12921" href="foundation.structure-identity-principle.html" class="Module">foundation.structure-identity-principle</a>
<a id="12961" class="Keyword">open</a> <a id="12966" class="Keyword">import</a> <a id="12973" href="foundation.structure.html" class="Module">foundation.structure</a>
<a id="12994" class="Keyword">open</a> <a id="12999" class="Keyword">import</a> <a id="13006" href="foundation.subterminal-types.html" class="Module">foundation.subterminal-types</a>
<a id="13035" class="Keyword">open</a> <a id="13040" class="Keyword">import</a> <a id="13047" href="foundation.subtype-identity-principle.html" class="Module">foundation.subtype-identity-principle</a>
<a id="13085" class="Keyword">open</a> <a id="13090" class="Keyword">import</a> <a id="13097" href="foundation.subtypes.html" class="Module">foundation.subtypes</a>
<a id="13117" class="Keyword">open</a> <a id="13122" class="Keyword">import</a> <a id="13129" href="foundation.subuniverses.html" class="Module">foundation.subuniverses</a>
<a id="13153" class="Keyword">open</a> <a id="13158" class="Keyword">import</a> <a id="13165" href="foundation.surjective-maps.html" class="Module">foundation.surjective-maps</a>
<a id="13192" class="Keyword">open</a> <a id="13197" class="Keyword">import</a> <a id="13204" href="foundation.truncated-equality.html" class="Module">foundation.truncated-equality</a>
<a id="13234" class="Keyword">open</a> <a id="13239" class="Keyword">import</a> <a id="13246" href="foundation.truncated-maps.html" class="Module">foundation.truncated-maps</a>
<a id="13272" class="Keyword">open</a> <a id="13277" class="Keyword">import</a> <a id="13284" href="foundation.truncated-types.html" class="Module">foundation.truncated-types</a>
<a id="13311" class="Keyword">open</a> <a id="13316" class="Keyword">import</a> <a id="13323" href="foundation.truncation-levels.html" class="Module">foundation.truncation-levels</a>
<a id="13352" class="Keyword">open</a> <a id="13357" class="Keyword">import</a> <a id="13364" href="foundation.truncations.html" class="Module">foundation.truncations</a>
<a id="13387" class="Keyword">open</a> <a id="13392" class="Keyword">import</a> <a id="13399" href="foundation.type-arithmetic-cartesian-product-types.html" class="Module">foundation.type-arithmetic-cartesian-product-types</a>
<a id="13450" class="Keyword">open</a> <a id="13455" class="Keyword">import</a> <a id="13462" href="foundation.type-arithmetic-coproduct-types.html" class="Module">foundation.type-arithmetic-coproduct-types</a>
<a id="13505" class="Keyword">open</a> <a id="13510" class="Keyword">import</a> <a id="13517" href="foundation.type-arithmetic-dependent-pair-types.html" class="Module">foundation.type-arithmetic-dependent-pair-types</a>
<a id="13565" class="Keyword">open</a> <a id="13570" class="Keyword">import</a> <a id="13577" href="foundation.type-arithmetic-empty-type.html" class="Module">foundation.type-arithmetic-empty-type</a>
<a id="13615" class="Keyword">open</a> <a id="13620" class="Keyword">import</a> <a id="13627" href="foundation.type-arithmetic-unit-type.html" class="Module">foundation.type-arithmetic-unit-type</a>
<a id="13664" class="Keyword">open</a> <a id="13669" class="Keyword">import</a> <a id="13676" href="foundation.uniqueness-image.html" class="Module">foundation.uniqueness-image</a>
<a id="13704" class="Keyword">open</a> <a id="13709" class="Keyword">import</a> <a id="13716" href="foundation.uniqueness-set-quotients.html" class="Module">foundation.uniqueness-set-quotients</a>
<a id="13752" class="Keyword">open</a> <a id="13757" class="Keyword">import</a> <a id="13764" href="foundation.uniqueness-set-truncations.html" class="Module">foundation.uniqueness-set-truncations</a>
<a id="13802" class="Keyword">open</a> <a id="13807" class="Keyword">import</a> <a id="13814" href="foundation.uniqueness-truncation.html" class="Module">foundation.uniqueness-truncation</a>
<a id="13847" class="Keyword">open</a> <a id="13852" class="Keyword">import</a> <a id="13859" href="foundation.unit-type.html" class="Module">foundation.unit-type</a>
<a id="13880" class="Keyword">open</a> <a id="13885" class="Keyword">import</a> <a id="13892" href="foundation.univalence-implies-function-extensionality.html" class="Module">foundation.univalence-implies-function-extensionality</a>
<a id="13946" class="Keyword">open</a> <a id="13951" class="Keyword">import</a> <a id="13958" href="foundation.univalence.html" class="Module">foundation.univalence</a>
<a id="13980" class="Keyword">open</a> <a id="13985" class="Keyword">import</a> <a id="13992" href="foundation.univalent-type-families.html" class="Module">foundation.univalent-type-families</a>
<a id="14027" class="Keyword">open</a> <a id="14032" class="Keyword">import</a> <a id="14039" href="foundation.universal-multiset.html" class="Module">foundation.universal-multiset</a>
<a id="14069" class="Keyword">open</a> <a id="14074" class="Keyword">import</a> <a id="14081" href="foundation.universal-property-booleans.html" class="Module">foundation.universal-property-booleans</a>
<a id="14120" class="Keyword">open</a> <a id="14125" class="Keyword">import</a> <a id="14132" href="foundation.universal-property-cartesian-product-types.html" class="Module">foundation.universal-property-cartesian-product-types</a>
<a id="14186" class="Keyword">open</a> <a id="14191" class="Keyword">import</a> <a id="14198" href="foundation.universal-property-coproduct-types.html" class="Module">foundation.universal-property-coproduct-types</a>
<a id="14244" class="Keyword">open</a> <a id="14249" class="Keyword">import</a> <a id="14256" href="foundation.universal-property-dependent-pair-types.html" class="Module">foundation.universal-property-dependent-pair-types</a>
<a id="14307" class="Keyword">open</a> <a id="14312" class="Keyword">import</a> <a id="14319" href="foundation.universal-property-empty-type.html" class="Module">foundation.universal-property-empty-type</a>
<a id="14360" class="Keyword">open</a> <a id="14365" class="Keyword">import</a> <a id="14372" href="foundation.universal-property-fiber-products.html" class="Module">foundation.universal-property-fiber-products</a>
<a id="14417" class="Keyword">open</a> <a id="14422" class="Keyword">import</a> <a id="14429" href="foundation.universal-property-identity-types.html" class="Module">foundation.universal-property-identity-types</a>
<a id="14474" class="Keyword">open</a> <a id="14479" class="Keyword">import</a> <a id="14486" href="foundation.universal-property-image.html" class="Module">foundation.universal-property-image</a>
<a id="14522" class="Keyword">open</a> <a id="14527" class="Keyword">import</a> <a id="14534" href="foundation.universal-property-maybe.html" class="Module">foundation.universal-property-maybe</a>
<a id="14570" class="Keyword">open</a> <a id="14575" class="Keyword">import</a> <a id="14582" href="foundation.universal-property-propositional-truncation-into-sets.html" class="Module">foundation.universal-property-propositional-truncation-into-sets</a>
<a id="14647" class="Keyword">open</a> <a id="14652" class="Keyword">import</a> <a id="14659" href="foundation.universal-property-propositional-truncation.html" class="Module">foundation.universal-property-propositional-truncation</a>
<a id="14714" class="Keyword">open</a> <a id="14719" class="Keyword">import</a> <a id="14726" href="foundation.universal-property-pullbacks.html" class="Module">foundation.universal-property-pullbacks</a>
<a id="14766" class="Keyword">open</a> <a id="14771" class="Keyword">import</a> <a id="14778" href="foundation.universal-property-set-quotients.html" class="Module">foundation.universal-property-set-quotients</a>
<a id="14822" class="Keyword">open</a> <a id="14827" class="Keyword">import</a> <a id="14834" href="foundation.universal-property-set-truncation.html" class="Module">foundation.universal-property-set-truncation</a>
<a id="14879" class="Keyword">open</a> <a id="14884" class="Keyword">import</a> <a id="14891" href="foundation.universal-property-truncation.html" class="Module">foundation.universal-property-truncation</a>
<a id="14932" class="Keyword">open</a> <a id="14937" class="Keyword">import</a> <a id="14944" href="foundation.universal-property-unit-type.html" class="Module">foundation.universal-property-unit-type</a>
<a id="14984" class="Keyword">open</a> <a id="14989" class="Keyword">import</a> <a id="14996" href="foundation.universe-levels.html" class="Module">foundation.universe-levels</a>
<a id="15023" class="Keyword">open</a> <a id="15028" class="Keyword">import</a> <a id="15035" href="foundation.unordered-pairs.html" class="Module">foundation.unordered-pairs</a>
<a id="15062" class="Keyword">open</a> <a id="15067" class="Keyword">import</a> <a id="15074" href="foundation.w-types.html" class="Module">foundation.w-types</a>
<a id="15093" class="Keyword">open</a> <a id="15098" class="Keyword">import</a> <a id="15105" href="foundation.weak-function-extensionality.html" class="Module">foundation.weak-function-extensionality</a>
<a id="15145" class="Keyword">open</a> <a id="15150" class="Keyword">import</a> <a id="15157" href="foundation.weakly-constant-maps.html" class="Module">foundation.weakly-constant-maps</a>
</pre>
## Foundation Core

<pre class="Agda"><a id="15222" class="Keyword">open</a> <a id="15227" class="Keyword">import</a> <a id="15234" href="foundation-core.0-maps.html" class="Module">foundation-core.0-maps</a>
<a id="15257" class="Keyword">open</a> <a id="15262" class="Keyword">import</a> <a id="15269" href="foundation-core.1-types.html" class="Module">foundation-core.1-types</a>
<a id="15293" class="Keyword">open</a> <a id="15298" class="Keyword">import</a> <a id="15305" href="foundation-core.cartesian-product-types.html" class="Module">foundation-core.cartesian-product-types</a>
<a id="15345" class="Keyword">open</a> <a id="15350" class="Keyword">import</a> <a id="15357" href="foundation-core.coherently-invertible-maps.html" class="Module">foundation-core.coherently-invertible-maps</a>
<a id="15400" class="Keyword">open</a> <a id="15405" class="Keyword">import</a> <a id="15412" href="foundation-core.commuting-squares.html" class="Module">foundation-core.commuting-squares</a>
<a id="15446" class="Keyword">open</a> <a id="15451" class="Keyword">import</a> <a id="15458" href="foundation-core.constant-maps.html" class="Module">foundation-core.constant-maps</a>
<a id="15488" class="Keyword">open</a> <a id="15493" class="Keyword">import</a> <a id="15500" href="foundation-core.contractible-maps.html" class="Module">foundation-core.contractible-maps</a>
<a id="15534" class="Keyword">open</a> <a id="15539" class="Keyword">import</a> <a id="15546" href="foundation-core.contractible-types.html" class="Module">foundation-core.contractible-types</a>
<a id="15581" class="Keyword">open</a> <a id="15586" class="Keyword">import</a> <a id="15593" href="foundation-core.dependent-pair-types.html" class="Module">foundation-core.dependent-pair-types</a>
<a id="15630" class="Keyword">open</a> <a id="15635" class="Keyword">import</a> <a id="15642" href="foundation-core.embeddings.html" class="Module">foundation-core.embeddings</a>
<a id="15669" class="Keyword">open</a> <a id="15674" class="Keyword">import</a> <a id="15681" href="foundation-core.empty-types.html" class="Module">foundation-core.empty-types</a>
<a id="15709" class="Keyword">open</a> <a id="15714" class="Keyword">import</a> <a id="15721" href="foundation-core.equality-cartesian-product-types.html" class="Module">foundation-core.equality-cartesian-product-types</a>
<a id="15770" class="Keyword">open</a> <a id="15775" class="Keyword">import</a> <a id="15782" href="foundation-core.equality-dependent-pair-types.html" class="Module">foundation-core.equality-dependent-pair-types</a>
<a id="15828" class="Keyword">open</a> <a id="15833" class="Keyword">import</a> <a id="15840" href="foundation-core.equality-fibers-of-maps.html" class="Module">foundation-core.equality-fibers-of-maps</a>
<a id="15880" class="Keyword">open</a> <a id="15885" class="Keyword">import</a> <a id="15892" href="foundation-core.equivalence-induction.html" class="Module">foundation-core.equivalence-induction</a>
<a id="15930" class="Keyword">open</a> <a id="15935" class="Keyword">import</a> <a id="15942" href="foundation-core.equivalences.html" class="Module">foundation-core.equivalences</a>
<a id="15971" class="Keyword">open</a> <a id="15976" class="Keyword">import</a> <a id="15983" href="foundation-core.faithful-maps.html" class="Module">foundation-core.faithful-maps</a>
<a id="16013" class="Keyword">open</a> <a id="16018" class="Keyword">import</a> <a id="16025" href="foundation-core.fibers-of-maps.html" class="Module">foundation-core.fibers-of-maps</a>
<a id="16056" class="Keyword">open</a> <a id="16061" class="Keyword">import</a> <a id="16068" href="foundation-core.functions.html" class="Module">foundation-core.functions</a>
<a id="16094" class="Keyword">open</a> <a id="16099" class="Keyword">import</a> <a id="16106" href="foundation-core.functoriality-dependent-pair-types.html" class="Module">foundation-core.functoriality-dependent-pair-types</a>
<a id="16157" class="Keyword">open</a> <a id="16162" class="Keyword">import</a> <a id="16169" href="foundation-core.fundamental-theorem-of-identity-types.html" class="Module">foundation-core.fundamental-theorem-of-identity-types</a>
<a id="16223" class="Keyword">open</a> <a id="16228" class="Keyword">import</a> <a id="16235" href="foundation-core.homotopies.html" class="Module">foundation-core.homotopies</a>
<a id="16262" class="Keyword">open</a> <a id="16267" class="Keyword">import</a> <a id="16274" href="foundation-core.identity-systems.html" class="Module">foundation-core.identity-systems</a>
<a id="16307" class="Keyword">open</a> <a id="16312" class="Keyword">import</a> <a id="16319" href="foundation-core.identity-types.html" class="Module">foundation-core.identity-types</a>
<a id="16350" class="Keyword">open</a> <a id="16355" class="Keyword">import</a> <a id="16362" href="foundation-core.logical-equivalences.html" class="Module">foundation-core.logical-equivalences</a>
<a id="16399" class="Keyword">open</a> <a id="16404" class="Keyword">import</a> <a id="16411" href="foundation-core.negation.html" class="Module">foundation-core.negation</a>
<a id="16436" class="Keyword">open</a> <a id="16441" class="Keyword">import</a> <a id="16448" href="foundation-core.path-split-maps.html" class="Module">foundation-core.path-split-maps</a>
<a id="16480" class="Keyword">open</a> <a id="16485" class="Keyword">import</a> <a id="16492" href="foundation-core.propositional-maps.html" class="Module">foundation-core.propositional-maps</a>
<a id="16527" class="Keyword">open</a> <a id="16532" class="Keyword">import</a> <a id="16539" href="foundation-core.propositions.html" class="Module">foundation-core.propositions</a>
<a id="16568" class="Keyword">open</a> <a id="16573" class="Keyword">import</a> <a id="16580" href="foundation-core.retractions.html" class="Module">foundation-core.retractions</a>
<a id="16608" class="Keyword">open</a> <a id="16613" class="Keyword">import</a> <a id="16620" href="foundation-core.sections.html" class="Module">foundation-core.sections</a>
<a id="16645" class="Keyword">open</a> <a id="16650" class="Keyword">import</a> <a id="16657" href="foundation-core.sets.html" class="Module">foundation-core.sets</a>
<a id="16678" class="Keyword">open</a> <a id="16683" class="Keyword">import</a> <a id="16690" href="foundation-core.singleton-induction.html" class="Module">foundation-core.singleton-induction</a>
<a id="16726" class="Keyword">open</a> <a id="16731" class="Keyword">import</a> <a id="16738" href="foundation-core.subtype-identity-principle.html" class="Module">foundation-core.subtype-identity-principle</a>
<a id="16781" class="Keyword">open</a> <a id="16786" class="Keyword">import</a> <a id="16793" href="foundation-core.subtypes.html" class="Module">foundation-core.subtypes</a>
<a id="16818" class="Keyword">open</a> <a id="16823" class="Keyword">import</a> <a id="16830" href="foundation-core.truncated-maps.html" class="Module">foundation-core.truncated-maps</a>
<a id="16861" class="Keyword">open</a> <a id="16866" class="Keyword">import</a> <a id="16873" href="foundation-core.truncated-types.html" class="Module">foundation-core.truncated-types</a>
<a id="16905" class="Keyword">open</a> <a id="16910" class="Keyword">import</a> <a id="16917" href="foundation-core.truncation-levels.html" class="Module">foundation-core.truncation-levels</a>
<a id="16951" class="Keyword">open</a> <a id="16956" class="Keyword">import</a> <a id="16963" href="foundation-core.type-arithmetic-cartesian-product-types.html" class="Module">foundation-core.type-arithmetic-cartesian-product-types</a>
<a id="17019" class="Keyword">open</a> <a id="17024" class="Keyword">import</a> <a id="17031" href="foundation-core.type-arithmetic-dependent-pair-types.html" class="Module">foundation-core.type-arithmetic-dependent-pair-types</a>
<a id="17084" class="Keyword">open</a> <a id="17089" class="Keyword">import</a> <a id="17096" href="foundation-core.univalence.html" class="Module">foundation-core.univalence</a>
<a id="17123" class="Keyword">open</a> <a id="17128" class="Keyword">import</a> <a id="17135" href="foundation-core.universe-levels.html" class="Module">foundation-core.universe-levels</a>
</pre>
## Graph theory

<pre class="Agda"><a id="17197" class="Keyword">open</a> <a id="17202" class="Keyword">import</a> <a id="17209" href="graph-theory.html" class="Module">graph-theory</a>
<a id="17222" class="Keyword">open</a> <a id="17227" class="Keyword">import</a> <a id="17234" href="graph-theory.connected-undirected-graphs.html" class="Module">graph-theory.connected-undirected-graphs</a>
<a id="17275" class="Keyword">open</a> <a id="17280" class="Keyword">import</a> <a id="17287" href="graph-theory.directed-graphs.html" class="Module">graph-theory.directed-graphs</a>
<a id="17316" class="Keyword">open</a> <a id="17321" class="Keyword">import</a> <a id="17328" href="graph-theory.edge-coloured-undirected-graphs.html" class="Module">graph-theory.edge-coloured-undirected-graphs</a>
<a id="17373" class="Keyword">open</a> <a id="17378" class="Keyword">import</a> <a id="17385" href="graph-theory.equivalences-undirected-graphs.html" class="Module">graph-theory.equivalences-undirected-graphs</a>
<a id="17429" class="Keyword">open</a> <a id="17434" class="Keyword">import</a> <a id="17441" href="graph-theory.finite-graphs.html" class="Module">graph-theory.finite-graphs</a>
<a id="17468" class="Keyword">open</a> <a id="17473" class="Keyword">import</a> <a id="17480" href="graph-theory.incidence-undirected-graphs.html" class="Module">graph-theory.incidence-undirected-graphs</a>
<a id="17521" class="Keyword">open</a> <a id="17526" class="Keyword">import</a> <a id="17533" href="graph-theory.matchings.html" class="Module">graph-theory.matchings</a>
<a id="17556" class="Keyword">open</a> <a id="17561" class="Keyword">import</a> <a id="17568" href="graph-theory.mere-equivalences-undirected-graphs.html" class="Module">graph-theory.mere-equivalences-undirected-graphs</a>
<a id="17617" class="Keyword">open</a> <a id="17622" class="Keyword">import</a> <a id="17629" href="graph-theory.morphisms-directed-graphs.html" class="Module">graph-theory.morphisms-directed-graphs</a>
<a id="17668" class="Keyword">open</a> <a id="17673" class="Keyword">import</a> <a id="17680" href="graph-theory.morphisms-undirected-graphs.html" class="Module">graph-theory.morphisms-undirected-graphs</a>
<a id="17721" class="Keyword">open</a> <a id="17726" class="Keyword">import</a> <a id="17733" href="graph-theory.orientations-undirected-graphs.html" class="Module">graph-theory.orientations-undirected-graphs</a>
<a id="17777" class="Keyword">open</a> <a id="17782" class="Keyword">import</a> <a id="17789" href="graph-theory.paths-undirected-graphs.html" class="Module">graph-theory.paths-undirected-graphs</a>
<a id="17826" class="Keyword">open</a> <a id="17831" class="Keyword">import</a> <a id="17838" href="graph-theory.polygons.html" class="Module">graph-theory.polygons</a>
<a id="17860" class="Keyword">open</a> <a id="17865" class="Keyword">import</a> <a id="17872" href="graph-theory.reflexive-graphs.html" class="Module">graph-theory.reflexive-graphs</a>
<a id="17902" class="Keyword">open</a> <a id="17907" class="Keyword">import</a> <a id="17914" href="graph-theory.regular-undirected-graphs.html" class="Module">graph-theory.regular-undirected-graphs</a>
<a id="17953" class="Keyword">open</a> <a id="17958" class="Keyword">import</a> <a id="17965" href="graph-theory.simple-undirected-graphs.html" class="Module">graph-theory.simple-undirected-graphs</a>
<a id="18003" class="Keyword">open</a> <a id="18008" class="Keyword">import</a> <a id="18015" href="graph-theory.undirected-graphs.html" class="Module">graph-theory.undirected-graphs</a>
<a id="18046" class="Keyword">open</a> <a id="18051" class="Keyword">import</a> <a id="18058" href="graph-theory.voltage-graphs.html" class="Module">graph-theory.voltage-graphs</a>
</pre>
## Group theory

<pre class="Agda"><a id="18116" class="Keyword">open</a> <a id="18121" class="Keyword">import</a> <a id="18128" href="group-theory.html" class="Module">group-theory</a>
<a id="18141" class="Keyword">open</a> <a id="18146" class="Keyword">import</a> <a id="18153" href="group-theory.abelian-groups.html" class="Module">group-theory.abelian-groups</a>
<a id="18181" class="Keyword">open</a> <a id="18186" class="Keyword">import</a> <a id="18193" href="group-theory.abelian-subgroups.html" class="Module">group-theory.abelian-subgroups</a>
<a id="18224" class="Keyword">open</a> <a id="18229" class="Keyword">import</a> <a id="18236" href="group-theory.abstract-group-torsors.html" class="Module">group-theory.abstract-group-torsors</a>
<a id="18272" class="Keyword">open</a> <a id="18277" class="Keyword">import</a> <a id="18284" href="group-theory.addition-homomorphisms-abelian-groups.html" class="Module">group-theory.addition-homomorphisms-abelian-groups</a>
<a id="18335" class="Keyword">open</a> <a id="18340" class="Keyword">import</a> <a id="18347" href="group-theory.category-of-groups.html" class="Module">group-theory.category-of-groups</a>
<a id="18379" class="Keyword">open</a> <a id="18384" class="Keyword">import</a> <a id="18391" href="group-theory.category-of-semigroups.html" class="Module">group-theory.category-of-semigroups</a>
<a id="18427" class="Keyword">open</a> <a id="18432" class="Keyword">import</a> <a id="18439" href="group-theory.cayleys-theorem.html" class="Module">group-theory.cayleys-theorem</a>
<a id="18468" class="Keyword">open</a> <a id="18473" class="Keyword">import</a> <a id="18480" href="group-theory.concrete-group-actions.html" class="Module">group-theory.concrete-group-actions</a>
<a id="18516" class="Keyword">open</a> <a id="18521" class="Keyword">import</a> <a id="18528" href="group-theory.concrete-groups.html" class="Module">group-theory.concrete-groups</a>
<a id="18557" class="Keyword">open</a> <a id="18562" class="Keyword">import</a> <a id="18569" href="group-theory.concrete-subgroups.html" class="Module">group-theory.concrete-subgroups</a>
<a id="18601" class="Keyword">open</a> <a id="18606" class="Keyword">import</a> <a id="18613" href="group-theory.conjugation.html" class="Module">group-theory.conjugation</a>
<a id="18638" class="Keyword">open</a> <a id="18643" class="Keyword">import</a> <a id="18650" href="group-theory.embeddings-groups.html" class="Module">group-theory.embeddings-groups</a>
<a id="18681" class="Keyword">open</a> <a id="18686" class="Keyword">import</a> <a id="18693" href="group-theory.endomorphism-rings-abelian-groups.html" class="Module">group-theory.endomorphism-rings-abelian-groups</a>
<a id="18740" class="Keyword">open</a> <a id="18745" class="Keyword">import</a> <a id="18752" href="group-theory.equivalences-group-actions.html" class="Module">group-theory.equivalences-group-actions</a>
<a id="18792" class="Keyword">open</a> <a id="18797" class="Keyword">import</a> <a id="18804" href="group-theory.equivalences-semigroups.html" class="Module">group-theory.equivalences-semigroups</a>
<a id="18841" class="Keyword">open</a> <a id="18846" class="Keyword">import</a> <a id="18853" href="group-theory.examples-higher-groups.html" class="Module">group-theory.examples-higher-groups</a>
<a id="18889" class="Keyword">open</a> <a id="18894" class="Keyword">import</a> <a id="18901" href="group-theory.furstenberg-groups.html" class="Module">group-theory.furstenberg-groups</a>
<a id="18933" class="Keyword">open</a> <a id="18938" class="Keyword">import</a> <a id="18945" href="group-theory.group-actions.html" class="Module">group-theory.group-actions</a>
<a id="18972" class="Keyword">open</a> <a id="18977" class="Keyword">import</a> <a id="18984" href="group-theory.groups.html" class="Module">group-theory.groups</a>
<a id="19004" class="Keyword">open</a> <a id="19009" class="Keyword">import</a> <a id="19016" href="group-theory.higher-groups.html" class="Module">group-theory.higher-groups</a>
<a id="19043" class="Keyword">open</a> <a id="19048" class="Keyword">import</a> <a id="19055" href="group-theory.homomorphisms-abelian-groups.html" class="Module">group-theory.homomorphisms-abelian-groups</a>
<a id="19097" class="Keyword">open</a> <a id="19102" class="Keyword">import</a> <a id="19109" href="group-theory.homomorphisms-group-actions.html" class="Module">group-theory.homomorphisms-group-actions</a>
<a id="19150" class="Keyword">open</a> <a id="19155" class="Keyword">import</a> <a id="19162" href="group-theory.homomorphisms-groups.html" class="Module">group-theory.homomorphisms-groups</a>
<a id="19196" class="Keyword">open</a> <a id="19201" class="Keyword">import</a> <a id="19208" href="group-theory.homomorphisms-monoids.html" class="Module">group-theory.homomorphisms-monoids</a>
<a id="19243" class="Keyword">open</a> <a id="19248" class="Keyword">import</a> <a id="19255" href="group-theory.homomorphisms-semigroups.html" class="Module">group-theory.homomorphisms-semigroups</a>
<a id="19293" class="Keyword">open</a> <a id="19298" class="Keyword">import</a> <a id="19305" href="group-theory.inverse-semigroups.html" class="Module">group-theory.inverse-semigroups</a>
<a id="19337" class="Keyword">open</a> <a id="19342" class="Keyword">import</a> <a id="19349" href="group-theory.invertible-elements-monoids.html" class="Module">group-theory.invertible-elements-monoids</a>
<a id="19390" class="Keyword">open</a> <a id="19395" class="Keyword">import</a> <a id="19402" href="group-theory.isomorphisms-abelian-groups.html" class="Module">group-theory.isomorphisms-abelian-groups</a>
<a id="19443" class="Keyword">open</a> <a id="19448" class="Keyword">import</a> <a id="19455" href="group-theory.isomorphisms-group-actions.html" class="Module">group-theory.isomorphisms-group-actions</a>
<a id="19495" class="Keyword">open</a> <a id="19500" class="Keyword">import</a> <a id="19507" href="group-theory.isomorphisms-groups.html" class="Module">group-theory.isomorphisms-groups</a>
<a id="19540" class="Keyword">open</a> <a id="19545" class="Keyword">import</a> <a id="19552" href="group-theory.isomorphisms-semigroups.html" class="Module">group-theory.isomorphisms-semigroups</a>
<a id="19589" class="Keyword">open</a> <a id="19594" class="Keyword">import</a> <a id="19601" href="group-theory.mere-equivalences-group-actions.html" class="Module">group-theory.mere-equivalences-group-actions</a>
<a id="19646" class="Keyword">open</a> <a id="19651" class="Keyword">import</a> <a id="19658" href="group-theory.monoids.html" class="Module">group-theory.monoids</a>
<a id="19679" class="Keyword">open</a> <a id="19684" class="Keyword">import</a> <a id="19691" href="group-theory.orbits-group-actions.html" class="Module">group-theory.orbits-group-actions</a>
<a id="19725" class="Keyword">open</a> <a id="19730" class="Keyword">import</a> <a id="19737" href="group-theory.precategory-of-group-actions.html" class="Module">group-theory.precategory-of-group-actions</a>
<a id="19779" class="Keyword">open</a> <a id="19784" class="Keyword">import</a> <a id="19791" href="group-theory.precategory-of-groups.html" class="Module">group-theory.precategory-of-groups</a>
<a id="19826" class="Keyword">open</a> <a id="19831" class="Keyword">import</a> <a id="19838" href="group-theory.precategory-of-semigroups.html" class="Module">group-theory.precategory-of-semigroups</a>
<a id="19877" class="Keyword">open</a> <a id="19882" class="Keyword">import</a> <a id="19889" href="group-theory.principal-group-actions.html" class="Module">group-theory.principal-group-actions</a>
<a id="19926" class="Keyword">open</a> <a id="19931" class="Keyword">import</a> <a id="19938" href="group-theory.semigroups.html" class="Module">group-theory.semigroups</a>
<a id="19962" class="Keyword">open</a> <a id="19967" class="Keyword">import</a> <a id="19974" href="group-theory.sheargroups.html" class="Module">group-theory.sheargroups</a>
<a id="19999" class="Keyword">open</a> <a id="20004" class="Keyword">import</a> <a id="20011" href="group-theory.stabilizer-groups.html" class="Module">group-theory.stabilizer-groups</a>
<a id="20042" class="Keyword">open</a> <a id="20047" class="Keyword">import</a> <a id="20054" href="group-theory.subgroups.html" class="Module">group-theory.subgroups</a>
<a id="20077" class="Keyword">open</a> <a id="20082" class="Keyword">import</a> <a id="20089" href="group-theory.substitution-functor-group-actions.html" class="Module">group-theory.substitution-functor-group-actions</a>
<a id="20137" class="Keyword">open</a> <a id="20142" class="Keyword">import</a> <a id="20149" href="group-theory.symmetric-groups.html" class="Module">group-theory.symmetric-groups</a>
<a id="20179" class="Keyword">open</a> <a id="20184" class="Keyword">import</a> <a id="20191" href="group-theory.transitive-group-actions.html" class="Module">group-theory.transitive-group-actions</a>
</pre>
## Linear algebra

<pre class="Agda"><a id="20261" class="Keyword">open</a> <a id="20266" class="Keyword">import</a> <a id="20273" href="linear-algebra.html" class="Module">linear-algebra</a>
<a id="20288" class="Keyword">open</a> <a id="20293" class="Keyword">import</a> <a id="20300" href="linear-algebra.constant-matrices.html" class="Module">linear-algebra.constant-matrices</a>
<a id="20333" class="Keyword">open</a> <a id="20338" class="Keyword">import</a> <a id="20345" href="linear-algebra.constant-vectors.html" class="Module">linear-algebra.constant-vectors</a>
<a id="20377" class="Keyword">open</a> <a id="20382" class="Keyword">import</a> <a id="20389" href="linear-algebra.diagonal-matrices-on-rings.html" class="Module">linear-algebra.diagonal-matrices-on-rings</a>
<a id="20431" class="Keyword">open</a> <a id="20436" class="Keyword">import</a> <a id="20443" href="linear-algebra.functoriality-matrices.html" class="Module">linear-algebra.functoriality-matrices</a>
<a id="20481" class="Keyword">open</a> <a id="20486" class="Keyword">import</a> <a id="20493" href="linear-algebra.functoriality-vectors.html" class="Module">linear-algebra.functoriality-vectors</a>
<a id="20530" class="Keyword">open</a> <a id="20535" class="Keyword">import</a> <a id="20542" href="linear-algebra.matrices-on-rings.html" class="Module">linear-algebra.matrices-on-rings</a>
<a id="20575" class="Keyword">open</a> <a id="20580" class="Keyword">import</a> <a id="20587" href="linear-algebra.matrices.html" class="Module">linear-algebra.matrices</a>
<a id="20611" class="Keyword">open</a> <a id="20616" class="Keyword">import</a> <a id="20623" href="linear-algebra.multiplication-matrices.html" class="Module">linear-algebra.multiplication-matrices</a>
<a id="20662" class="Keyword">open</a> <a id="20667" class="Keyword">import</a> <a id="20674" href="linear-algebra.scalar-multiplication-matrices.html" class="Module">linear-algebra.scalar-multiplication-matrices</a>
<a id="20720" class="Keyword">open</a> <a id="20725" class="Keyword">import</a> <a id="20732" href="linear-algebra.scalar-multiplication-vectors.html" class="Module">linear-algebra.scalar-multiplication-vectors</a>
<a id="20777" class="Keyword">open</a> <a id="20782" class="Keyword">import</a> <a id="20789" href="linear-algebra.transposition-matrices.html" class="Module">linear-algebra.transposition-matrices</a>
<a id="20827" class="Keyword">open</a> <a id="20832" class="Keyword">import</a> <a id="20839" href="linear-algebra.vectors-on-rings.html" class="Module">linear-algebra.vectors-on-rings</a>
<a id="20871" class="Keyword">open</a> <a id="20876" class="Keyword">import</a> <a id="20883" href="linear-algebra.vectors.html" class="Module">linear-algebra.vectors</a>
</pre>
## Order theory

<pre class="Agda"><a id="20936" class="Keyword">open</a> <a id="20941" class="Keyword">import</a> <a id="20948" href="order-theory.html" class="Module">order-theory</a>
<a id="20961" class="Keyword">open</a> <a id="20966" class="Keyword">import</a> <a id="20973" href="order-theory.chains-posets.html" class="Module">order-theory.chains-posets</a>
<a id="21000" class="Keyword">open</a> <a id="21005" class="Keyword">import</a> <a id="21012" href="order-theory.chains-preorders.html" class="Module">order-theory.chains-preorders</a>
<a id="21042" class="Keyword">open</a> <a id="21047" class="Keyword">import</a> <a id="21054" href="order-theory.decidable-subposets.html" class="Module">order-theory.decidable-subposets</a>
<a id="21087" class="Keyword">open</a> <a id="21092" class="Keyword">import</a> <a id="21099" href="order-theory.decidable-subpreorders.html" class="Module">order-theory.decidable-subpreorders</a>
<a id="21135" class="Keyword">open</a> <a id="21140" class="Keyword">import</a> <a id="21147" href="order-theory.finite-posets.html" class="Module">order-theory.finite-posets</a>
<a id="21174" class="Keyword">open</a> <a id="21179" class="Keyword">import</a> <a id="21186" href="order-theory.finite-preorders.html" class="Module">order-theory.finite-preorders</a>
<a id="21216" class="Keyword">open</a> <a id="21221" class="Keyword">import</a> <a id="21228" href="order-theory.finitely-graded-posets.html" class="Module">order-theory.finitely-graded-posets</a>
<a id="21264" class="Keyword">open</a> <a id="21269" class="Keyword">import</a> <a id="21276" href="order-theory.greatest-lower-bounds-posets.html" class="Module">order-theory.greatest-lower-bounds-posets</a>
<a id="21318" class="Keyword">open</a> <a id="21323" class="Keyword">import</a> <a id="21330" href="order-theory.interval-subposets.html" class="Module">order-theory.interval-subposets</a>
<a id="21362" class="Keyword">open</a> <a id="21367" class="Keyword">import</a> <a id="21374" href="order-theory.largest-elements-posets.html" class="Module">order-theory.largest-elements-posets</a>
<a id="21411" class="Keyword">open</a> <a id="21416" class="Keyword">import</a> <a id="21423" href="order-theory.largest-elements-preorders.html" class="Module">order-theory.largest-elements-preorders</a>
<a id="21463" class="Keyword">open</a> <a id="21468" class="Keyword">import</a> <a id="21475" href="order-theory.least-elements-posets.html" class="Module">order-theory.least-elements-posets</a>
<a id="21510" class="Keyword">open</a> <a id="21515" class="Keyword">import</a> <a id="21522" href="order-theory.least-elements-preorders.html" class="Module">order-theory.least-elements-preorders</a>
<a id="21560" class="Keyword">open</a> <a id="21565" class="Keyword">import</a> <a id="21572" href="order-theory.locally-finite-posets.html" class="Module">order-theory.locally-finite-posets</a>
<a id="21607" class="Keyword">open</a> <a id="21612" class="Keyword">import</a> <a id="21619" href="order-theory.maximal-chains-posets.html" class="Module">order-theory.maximal-chains-posets</a>
<a id="21654" class="Keyword">open</a> <a id="21659" class="Keyword">import</a> <a id="21666" href="order-theory.maximal-chains-preorders.html" class="Module">order-theory.maximal-chains-preorders</a>
<a id="21704" class="Keyword">open</a> <a id="21709" class="Keyword">import</a> <a id="21716" href="order-theory.meet-semilattices.html" class="Module">order-theory.meet-semilattices</a>
<a id="21747" class="Keyword">open</a> <a id="21752" class="Keyword">import</a> <a id="21759" href="order-theory.planar-binary-trees.html" class="Module">order-theory.planar-binary-trees</a>
<a id="21792" class="Keyword">open</a> <a id="21797" class="Keyword">import</a> <a id="21804" href="order-theory.posets.html" class="Module">order-theory.posets</a>
<a id="21824" class="Keyword">open</a> <a id="21829" class="Keyword">import</a> <a id="21836" href="order-theory.preorders.html" class="Module">order-theory.preorders</a>
<a id="21859" class="Keyword">open</a> <a id="21864" class="Keyword">import</a> <a id="21871" href="order-theory.subposets.html" class="Module">order-theory.subposets</a>
<a id="21894" class="Keyword">open</a> <a id="21899" class="Keyword">import</a> <a id="21906" href="order-theory.subpreorders.html" class="Module">order-theory.subpreorders</a>
<a id="21932" class="Keyword">open</a> <a id="21937" class="Keyword">import</a> <a id="21944" href="order-theory.total-posets.html" class="Module">order-theory.total-posets</a>
<a id="21970" class="Keyword">open</a> <a id="21975" class="Keyword">import</a> <a id="21982" href="order-theory.total-preorders.html" class="Module">order-theory.total-preorders</a>
</pre>
## Polytopes

<pre class="Agda"><a id="22038" class="Keyword">open</a> <a id="22043" class="Keyword">import</a> <a id="22050" href="polytopes.html" class="Module">polytopes</a>
<a id="22060" class="Keyword">open</a> <a id="22065" class="Keyword">import</a> <a id="22072" href="polytopes.abstract-polytopes.html" class="Module">polytopes.abstract-polytopes</a>
</pre>
## Ring theory

<pre class="Agda"><a id="22130" class="Keyword">open</a> <a id="22135" class="Keyword">import</a> <a id="22142" href="ring-theory.html" class="Module">ring-theory</a>
<a id="22154" class="Keyword">open</a> <a id="22159" class="Keyword">import</a> <a id="22166" href="ring-theory.commutative-rings.html" class="Module">ring-theory.commutative-rings</a>
<a id="22196" class="Keyword">open</a> <a id="22201" class="Keyword">import</a> <a id="22208" href="ring-theory.discrete-fields.html" class="Module">ring-theory.discrete-fields</a>
<a id="22236" class="Keyword">open</a> <a id="22241" class="Keyword">import</a> <a id="22248" href="ring-theory.division-rings.html" class="Module">ring-theory.division-rings</a>
<a id="22275" class="Keyword">open</a> <a id="22280" class="Keyword">import</a> <a id="22287" href="ring-theory.eisenstein-integers.html" class="Module">ring-theory.eisenstein-integers</a>
<a id="22319" class="Keyword">open</a> <a id="22324" class="Keyword">import</a> <a id="22331" href="ring-theory.gaussian-integers.html" class="Module">ring-theory.gaussian-integers</a>
<a id="22361" class="Keyword">open</a> <a id="22366" class="Keyword">import</a> <a id="22373" href="ring-theory.homomorphisms-commutative-rings.html" class="Module">ring-theory.homomorphisms-commutative-rings</a>
<a id="22417" class="Keyword">open</a> <a id="22422" class="Keyword">import</a> <a id="22429" href="ring-theory.homomorphisms-rings.html" class="Module">ring-theory.homomorphisms-rings</a>
<a id="22461" class="Keyword">open</a> <a id="22466" class="Keyword">import</a> <a id="22473" href="ring-theory.ideals-generated-by-subsets-rings.html" class="Module">ring-theory.ideals-generated-by-subsets-rings</a>
<a id="22519" class="Keyword">open</a> <a id="22524" class="Keyword">import</a> <a id="22531" href="ring-theory.ideals-rings.html" class="Module">ring-theory.ideals-rings</a>
<a id="22556" class="Keyword">open</a> <a id="22561" class="Keyword">import</a> <a id="22568" href="ring-theory.invertible-elements-rings.html" class="Module">ring-theory.invertible-elements-rings</a>
<a id="22606" class="Keyword">open</a> <a id="22611" class="Keyword">import</a> <a id="22618" href="ring-theory.isomorphisms-commutative-rings.html" class="Module">ring-theory.isomorphisms-commutative-rings</a>
<a id="22661" class="Keyword">open</a> <a id="22666" class="Keyword">import</a> <a id="22673" href="ring-theory.isomorphisms-rings.html" class="Module">ring-theory.isomorphisms-rings</a>
<a id="22704" class="Keyword">open</a> <a id="22709" class="Keyword">import</a> <a id="22716" href="ring-theory.localizations-rings.html" class="Module">ring-theory.localizations-rings</a>
<a id="22748" class="Keyword">open</a> <a id="22753" class="Keyword">import</a> <a id="22760" href="ring-theory.nontrivial-rings.html" class="Module">ring-theory.nontrivial-rings</a>
<a id="22789" class="Keyword">open</a> <a id="22794" class="Keyword">import</a> <a id="22801" href="ring-theory.rings.html" class="Module">ring-theory.rings</a>
</pre>
## Synthetic homotopy theory

<pre class="Agda"><a id="22862" class="Keyword">open</a> <a id="22867" class="Keyword">import</a> <a id="22874" href="synthetic-homotopy-theory.html" class="Module">synthetic-homotopy-theory</a>
<a id="22900" class="Keyword">open</a> <a id="22905" class="Keyword">import</a> <a id="22912" href="synthetic-homotopy-theory.23-pullbacks.html" class="Module">synthetic-homotopy-theory.23-pullbacks</a>
<a id="22951" class="Keyword">open</a> <a id="22956" class="Keyword">import</a> <a id="22963" href="synthetic-homotopy-theory.24-pushouts.html" class="Module">synthetic-homotopy-theory.24-pushouts</a>
<a id="23001" class="Keyword">open</a> <a id="23006" class="Keyword">import</a> <a id="23013" href="synthetic-homotopy-theory.25-cubical-diagrams.html" class="Module">synthetic-homotopy-theory.25-cubical-diagrams</a>
<a id="23059" class="Keyword">open</a> <a id="23064" class="Keyword">import</a> <a id="23071" href="synthetic-homotopy-theory.26-descent.html" class="Module">synthetic-homotopy-theory.26-descent</a>
<a id="23108" class="Keyword">open</a> <a id="23113" class="Keyword">import</a> <a id="23120" href="synthetic-homotopy-theory.26-id-pushout.html" class="Module">synthetic-homotopy-theory.26-id-pushout</a>
<a id="23160" class="Keyword">open</a> <a id="23165" class="Keyword">import</a> <a id="23172" href="synthetic-homotopy-theory.27-sequences.html" class="Module">synthetic-homotopy-theory.27-sequences</a>
<a id="23211" class="Keyword">open</a> <a id="23216" class="Keyword">import</a> <a id="23223" href="synthetic-homotopy-theory.circle.html" class="Module">synthetic-homotopy-theory.circle</a>
<a id="23256" class="Keyword">open</a> <a id="23261" class="Keyword">import</a> <a id="23268" href="synthetic-homotopy-theory.commutative-operations.html" class="Module">synthetic-homotopy-theory.commutative-operations</a>
<a id="23317" class="Keyword">open</a> <a id="23322" class="Keyword">import</a> <a id="23329" href="synthetic-homotopy-theory.cyclic-types.html" class="Module">synthetic-homotopy-theory.cyclic-types</a>
<a id="23368" class="Keyword">open</a> <a id="23373" class="Keyword">import</a> <a id="23380" href="synthetic-homotopy-theory.double-loop-spaces.html" class="Module">synthetic-homotopy-theory.double-loop-spaces</a>
<a id="23425" class="Keyword">open</a> <a id="23430" class="Keyword">import</a> <a id="23437" href="synthetic-homotopy-theory.functoriality-loop-spaces.html" class="Module">synthetic-homotopy-theory.functoriality-loop-spaces</a>
<a id="23489" class="Keyword">open</a> <a id="23494" class="Keyword">import</a> <a id="23501" href="synthetic-homotopy-theory.groups-of-loops-in-1-types.html" class="Module">synthetic-homotopy-theory.groups-of-loops-in-1-types</a>
<a id="23554" class="Keyword">open</a> <a id="23559" class="Keyword">import</a> <a id="23566" href="synthetic-homotopy-theory.infinite-cyclic-types.html" class="Module">synthetic-homotopy-theory.infinite-cyclic-types</a>
<a id="23614" class="Keyword">open</a> <a id="23619" class="Keyword">import</a> <a id="23626" href="synthetic-homotopy-theory.interval-type.html" class="Module">synthetic-homotopy-theory.interval-type</a>
<a id="23666" class="Keyword">open</a> <a id="23671" class="Keyword">import</a> <a id="23678" href="synthetic-homotopy-theory.iterated-loop-spaces.html" class="Module">synthetic-homotopy-theory.iterated-loop-spaces</a>
<a id="23725" class="Keyword">open</a> <a id="23730" class="Keyword">import</a> <a id="23737" href="synthetic-homotopy-theory.loop-spaces.html" class="Module">synthetic-homotopy-theory.loop-spaces</a>
<a id="23775" class="Keyword">open</a> <a id="23780" class="Keyword">import</a> <a id="23787" href="synthetic-homotopy-theory.pointed-dependent-functions.html" class="Module">synthetic-homotopy-theory.pointed-dependent-functions</a>
<a id="23841" class="Keyword">open</a> <a id="23846" class="Keyword">import</a> <a id="23853" href="synthetic-homotopy-theory.pointed-equivalences.html" class="Module">synthetic-homotopy-theory.pointed-equivalences</a>
<a id="23900" class="Keyword">open</a> <a id="23905" class="Keyword">import</a> <a id="23912" href="synthetic-homotopy-theory.pointed-families-of-types.html" class="Module">synthetic-homotopy-theory.pointed-families-of-types</a>
<a id="23964" class="Keyword">open</a> <a id="23969" class="Keyword">import</a> <a id="23976" href="synthetic-homotopy-theory.pointed-homotopies.html" class="Module">synthetic-homotopy-theory.pointed-homotopies</a>
<a id="24021" class="Keyword">open</a> <a id="24026" class="Keyword">import</a> <a id="24033" href="synthetic-homotopy-theory.pointed-maps.html" class="Module">synthetic-homotopy-theory.pointed-maps</a>
<a id="24072" class="Keyword">open</a> <a id="24077" class="Keyword">import</a> <a id="24084" href="synthetic-homotopy-theory.pointed-types.html" class="Module">synthetic-homotopy-theory.pointed-types</a>
<a id="24124" class="Keyword">open</a> <a id="24129" class="Keyword">import</a> <a id="24136" href="synthetic-homotopy-theory.spaces.html" class="Module">synthetic-homotopy-theory.spaces</a>
<a id="24169" class="Keyword">open</a> <a id="24174" class="Keyword">import</a> <a id="24181" href="synthetic-homotopy-theory.triple-loop-spaces.html" class="Module">synthetic-homotopy-theory.triple-loop-spaces</a>
<a id="24226" class="Keyword">open</a> <a id="24231" class="Keyword">import</a> <a id="24238" href="synthetic-homotopy-theory.universal-cover-circle.html" class="Module">synthetic-homotopy-theory.universal-cover-circle</a>
</pre>
## Tutorials

<pre class="Agda"><a id="24314" class="Keyword">open</a> <a id="24319" class="Keyword">import</a> <a id="24326" href="tutorials.basic-agda.html" class="Module">tutorials.basic-agda</a>
</pre>
## Type theories

<pre class="Agda"><a id="24378" class="Keyword">open</a> <a id="24383" class="Keyword">import</a> <a id="24390" href="type-theories.html" class="Module">type-theories</a>
<a id="24404" class="Keyword">open</a> <a id="24409" class="Keyword">import</a> <a id="24416" href="type-theories.comprehension-type-theories.html" class="Module">type-theories.comprehension-type-theories</a>
<a id="24458" class="Keyword">open</a> <a id="24463" class="Keyword">import</a> <a id="24470" href="type-theories.dependent-type-theories.html" class="Module">type-theories.dependent-type-theories</a>
<a id="24508" class="Keyword">open</a> <a id="24513" class="Keyword">import</a> <a id="24520" href="type-theories.fibered-dependent-type-theories.html" class="Module">type-theories.fibered-dependent-type-theories</a>
<a id="24566" class="Keyword">open</a> <a id="24571" class="Keyword">import</a> <a id="24578" href="type-theories.sections-dependent-type-theories.html" class="Module">type-theories.sections-dependent-type-theories</a>
<a id="24625" class="Keyword">open</a> <a id="24630" class="Keyword">import</a> <a id="24637" href="type-theories.simple-type-theories.html" class="Module">type-theories.simple-type-theories</a>
<a id="24672" class="Keyword">open</a> <a id="24677" class="Keyword">import</a> <a id="24684" href="type-theories.unityped-type-theories.html" class="Module">type-theories.unityped-type-theories</a>
</pre>
## Univalent combinatorics

<pre class="Agda"><a id="24762" class="Keyword">open</a> <a id="24767" class="Keyword">import</a> <a id="24774" href="univalent-combinatorics.html" class="Module">univalent-combinatorics</a>
<a id="24798" class="Keyword">open</a> <a id="24803" class="Keyword">import</a> <a id="24810" href="univalent-combinatorics.2-element-decidable-subtypes.html" class="Module">univalent-combinatorics.2-element-decidable-subtypes</a>
<a id="24863" class="Keyword">open</a> <a id="24868" class="Keyword">import</a> <a id="24875" href="univalent-combinatorics.2-element-subtypes.html" class="Module">univalent-combinatorics.2-element-subtypes</a>
<a id="24918" class="Keyword">open</a> <a id="24923" class="Keyword">import</a> <a id="24930" href="univalent-combinatorics.2-element-types.html" class="Module">univalent-combinatorics.2-element-types</a>
<a id="24970" class="Keyword">open</a> <a id="24975" class="Keyword">import</a> <a id="24982" href="univalent-combinatorics.binomial-types.html" class="Module">univalent-combinatorics.binomial-types</a>
<a id="25021" class="Keyword">open</a> <a id="25026" class="Keyword">import</a> <a id="25033" href="univalent-combinatorics.cartesian-product-types.html" class="Module">univalent-combinatorics.cartesian-product-types</a>
<a id="25081" class="Keyword">open</a> <a id="25086" class="Keyword">import</a> <a id="25093" href="univalent-combinatorics.classical-finite-types.html" class="Module">univalent-combinatorics.classical-finite-types</a>
<a id="25140" class="Keyword">open</a> <a id="25145" class="Keyword">import</a> <a id="25152" href="univalent-combinatorics.complements-isolated-points.html" class="Module">univalent-combinatorics.complements-isolated-points</a>
<a id="25204" class="Keyword">open</a> <a id="25209" class="Keyword">import</a> <a id="25216" href="univalent-combinatorics.coproduct-types.html" class="Module">univalent-combinatorics.coproduct-types</a>
<a id="25256" class="Keyword">open</a> <a id="25261" class="Keyword">import</a> <a id="25268" href="univalent-combinatorics.counting-decidable-subtypes.html" class="Module">univalent-combinatorics.counting-decidable-subtypes</a>
<a id="25320" class="Keyword">open</a> <a id="25325" class="Keyword">import</a> <a id="25332" href="univalent-combinatorics.counting-dependent-pair-types.html" class="Module">univalent-combinatorics.counting-dependent-pair-types</a>
<a id="25386" class="Keyword">open</a> <a id="25391" class="Keyword">import</a> <a id="25398" href="univalent-combinatorics.counting-maybe.html" class="Module">univalent-combinatorics.counting-maybe</a>
<a id="25437" class="Keyword">open</a> <a id="25442" class="Keyword">import</a> <a id="25449" href="univalent-combinatorics.counting.html" class="Module">univalent-combinatorics.counting</a>
<a id="25482" class="Keyword">open</a> <a id="25487" class="Keyword">import</a> <a id="25494" href="univalent-combinatorics.cubes.html" class="Module">univalent-combinatorics.cubes</a>
<a id="25524" class="Keyword">open</a> <a id="25529" class="Keyword">import</a> <a id="25536" href="univalent-combinatorics.decidable-dependent-function-types.html" class="Module">univalent-combinatorics.decidable-dependent-function-types</a>
<a id="25595" class="Keyword">open</a> <a id="25600" class="Keyword">import</a> <a id="25607" href="univalent-combinatorics.decidable-dependent-pair-types.html" class="Module">univalent-combinatorics.decidable-dependent-pair-types</a>
<a id="25662" class="Keyword">open</a> <a id="25667" class="Keyword">import</a> <a id="25674" href="univalent-combinatorics.decidable-subtypes.html" class="Module">univalent-combinatorics.decidable-subtypes</a>
<a id="25717" class="Keyword">open</a> <a id="25722" class="Keyword">import</a> <a id="25729" href="univalent-combinatorics.dependent-function-types.html" class="Module">univalent-combinatorics.dependent-function-types</a>
<a id="25778" class="Keyword">open</a> <a id="25783" class="Keyword">import</a> <a id="25790" href="univalent-combinatorics.dedekind-finite-sets.html" class="Module">univalent-combinatorics.dedekind-finite-sets</a>
<a id="25835" class="Keyword">open</a> <a id="25840" class="Keyword">import</a> <a id="25847" href="univalent-combinatorics.dependent-sum-finite-types.html" class="Module">univalent-combinatorics.dependent-sum-finite-types</a>
<a id="25898" class="Keyword">open</a> <a id="25903" class="Keyword">import</a> <a id="25910" href="univalent-combinatorics.distributivity-of-set-truncation-over-finite-products.html" class="Module">univalent-combinatorics.distributivity-of-set-truncation-over-finite-products</a>
<a id="25988" class="Keyword">open</a> <a id="25993" class="Keyword">import</a> <a id="26000" href="univalent-combinatorics.double-counting.html" class="Module">univalent-combinatorics.double-counting</a>
<a id="26040" class="Keyword">open</a> <a id="26045" class="Keyword">import</a> <a id="26052" href="univalent-combinatorics.embeddings-standard-finite-types.html" class="Module">univalent-combinatorics.embeddings-standard-finite-types</a>
<a id="26109" class="Keyword">open</a> <a id="26114" class="Keyword">import</a> <a id="26121" href="univalent-combinatorics.embeddings.html" class="Module">univalent-combinatorics.embeddings</a>
<a id="26156" class="Keyword">open</a> <a id="26161" class="Keyword">import</a> <a id="26168" href="univalent-combinatorics.equality-finite-types.html" class="Module">univalent-combinatorics.equality-finite-types</a>
<a id="26214" class="Keyword">open</a> <a id="26219" class="Keyword">import</a> <a id="26226" href="univalent-combinatorics.equality-standard-finite-types.html" class="Module">univalent-combinatorics.equality-standard-finite-types</a>
<a id="26281" class="Keyword">open</a> <a id="26286" class="Keyword">import</a> <a id="26293" href="univalent-combinatorics.equivalences-cubes.html" class="Module">univalent-combinatorics.equivalences-cubes</a>
<a id="26336" class="Keyword">open</a> <a id="26341" class="Keyword">import</a> <a id="26348" href="univalent-combinatorics.equivalences-standard-finite-types.html" class="Module">univalent-combinatorics.equivalences-standard-finite-types</a>
<a id="26407" class="Keyword">open</a> <a id="26412" class="Keyword">import</a> <a id="26419" href="univalent-combinatorics.equivalences.html" class="Module">univalent-combinatorics.equivalences</a>
<a id="26456" class="Keyword">open</a> <a id="26461" class="Keyword">import</a> <a id="26468" href="univalent-combinatorics.fibers-of-maps.html" class="Module">univalent-combinatorics.fibers-of-maps</a>
<a id="26507" class="Keyword">open</a> <a id="26512" class="Keyword">import</a> <a id="26519" href="univalent-combinatorics.finite-choice.html" class="Module">univalent-combinatorics.finite-choice</a>
<a id="26557" class="Keyword">open</a> <a id="26562" class="Keyword">import</a> <a id="26569" href="univalent-combinatorics.finite-connected-components.html" class="Module">univalent-combinatorics.finite-connected-components</a>
<a id="26621" class="Keyword">open</a> <a id="26626" class="Keyword">import</a> <a id="26633" href="univalent-combinatorics.finite-presentations.html" class="Module">univalent-combinatorics.finite-presentations</a>
<a id="26678" class="Keyword">open</a> <a id="26683" class="Keyword">import</a> <a id="26690" href="univalent-combinatorics.finite-types.html" class="Module">univalent-combinatorics.finite-types</a>
<a id="26727" class="Keyword">open</a> <a id="26732" class="Keyword">import</a> <a id="26739" href="univalent-combinatorics.finitely-presented-types.html" class="Module">univalent-combinatorics.finitely-presented-types</a>
<a id="26788" class="Keyword">open</a> <a id="26793" class="Keyword">import</a> <a id="26800" href="univalent-combinatorics.function-types.html" class="Module">univalent-combinatorics.function-types</a>
<a id="26839" class="Keyword">open</a> <a id="26844" class="Keyword">import</a> <a id="26851" href="univalent-combinatorics.image-of-maps.html" class="Module">univalent-combinatorics.image-of-maps</a>
<a id="26889" class="Keyword">open</a> <a id="26894" class="Keyword">import</a> <a id="26901" href="univalent-combinatorics.inequality-types-with-counting.html" class="Module">univalent-combinatorics.inequality-types-with-counting</a>
<a id="26956" class="Keyword">open</a> <a id="26961" class="Keyword">import</a> <a id="26968" href="univalent-combinatorics.injective-maps.html" class="Module">univalent-combinatorics.injective-maps</a>
<a id="27007" class="Keyword">open</a> <a id="27012" class="Keyword">import</a> <a id="27019" href="univalent-combinatorics.kuratowsky-finite-sets.html" class="Module">univalent-combinatorics.kuratowsky-finite-sets</a>
<a id="27066" class="Keyword">open</a> <a id="27071" class="Keyword">import</a> <a id="27078" href="univalent-combinatorics.lists.html" class="Module">univalent-combinatorics.lists</a>
<a id="27108" class="Keyword">open</a> <a id="27113" class="Keyword">import</a> <a id="27120" href="univalent-combinatorics.maybe.html" class="Module">univalent-combinatorics.maybe</a>
<a id="27150" class="Keyword">open</a> <a id="27155" class="Keyword">import</a> <a id="27162" href="univalent-combinatorics.orientations-cubes.html" class="Module">univalent-combinatorics.orientations-cubes</a>
<a id="27205" class="Keyword">open</a> <a id="27210" class="Keyword">import</a> <a id="27217" href="univalent-combinatorics.petri-nets.html" class="Module">univalent-combinatorics.petri-nets</a>
<a id="27252" class="Keyword">open</a> <a id="27257" class="Keyword">import</a> <a id="27264" href="univalent-combinatorics.pi-finite-types.html" class="Module">univalent-combinatorics.pi-finite-types</a>
<a id="27304" class="Keyword">open</a> <a id="27309" class="Keyword">import</a> <a id="27316" href="univalent-combinatorics.pigeonhole-principle.html" class="Module">univalent-combinatorics.pigeonhole-principle</a>
<a id="27361" class="Keyword">open</a> <a id="27366" class="Keyword">import</a> <a id="27373" href="univalent-combinatorics.presented-pi-finite-types.html" class="Module">univalent-combinatorics.presented-pi-finite-types</a>
<a id="27423" class="Keyword">open</a> <a id="27428" class="Keyword">import</a> <a id="27435" href="univalent-combinatorics.ramsey-theory.html" class="Module">univalent-combinatorics.ramsey-theory</a>
<a id="27473" class="Keyword">open</a> <a id="27478" class="Keyword">import</a> <a id="27485" href="univalent-combinatorics.retracts-of-finite-types.html" class="Module">univalent-combinatorics.retracts-of-finite-types</a>
<a id="27534" class="Keyword">open</a> <a id="27539" class="Keyword">import</a> <a id="27546" href="univalent-combinatorics.skipping-element-standard-finite-types.html" class="Module">univalent-combinatorics.skipping-element-standard-finite-types</a>
<a id="27609" class="Keyword">open</a> <a id="27614" class="Keyword">import</a> <a id="27621" href="univalent-combinatorics.species.html" class="Module">univalent-combinatorics.species</a>
<a id="27653" class="Keyword">open</a> <a id="27658" class="Keyword">import</a> <a id="27665" href="univalent-combinatorics.standard-finite-pruned-trees.html" class="Module">univalent-combinatorics.standard-finite-pruned-trees</a>
<a id="27718" class="Keyword">open</a> <a id="27723" class="Keyword">import</a> <a id="27730" href="univalent-combinatorics.standard-finite-trees.html" class="Module">univalent-combinatorics.standard-finite-trees</a>
<a id="27776" class="Keyword">open</a> <a id="27781" class="Keyword">import</a> <a id="27788" href="univalent-combinatorics.standard-finite-types.html" class="Module">univalent-combinatorics.standard-finite-types</a>
<a id="27834" class="Keyword">open</a> <a id="27839" class="Keyword">import</a> <a id="27846" href="univalent-combinatorics.sums-of-natural-numbers.html" class="Module">univalent-combinatorics.sums-of-natural-numbers</a>
<a id="27894" class="Keyword">open</a> <a id="27899" class="Keyword">import</a> <a id="27906" href="univalent-combinatorics.surjective-maps.html" class="Module">univalent-combinatorics.surjective-maps</a>
</pre>
## Wild algebra

<pre class="Agda"><a id="27976" class="Keyword">open</a> <a id="27981" class="Keyword">import</a> <a id="27988" href="wild-algebra.html" class="Module">wild-algebra</a>
<a id="28001" class="Keyword">open</a> <a id="28006" class="Keyword">import</a> <a id="28013" href="wild-algebra.magmas.html" class="Module">wild-algebra.magmas</a>
<a id="28033" class="Keyword">open</a> <a id="28038" class="Keyword">import</a> <a id="28045" href="wild-algebra.morphisms-magmas.html" class="Module">wild-algebra.morphisms-magmas</a>
<a id="28075" class="Keyword">open</a> <a id="28080" class="Keyword">import</a> <a id="28087" href="wild-algebra.morphisms-wild-unital-magmas.html" class="Module">wild-algebra.morphisms-wild-unital-magmas</a>
<a id="28129" class="Keyword">open</a> <a id="28134" class="Keyword">import</a> <a id="28141" href="wild-algebra.universal-property-lists-wild-monoids.html" class="Module">wild-algebra.universal-property-lists-wild-monoids</a>
<a id="28192" class="Keyword">open</a> <a id="28197" class="Keyword">import</a> <a id="28204" href="wild-algebra.wild-groups.html" class="Module">wild-algebra.wild-groups</a>
<a id="28229" class="Keyword">open</a> <a id="28234" class="Keyword">import</a> <a id="28241" href="wild-algebra.wild-loops.html" class="Module">wild-algebra.wild-loops</a>
<a id="28265" class="Keyword">open</a> <a id="28270" class="Keyword">import</a> <a id="28277" href="wild-algebra.wild-monoids.html" class="Module">wild-algebra.wild-monoids</a>
<a id="28303" class="Keyword">open</a> <a id="28308" class="Keyword">import</a> <a id="28315" href="wild-algebra.wild-quasigroups.html" class="Module">wild-algebra.wild-quasigroups</a>
<a id="28345" class="Keyword">open</a> <a id="28350" class="Keyword">import</a> <a id="28357" href="wild-algebra.wild-semigroups.html" class="Module">wild-algebra.wild-semigroups</a>
<a id="28386" class="Keyword">open</a> <a id="28391" class="Keyword">import</a> <a id="28398" href="wild-algebra.wild-unital-magmas.html" class="Module">wild-algebra.wild-unital-magmas</a>
</pre>
## Everything

See the list of all Agda modules [here](everything.html).

