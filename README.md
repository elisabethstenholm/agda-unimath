---
title: Univalent mathematics in Agda
---

Welcome to the website of the `agda-unimath` formalization project.

[![CI](https://github.com/UniMath/agda-unimath/actions/workflows/ci.yaml/badge.svg)](https://github.com/UniMath/agda-unimath/actions/workflows/ci.yaml) [![pages-build-deployment](https://github.com/UniMath/agda-unimath/actions/workflows/pages/pages-build-deployment/badge.svg)](https://github.com/UniMath/agda-unimath/actions/workflows/pages/pages-build-deployment)

The `agda-unimath` library is a new formalisation project for univalent mathematics in Agda. Our goal is to formalize an extensive curriculum of mathematics from the univalent point of view. Furthermore, we think libraries of formalized mathematics have the potential to be useful, and informative resources for mathematicians. Our library is designed to work towards this goal, and we welcome contributions to the library about any topic in mathematics.

The library is built in Agda 2.6.2. It can be compiled by running `make check` from the main folder of the repository.

## Joining the project

Great, you want to contribute something! The best way to start is to find us in our chat channels on the [agda-unimath discord](https://discord.gg/Zp2e8hYsuX). We have a vibing community there, and you're more than welcome to join us just to hang out.

Once you've decided what you want to contribute, the best way to proceed is to make your own fork of the library. Within your fork, make a separate branch in which you will be making your contributions. Now you're ready to start your project! When you've completed your formalization you can proceed by making a pull request. Then we will review your contributions, and merge it when it is ready for the `agda-unimath` library.

## Statement of inclusion

There are many reasons to contribute something to a library of formalized mathematics. Some do it just for fun, some do it for their research, some do it to learn something. Whatever your reason is, we welcome your contributions! To keep the experience of contributing something to our library enjoyable for everyone, we strive for an inclusive community of contributors. You can expect from us that we are kind and respectful in discussions, that we will be mindful of your pronouns and use [inclusive language](https://www.apa.org/about/apa/equity-diversity-inclusion/language-guidelines), and that we value your input regardless of your level of experience or status in the community. We're commited to providing a safe and welcoming environment to people of any gender identity, sexual orientation, race, colour, age, ability, ethnicity, background, or fluency in English -- here on github, in online communication channels, and in person. Homotopy type theory is difficult enough without all the barriers that many of us have to face, so we hope to bring some of those down a bit.

:rainbow: Happy contributing!

Elisabeth Bonnevier  
Jonathan Prieto-Cubides  
Egbert Rijke

<pre class="Agda"><a id="2980" class="Symbol">{-#</a> <a id="2984" class="Keyword">OPTIONS</a> <a id="2992" class="Pragma">--without-K</a> <a id="3004" class="Pragma">--exact-split</a> <a id="3018" class="Pragma">--guardedness</a> <a id="3032" class="Symbol">#-}</a>
</pre>
See the list of all Agda modules [here](everything.html).

## Category theory

<pre class="Agda"><a id="3128" class="Keyword">open</a> <a id="3133" class="Keyword">import</a> <a id="3140" href="category-theory.html" class="Module">category-theory</a>
<a id="3156" class="Keyword">open</a> <a id="3161" class="Keyword">import</a> <a id="3168" href="category-theory.adjunctions-large-precategories.html" class="Module">category-theory.adjunctions-large-precategories</a>
<a id="3216" class="Keyword">open</a> <a id="3221" class="Keyword">import</a> <a id="3228" href="category-theory.anafunctors.html" class="Module">category-theory.anafunctors</a>
<a id="3256" class="Keyword">open</a> <a id="3261" class="Keyword">import</a> <a id="3268" href="category-theory.categories.html" class="Module">category-theory.categories</a>
<a id="3295" class="Keyword">open</a> <a id="3300" class="Keyword">import</a> <a id="3307" href="category-theory.epimorphisms-large-precategories.html" class="Module">category-theory.epimorphisms-large-precategories</a>
<a id="3356" class="Keyword">open</a> <a id="3361" class="Keyword">import</a> <a id="3368" href="category-theory.equivalences-categories.html" class="Module">category-theory.equivalences-categories</a>
<a id="3408" class="Keyword">open</a> <a id="3413" class="Keyword">import</a> <a id="3420" href="category-theory.equivalences-large-precategories.html" class="Module">category-theory.equivalences-large-precategories</a>
<a id="3469" class="Keyword">open</a> <a id="3474" class="Keyword">import</a> <a id="3481" href="category-theory.equivalences-precategories.html" class="Module">category-theory.equivalences-precategories</a>
<a id="3524" class="Keyword">open</a> <a id="3529" class="Keyword">import</a> <a id="3536" href="category-theory.functors-categories.html" class="Module">category-theory.functors-categories</a>
<a id="3572" class="Keyword">open</a> <a id="3577" class="Keyword">import</a> <a id="3584" href="category-theory.functors-large-precategories.html" class="Module">category-theory.functors-large-precategories</a>
<a id="3629" class="Keyword">open</a> <a id="3634" class="Keyword">import</a> <a id="3641" href="category-theory.functors-precategories.html" class="Module">category-theory.functors-precategories</a>
<a id="3680" class="Keyword">open</a> <a id="3685" class="Keyword">import</a> <a id="3692" href="category-theory.homotopies-natural-transformations-large-precategories.html" class="Module">category-theory.homotopies-natural-transformations-large-precategories</a>
<a id="3763" class="Keyword">open</a> <a id="3768" class="Keyword">import</a> <a id="3775" href="category-theory.initial-objects-precategories.html" class="Module">category-theory.initial-objects-precategories</a>
<a id="3821" class="Keyword">open</a> <a id="3826" class="Keyword">import</a> <a id="3833" href="category-theory.isomorphisms-categories.html" class="Module">category-theory.isomorphisms-categories</a>
<a id="3873" class="Keyword">open</a> <a id="3878" class="Keyword">import</a> <a id="3885" href="category-theory.isomorphisms-large-precategories.html" class="Module">category-theory.isomorphisms-large-precategories</a>
<a id="3934" class="Keyword">open</a> <a id="3939" class="Keyword">import</a> <a id="3946" href="category-theory.isomorphisms-precategories.html" class="Module">category-theory.isomorphisms-precategories</a>
<a id="3989" class="Keyword">open</a> <a id="3994" class="Keyword">import</a> <a id="4001" href="category-theory.large-categories.html" class="Module">category-theory.large-categories</a>
<a id="4034" class="Keyword">open</a> <a id="4039" class="Keyword">import</a> <a id="4046" href="category-theory.large-precategories.html" class="Module">category-theory.large-precategories</a>
<a id="4082" class="Keyword">open</a> <a id="4087" class="Keyword">import</a> <a id="4094" href="category-theory.monomorphisms-large-precategories.html" class="Module">category-theory.monomorphisms-large-precategories</a>
<a id="4144" class="Keyword">open</a> <a id="4149" class="Keyword">import</a> <a id="4156" href="category-theory.natural-isomorphisms-categories.html" class="Module">category-theory.natural-isomorphisms-categories</a>
<a id="4204" class="Keyword">open</a> <a id="4209" class="Keyword">import</a> <a id="4216" href="category-theory.natural-isomorphisms-large-precategories.html" class="Module">category-theory.natural-isomorphisms-large-precategories</a>
<a id="4273" class="Keyword">open</a> <a id="4278" class="Keyword">import</a> <a id="4285" href="category-theory.natural-isomorphisms-precategories.html" class="Module">category-theory.natural-isomorphisms-precategories</a>
<a id="4336" class="Keyword">open</a> <a id="4341" class="Keyword">import</a> <a id="4348" href="category-theory.natural-transformations-categories.html" class="Module">category-theory.natural-transformations-categories</a>
<a id="4399" class="Keyword">open</a> <a id="4404" class="Keyword">import</a> <a id="4411" href="category-theory.natural-transformations-large-precategories.html" class="Module">category-theory.natural-transformations-large-precategories</a>
<a id="4471" class="Keyword">open</a> <a id="4476" class="Keyword">import</a> <a id="4483" href="category-theory.natural-transformations-precategories.html" class="Module">category-theory.natural-transformations-precategories</a>
<a id="4537" class="Keyword">open</a> <a id="4542" class="Keyword">import</a> <a id="4549" href="category-theory.precategories.html" class="Module">category-theory.precategories</a>
<a id="4579" class="Keyword">open</a> <a id="4584" class="Keyword">import</a> <a id="4591" href="category-theory.slice-precategories.html" class="Module">category-theory.slice-precategories</a>
<a id="4627" class="Keyword">open</a> <a id="4632" class="Keyword">import</a> <a id="4639" href="category-theory.terminal-objects-precategories.html" class="Module">category-theory.terminal-objects-precategories</a>
</pre>
## Commutative algebra

<pre class="Agda"><a id="4723" class="Keyword">open</a> <a id="4728" class="Keyword">import</a> <a id="4735" href="commutative-algebra.html" class="Module">commutative-algebra</a>
<a id="4755" class="Keyword">open</a> <a id="4760" class="Keyword">import</a> <a id="4767" href="commutative-algebra.commutative-rings.html" class="Module">commutative-algebra.commutative-rings</a>
<a id="4805" class="Keyword">open</a> <a id="4810" class="Keyword">import</a> <a id="4817" href="commutative-algebra.discrete-fields.html" class="Module">commutative-algebra.discrete-fields</a>
<a id="4853" class="Keyword">open</a> <a id="4858" class="Keyword">import</a> <a id="4865" href="commutative-algebra.eisenstein-integers.html" class="Module">commutative-algebra.eisenstein-integers</a>
<a id="4905" class="Keyword">open</a> <a id="4910" class="Keyword">import</a> <a id="4917" href="commutative-algebra.gaussian-integers.html" class="Module">commutative-algebra.gaussian-integers</a>
<a id="4955" class="Keyword">open</a> <a id="4960" class="Keyword">import</a> <a id="4967" href="commutative-algebra.homomorphisms-commutative-rings.html" class="Module">commutative-algebra.homomorphisms-commutative-rings</a>
<a id="5019" class="Keyword">open</a> <a id="5024" class="Keyword">import</a> <a id="5031" href="commutative-algebra.ideals-commutative-rings.html" class="Module">commutative-algebra.ideals-commutative-rings</a>
<a id="5076" class="Keyword">open</a> <a id="5081" class="Keyword">import</a> <a id="5088" href="commutative-algebra.isomorphisms-commutative-rings.html" class="Module">commutative-algebra.isomorphisms-commutative-rings</a>
</pre>
## Elementary number theory

<pre class="Agda"><a id="5181" class="Keyword">open</a> <a id="5186" class="Keyword">import</a> <a id="5193" href="elementary-number-theory.html" class="Module">elementary-number-theory</a>
<a id="5218" class="Keyword">open</a> <a id="5223" class="Keyword">import</a> <a id="5230" href="elementary-number-theory.absolute-value-integers.html" class="Module">elementary-number-theory.absolute-value-integers</a>
<a id="5279" class="Keyword">open</a> <a id="5284" class="Keyword">import</a> <a id="5291" href="elementary-number-theory.addition-integers.html" class="Module">elementary-number-theory.addition-integers</a>
<a id="5334" class="Keyword">open</a> <a id="5339" class="Keyword">import</a> <a id="5346" href="elementary-number-theory.addition-natural-numbers.html" class="Module">elementary-number-theory.addition-natural-numbers</a>
<a id="5396" class="Keyword">open</a> <a id="5401" class="Keyword">import</a> <a id="5408" href="elementary-number-theory.arithmetic-functions.html" class="Module">elementary-number-theory.arithmetic-functions</a>
<a id="5454" class="Keyword">open</a> <a id="5459" class="Keyword">import</a> <a id="5466" href="elementary-number-theory.binomial-coefficients.html" class="Module">elementary-number-theory.binomial-coefficients</a>
<a id="5513" class="Keyword">open</a> <a id="5518" class="Keyword">import</a> <a id="5525" href="elementary-number-theory.bounded-sums-arithmetic-functions.html" class="Module">elementary-number-theory.bounded-sums-arithmetic-functions</a>
<a id="5584" class="Keyword">open</a> <a id="5589" class="Keyword">import</a> <a id="5596" href="elementary-number-theory.catalan-numbers.html" class="Module">elementary-number-theory.catalan-numbers</a>
<a id="5637" class="Keyword">open</a> <a id="5642" class="Keyword">import</a> <a id="5649" href="elementary-number-theory.collatz-bijection.html" class="Module">elementary-number-theory.collatz-bijection</a>
<a id="5692" class="Keyword">open</a> <a id="5697" class="Keyword">import</a> <a id="5704" href="elementary-number-theory.collatz-conjecture.html" class="Module">elementary-number-theory.collatz-conjecture</a>
<a id="5748" class="Keyword">open</a> <a id="5753" class="Keyword">import</a> <a id="5760" href="elementary-number-theory.congruence-integers.html" class="Module">elementary-number-theory.congruence-integers</a>
<a id="5805" class="Keyword">open</a> <a id="5810" class="Keyword">import</a> <a id="5817" href="elementary-number-theory.congruence-natural-numbers.html" class="Module">elementary-number-theory.congruence-natural-numbers</a>
<a id="5869" class="Keyword">open</a> <a id="5874" class="Keyword">import</a> <a id="5881" href="elementary-number-theory.decidable-dependent-function-types.html" class="Module">elementary-number-theory.decidable-dependent-function-types</a>
<a id="5941" class="Keyword">open</a> <a id="5946" class="Keyword">import</a> <a id="5953" href="elementary-number-theory.decidable-types.html" class="Module">elementary-number-theory.decidable-types</a>
<a id="5994" class="Keyword">open</a> <a id="5999" class="Keyword">import</a> <a id="6006" href="elementary-number-theory.difference-integers.html" class="Module">elementary-number-theory.difference-integers</a>
<a id="6051" class="Keyword">open</a> <a id="6056" class="Keyword">import</a> <a id="6063" href="elementary-number-theory.dirichlet-convolution.html" class="Module">elementary-number-theory.dirichlet-convolution</a>
<a id="6110" class="Keyword">open</a> <a id="6115" class="Keyword">import</a> <a id="6122" href="elementary-number-theory.distance-integers.html" class="Module">elementary-number-theory.distance-integers</a>
<a id="6165" class="Keyword">open</a> <a id="6170" class="Keyword">import</a> <a id="6177" href="elementary-number-theory.distance-natural-numbers.html" class="Module">elementary-number-theory.distance-natural-numbers</a>
<a id="6227" class="Keyword">open</a> <a id="6232" class="Keyword">import</a> <a id="6239" href="elementary-number-theory.divisibility-integers.html" class="Module">elementary-number-theory.divisibility-integers</a>
<a id="6286" class="Keyword">open</a> <a id="6291" class="Keyword">import</a> <a id="6298" href="elementary-number-theory.divisibility-modular-arithmetic.html" class="Module">elementary-number-theory.divisibility-modular-arithmetic</a>
<a id="6355" class="Keyword">open</a> <a id="6360" class="Keyword">import</a> <a id="6367" href="elementary-number-theory.divisibility-natural-numbers.html" class="Module">elementary-number-theory.divisibility-natural-numbers</a>
<a id="6421" class="Keyword">open</a> <a id="6426" class="Keyword">import</a> <a id="6433" href="elementary-number-theory.divisibility-standard-finite-types.html" class="Module">elementary-number-theory.divisibility-standard-finite-types</a>
<a id="6493" class="Keyword">open</a> <a id="6498" class="Keyword">import</a> <a id="6505" href="elementary-number-theory.equality-integers.html" class="Module">elementary-number-theory.equality-integers</a>
<a id="6548" class="Keyword">open</a> <a id="6553" class="Keyword">import</a> <a id="6560" href="elementary-number-theory.equality-natural-numbers.html" class="Module">elementary-number-theory.equality-natural-numbers</a>
<a id="6610" class="Keyword">open</a> <a id="6615" class="Keyword">import</a> <a id="6622" href="elementary-number-theory.euclidean-division-natural-numbers.html" class="Module">elementary-number-theory.euclidean-division-natural-numbers</a>
<a id="6682" class="Keyword">open</a> <a id="6687" class="Keyword">import</a> <a id="6694" href="elementary-number-theory.eulers-totient-function.html" class="Module">elementary-number-theory.eulers-totient-function</a>
<a id="6743" class="Keyword">open</a> <a id="6748" class="Keyword">import</a> <a id="6755" href="elementary-number-theory.exponentiation-natural-numbers.html" class="Module">elementary-number-theory.exponentiation-natural-numbers</a>
<a id="6811" class="Keyword">open</a> <a id="6816" class="Keyword">import</a> <a id="6823" href="elementary-number-theory.factorials.html" class="Module">elementary-number-theory.factorials</a>
<a id="6859" class="Keyword">open</a> <a id="6864" class="Keyword">import</a> <a id="6871" href="elementary-number-theory.falling-factorials.html" class="Module">elementary-number-theory.falling-factorials</a>
<a id="6915" class="Keyword">open</a> <a id="6920" class="Keyword">import</a> <a id="6927" href="elementary-number-theory.fibonacci-sequence.html" class="Module">elementary-number-theory.fibonacci-sequence</a>
<a id="6971" class="Keyword">open</a> <a id="6976" class="Keyword">import</a> <a id="6983" href="elementary-number-theory.finitary-natural-numbers.html" class="Module">elementary-number-theory.finitary-natural-numbers</a>
<a id="7033" class="Keyword">open</a> <a id="7038" class="Keyword">import</a> <a id="7045" href="elementary-number-theory.finitely-cyclic-maps.html" class="Module">elementary-number-theory.finitely-cyclic-maps</a>
<a id="7091" class="Keyword">open</a> <a id="7096" class="Keyword">import</a> <a id="7103" href="elementary-number-theory.fractions.html" class="Module">elementary-number-theory.fractions</a>
<a id="7138" class="Keyword">open</a> <a id="7143" class="Keyword">import</a> <a id="7150" href="elementary-number-theory.goldbach-conjecture.html" class="Module">elementary-number-theory.goldbach-conjecture</a>
<a id="7195" class="Keyword">open</a> <a id="7200" class="Keyword">import</a> <a id="7207" href="elementary-number-theory.greatest-common-divisor-integers.html" class="Module">elementary-number-theory.greatest-common-divisor-integers</a>
<a id="7265" class="Keyword">open</a> <a id="7270" class="Keyword">import</a> <a id="7277" href="elementary-number-theory.greatest-common-divisor-natural-numbers.html" class="Module">elementary-number-theory.greatest-common-divisor-natural-numbers</a>
<a id="7342" class="Keyword">open</a> <a id="7347" class="Keyword">import</a> <a id="7354" href="elementary-number-theory.group-of-integers.html" class="Module">elementary-number-theory.group-of-integers</a>
<a id="7397" class="Keyword">open</a> <a id="7402" class="Keyword">import</a> <a id="7409" href="elementary-number-theory.groups-of-modular-arithmetic.html" class="Module">elementary-number-theory.groups-of-modular-arithmetic</a>
<a id="7463" class="Keyword">open</a> <a id="7468" class="Keyword">import</a> <a id="7475" href="elementary-number-theory.inequality-integers.html" class="Module">elementary-number-theory.inequality-integers</a>
<a id="7520" class="Keyword">open</a> <a id="7525" class="Keyword">import</a> <a id="7532" href="elementary-number-theory.inequality-natural-numbers.html" class="Module">elementary-number-theory.inequality-natural-numbers</a>
<a id="7584" class="Keyword">open</a> <a id="7589" class="Keyword">import</a> <a id="7596" href="elementary-number-theory.inequality-standard-finite-types.html" class="Module">elementary-number-theory.inequality-standard-finite-types</a>
<a id="7654" class="Keyword">open</a> <a id="7659" class="Keyword">import</a> <a id="7666" href="elementary-number-theory.infinitude-of-primes.html" class="Module">elementary-number-theory.infinitude-of-primes</a>
<a id="7712" class="Keyword">open</a> <a id="7717" class="Keyword">import</a> <a id="7724" href="elementary-number-theory.integer-partitions.html" class="Module">elementary-number-theory.integer-partitions</a>
<a id="7768" class="Keyword">open</a> <a id="7773" class="Keyword">import</a> <a id="7780" href="elementary-number-theory.integers.html" class="Module">elementary-number-theory.integers</a>
<a id="7814" class="Keyword">open</a> <a id="7819" class="Keyword">import</a> <a id="7826" href="elementary-number-theory.lower-bounds-natural-numbers.html" class="Module">elementary-number-theory.lower-bounds-natural-numbers</a>
<a id="7880" class="Keyword">open</a> <a id="7885" class="Keyword">import</a> <a id="7892" href="elementary-number-theory.maximum-natural-numbers.html" class="Module">elementary-number-theory.maximum-natural-numbers</a>
<a id="7941" class="Keyword">open</a> <a id="7946" class="Keyword">import</a> <a id="7953" href="elementary-number-theory.mersenne-primes.html" class="Module">elementary-number-theory.mersenne-primes</a>
<a id="7994" class="Keyword">open</a> <a id="7999" class="Keyword">import</a> <a id="8006" href="elementary-number-theory.minimum-natural-numbers.html" class="Module">elementary-number-theory.minimum-natural-numbers</a>
<a id="8055" class="Keyword">open</a> <a id="8060" class="Keyword">import</a> <a id="8067" href="elementary-number-theory.modular-arithmetic-standard-finite-types.html" class="Module">elementary-number-theory.modular-arithmetic-standard-finite-types</a>
<a id="8133" class="Keyword">open</a> <a id="8138" class="Keyword">import</a> <a id="8145" href="elementary-number-theory.modular-arithmetic.html" class="Module">elementary-number-theory.modular-arithmetic</a>
<a id="8189" class="Keyword">open</a> <a id="8194" class="Keyword">import</a> <a id="8201" href="elementary-number-theory.multiplication-integers.html" class="Module">elementary-number-theory.multiplication-integers</a>
<a id="8250" class="Keyword">open</a> <a id="8255" class="Keyword">import</a> <a id="8262" href="elementary-number-theory.multiplication-natural-numbers.html" class="Module">elementary-number-theory.multiplication-natural-numbers</a>
<a id="8318" class="Keyword">open</a> <a id="8323" class="Keyword">import</a> <a id="8330" href="elementary-number-theory.natural-numbers.html" class="Module">elementary-number-theory.natural-numbers</a>
<a id="8371" class="Keyword">open</a> <a id="8376" class="Keyword">import</a> <a id="8383" href="elementary-number-theory.nonzero-natural-numbers.html" class="Module">elementary-number-theory.nonzero-natural-numbers</a>
<a id="8432" class="Keyword">open</a> <a id="8437" class="Keyword">import</a> <a id="8444" href="elementary-number-theory.ordinal-induction-natural-numbers.html" class="Module">elementary-number-theory.ordinal-induction-natural-numbers</a>
<a id="8503" class="Keyword">open</a> <a id="8508" class="Keyword">import</a> <a id="8515" href="elementary-number-theory.prime-numbers.html" class="Module">elementary-number-theory.prime-numbers</a>
<a id="8554" class="Keyword">open</a> <a id="8559" class="Keyword">import</a> <a id="8566" href="elementary-number-theory.products-of-natural-numbers.html" class="Module">elementary-number-theory.products-of-natural-numbers</a>
<a id="8619" class="Keyword">open</a> <a id="8624" class="Keyword">import</a> <a id="8631" href="elementary-number-theory.proper-divisors-natural-numbers.html" class="Module">elementary-number-theory.proper-divisors-natural-numbers</a>
<a id="8688" class="Keyword">open</a> <a id="8693" class="Keyword">import</a> <a id="8700" href="elementary-number-theory.rational-numbers.html" class="Module">elementary-number-theory.rational-numbers</a>
<a id="8742" class="Keyword">open</a> <a id="8747" class="Keyword">import</a> <a id="8754" href="elementary-number-theory.relatively-prime-integers.html" class="Module">elementary-number-theory.relatively-prime-integers</a>
<a id="8805" class="Keyword">open</a> <a id="8810" class="Keyword">import</a> <a id="8817" href="elementary-number-theory.relatively-prime-natural-numbers.html" class="Module">elementary-number-theory.relatively-prime-natural-numbers</a>
<a id="8875" class="Keyword">open</a> <a id="8880" class="Keyword">import</a> <a id="8887" href="elementary-number-theory.repeating-element-standard-finite-type.html" class="Module">elementary-number-theory.repeating-element-standard-finite-type</a>
<a id="8951" class="Keyword">open</a> <a id="8956" class="Keyword">import</a> <a id="8963" href="elementary-number-theory.retracts-of-natural-numbers.html" class="Module">elementary-number-theory.retracts-of-natural-numbers</a>
<a id="9016" class="Keyword">open</a> <a id="9021" class="Keyword">import</a> <a id="9028" href="elementary-number-theory.square-free-natural-numbers.html" class="Module">elementary-number-theory.square-free-natural-numbers</a>
<a id="9081" class="Keyword">open</a> <a id="9086" class="Keyword">import</a> <a id="9093" href="elementary-number-theory.stirling-numbers-of-the-second-kind.html" class="Module">elementary-number-theory.stirling-numbers-of-the-second-kind</a>
<a id="9154" class="Keyword">open</a> <a id="9159" class="Keyword">import</a> <a id="9166" href="elementary-number-theory.strong-induction-natural-numbers.html" class="Module">elementary-number-theory.strong-induction-natural-numbers</a>
<a id="9224" class="Keyword">open</a> <a id="9229" class="Keyword">import</a> <a id="9236" href="elementary-number-theory.sums-of-natural-numbers.html" class="Module">elementary-number-theory.sums-of-natural-numbers</a>
<a id="9285" class="Keyword">open</a> <a id="9290" class="Keyword">import</a> <a id="9297" href="elementary-number-theory.telephone-numbers.html" class="Module">elementary-number-theory.telephone-numbers</a>
<a id="9340" class="Keyword">open</a> <a id="9345" class="Keyword">import</a> <a id="9352" href="elementary-number-theory.triangular-numbers.html" class="Module">elementary-number-theory.triangular-numbers</a>
<a id="9396" class="Keyword">open</a> <a id="9401" class="Keyword">import</a> <a id="9408" href="elementary-number-theory.twin-prime-conjecture.html" class="Module">elementary-number-theory.twin-prime-conjecture</a>
<a id="9455" class="Keyword">open</a> <a id="9460" class="Keyword">import</a> <a id="9467" href="elementary-number-theory.unit-elements-standard-finite-types.html" class="Module">elementary-number-theory.unit-elements-standard-finite-types</a>
<a id="9528" class="Keyword">open</a> <a id="9533" class="Keyword">import</a> <a id="9540" href="elementary-number-theory.unit-similarity-standard-finite-types.html" class="Module">elementary-number-theory.unit-similarity-standard-finite-types</a>
<a id="9603" class="Keyword">open</a> <a id="9608" class="Keyword">import</a> <a id="9615" href="elementary-number-theory.universal-property-natural-numbers.html" class="Module">elementary-number-theory.universal-property-natural-numbers</a>
<a id="9675" class="Keyword">open</a> <a id="9680" class="Keyword">import</a> <a id="9687" href="elementary-number-theory.upper-bounds-natural-numbers.html" class="Module">elementary-number-theory.upper-bounds-natural-numbers</a>
<a id="9741" class="Keyword">open</a> <a id="9746" class="Keyword">import</a> <a id="9753" href="elementary-number-theory.well-ordering-principle-natural-numbers.html" class="Module">elementary-number-theory.well-ordering-principle-natural-numbers</a>
<a id="9818" class="Keyword">open</a> <a id="9823" class="Keyword">import</a> <a id="9830" href="elementary-number-theory.well-ordering-principle-standard-finite-types.html" class="Module">elementary-number-theory.well-ordering-principle-standard-finite-types</a>
</pre>
## Finite group theory

<pre class="Agda"><a id="9938" class="Keyword">open</a> <a id="9943" class="Keyword">import</a> <a id="9950" href="finite-group-theory.html" class="Module">finite-group-theory</a>
<a id="9970" class="Keyword">open</a> <a id="9975" class="Keyword">import</a> <a id="9982" href="finite-group-theory.abstract-quaternion-group.html" class="Module">finite-group-theory.abstract-quaternion-group</a>
<a id="10028" class="Keyword">open</a> <a id="10033" class="Keyword">import</a> <a id="10040" href="finite-group-theory.concrete-quaternion-group.html" class="Module">finite-group-theory.concrete-quaternion-group</a>
<a id="10086" class="Keyword">open</a> <a id="10091" class="Keyword">import</a> <a id="10098" href="finite-group-theory.finite-groups.html" class="Module">finite-group-theory.finite-groups</a>
<a id="10132" class="Keyword">open</a> <a id="10137" class="Keyword">import</a> <a id="10144" href="finite-group-theory.finite-monoids.html" class="Module">finite-group-theory.finite-monoids</a>
<a id="10179" class="Keyword">open</a> <a id="10184" class="Keyword">import</a> <a id="10191" href="finite-group-theory.finite-semigroups.html" class="Module">finite-group-theory.finite-semigroups</a>
<a id="10229" class="Keyword">open</a> <a id="10234" class="Keyword">import</a> <a id="10241" href="finite-group-theory.groups-of-order-2.html" class="Module">finite-group-theory.groups-of-order-2</a>
<a id="10279" class="Keyword">open</a> <a id="10284" class="Keyword">import</a> <a id="10291" href="finite-group-theory.orbits-permutations.html" class="Module">finite-group-theory.orbits-permutations</a>
<a id="10331" class="Keyword">open</a> <a id="10336" class="Keyword">import</a> <a id="10343" href="finite-group-theory.permutations.html" class="Module">finite-group-theory.permutations</a>
<a id="10376" class="Keyword">open</a> <a id="10381" class="Keyword">import</a> <a id="10388" href="finite-group-theory.sign-homomorphism.html" class="Module">finite-group-theory.sign-homomorphism</a>
<a id="10426" class="Keyword">open</a> <a id="10431" class="Keyword">import</a> <a id="10438" href="finite-group-theory.transpositions.html" class="Module">finite-group-theory.transpositions</a>
</pre>
## Foundation

<pre class="Agda"><a id="10501" class="Keyword">open</a> <a id="10506" class="Keyword">import</a> <a id="10513" href="foundation.html" class="Module">foundation</a>
<a id="10524" class="Keyword">open</a> <a id="10529" class="Keyword">import</a> <a id="10536" href="foundation.0-maps.html" class="Module">foundation.0-maps</a>
<a id="10554" class="Keyword">open</a> <a id="10559" class="Keyword">import</a> <a id="10566" href="foundation.1-types.html" class="Module">foundation.1-types</a>
<a id="10585" class="Keyword">open</a> <a id="10590" class="Keyword">import</a> <a id="10597" href="foundation.2-types.html" class="Module">foundation.2-types</a>
<a id="10616" class="Keyword">open</a> <a id="10621" class="Keyword">import</a> <a id="10628" href="foundation.algebras-polynomial-endofunctors.html" class="Module">foundation.algebras-polynomial-endofunctors</a>
<a id="10672" class="Keyword">open</a> <a id="10677" class="Keyword">import</a> <a id="10684" href="foundation.automorphisms.html" class="Module">foundation.automorphisms</a>
<a id="10709" class="Keyword">open</a> <a id="10714" class="Keyword">import</a> <a id="10721" href="foundation.axiom-of-choice.html" class="Module">foundation.axiom-of-choice</a>
<a id="10748" class="Keyword">open</a> <a id="10753" class="Keyword">import</a> <a id="10760" href="foundation.bands.html" class="Module">foundation.bands</a>
<a id="10777" class="Keyword">open</a> <a id="10782" class="Keyword">import</a> <a id="10789" href="foundation.binary-embeddings.html" class="Module">foundation.binary-embeddings</a>
<a id="10818" class="Keyword">open</a> <a id="10823" class="Keyword">import</a> <a id="10830" href="foundation.binary-equivalences-unordered-pairs-of-types.html" class="Module">foundation.binary-equivalences-unordered-pairs-of-types</a>
<a id="10886" class="Keyword">open</a> <a id="10891" class="Keyword">import</a> <a id="10898" href="foundation.binary-equivalences.html" class="Module">foundation.binary-equivalences</a>
<a id="10929" class="Keyword">open</a> <a id="10934" class="Keyword">import</a> <a id="10941" href="foundation.binary-operations-unordered-pairs-of-types.html" class="Module">foundation.binary-operations-unordered-pairs-of-types</a>
<a id="10995" class="Keyword">open</a> <a id="11000" class="Keyword">import</a> <a id="11007" href="foundation.binary-relations.html" class="Module">foundation.binary-relations</a>
<a id="11035" class="Keyword">open</a> <a id="11040" class="Keyword">import</a> <a id="11047" href="foundation.boolean-reflection.html" class="Module">foundation.boolean-reflection</a>
<a id="11077" class="Keyword">open</a> <a id="11082" class="Keyword">import</a> <a id="11089" href="foundation.booleans.html" class="Module">foundation.booleans</a>
<a id="11109" class="Keyword">open</a> <a id="11114" class="Keyword">import</a> <a id="11121" href="foundation.cantors-diagonal-argument.html" class="Module">foundation.cantors-diagonal-argument</a>
<a id="11158" class="Keyword">open</a> <a id="11163" class="Keyword">import</a> <a id="11170" href="foundation.cartesian-product-types.html" class="Module">foundation.cartesian-product-types</a>
<a id="11205" class="Keyword">open</a> <a id="11210" class="Keyword">import</a> <a id="11217" href="foundation.choice-of-representatives-equivalence-relation.html" class="Module">foundation.choice-of-representatives-equivalence-relation</a>
<a id="11275" class="Keyword">open</a> <a id="11280" class="Keyword">import</a> <a id="11287" href="foundation.coherently-invertible-maps.html" class="Module">foundation.coherently-invertible-maps</a>
<a id="11325" class="Keyword">open</a> <a id="11330" class="Keyword">import</a> <a id="11337" href="foundation.commutative-operations.html" class="Module">foundation.commutative-operations</a>
<a id="11371" class="Keyword">open</a> <a id="11376" class="Keyword">import</a> <a id="11383" href="foundation.commuting-squares.html" class="Module">foundation.commuting-squares</a>
<a id="11412" class="Keyword">open</a> <a id="11417" class="Keyword">import</a> <a id="11424" href="foundation.complements.html" class="Module">foundation.complements</a>
<a id="11447" class="Keyword">open</a> <a id="11452" class="Keyword">import</a> <a id="11459" href="foundation.cones-pullbacks.html" class="Module">foundation.cones-pullbacks</a>
<a id="11486" class="Keyword">open</a> <a id="11491" class="Keyword">import</a> <a id="11498" href="foundation.conjunction.html" class="Module">foundation.conjunction</a>
<a id="11521" class="Keyword">open</a> <a id="11526" class="Keyword">import</a> <a id="11533" href="foundation.connected-components-universes.html" class="Module">foundation.connected-components-universes</a>
<a id="11575" class="Keyword">open</a> <a id="11580" class="Keyword">import</a> <a id="11587" href="foundation.connected-components.html" class="Module">foundation.connected-components</a>
<a id="11619" class="Keyword">open</a> <a id="11624" class="Keyword">import</a> <a id="11631" href="foundation.connected-types.html" class="Module">foundation.connected-types</a>
<a id="11658" class="Keyword">open</a> <a id="11663" class="Keyword">import</a> <a id="11670" href="foundation.constant-maps.html" class="Module">foundation.constant-maps</a>
<a id="11695" class="Keyword">open</a> <a id="11700" class="Keyword">import</a> <a id="11707" href="foundation.contractible-maps.html" class="Module">foundation.contractible-maps</a>
<a id="11736" class="Keyword">open</a> <a id="11741" class="Keyword">import</a> <a id="11748" href="foundation.contractible-types.html" class="Module">foundation.contractible-types</a>
<a id="11778" class="Keyword">open</a> <a id="11783" class="Keyword">import</a> <a id="11790" href="foundation.coproduct-types.html" class="Module">foundation.coproduct-types</a>
<a id="11817" class="Keyword">open</a> <a id="11822" class="Keyword">import</a> <a id="11829" href="foundation.coslice.html" class="Module">foundation.coslice</a>
<a id="11848" class="Keyword">open</a> <a id="11853" class="Keyword">import</a> <a id="11860" href="foundation.decidable-dependent-function-types.html" class="Module">foundation.decidable-dependent-function-types</a>
<a id="11906" class="Keyword">open</a> <a id="11911" class="Keyword">import</a> <a id="11918" href="foundation.decidable-dependent-pair-types.html" class="Module">foundation.decidable-dependent-pair-types</a>
<a id="11960" class="Keyword">open</a> <a id="11965" class="Keyword">import</a> <a id="11972" href="foundation.decidable-embeddings.html" class="Module">foundation.decidable-embeddings</a>
<a id="12004" class="Keyword">open</a> <a id="12009" class="Keyword">import</a> <a id="12016" href="foundation.decidable-equality.html" class="Module">foundation.decidable-equality</a>
<a id="12046" class="Keyword">open</a> <a id="12051" class="Keyword">import</a> <a id="12058" href="foundation.decidable-maps.html" class="Module">foundation.decidable-maps</a>
<a id="12084" class="Keyword">open</a> <a id="12089" class="Keyword">import</a> <a id="12096" href="foundation.decidable-propositions.html" class="Module">foundation.decidable-propositions</a>
<a id="12130" class="Keyword">open</a> <a id="12135" class="Keyword">import</a> <a id="12142" href="foundation.decidable-subtypes.html" class="Module">foundation.decidable-subtypes</a>
<a id="12172" class="Keyword">open</a> <a id="12177" class="Keyword">import</a> <a id="12184" href="foundation.decidable-types.html" class="Module">foundation.decidable-types</a>
<a id="12211" class="Keyword">open</a> <a id="12216" class="Keyword">import</a> <a id="12223" href="foundation.dependent-pair-types.html" class="Module">foundation.dependent-pair-types</a>
<a id="12255" class="Keyword">open</a> <a id="12260" class="Keyword">import</a> <a id="12267" href="foundation.diagonal-maps-of-types.html" class="Module">foundation.diagonal-maps-of-types</a>
<a id="12301" class="Keyword">open</a> <a id="12306" class="Keyword">import</a> <a id="12313" href="foundation.disjunction.html" class="Module">foundation.disjunction</a>
<a id="12336" class="Keyword">open</a> <a id="12341" class="Keyword">import</a> <a id="12348" href="foundation.distributivity-of-dependent-functions-over-coproduct-types.html" class="Module">foundation.distributivity-of-dependent-functions-over-coproduct-types</a>
<a id="12418" class="Keyword">open</a> <a id="12423" class="Keyword">import</a> <a id="12430" href="foundation.distributivity-of-dependent-functions-over-dependent-pairs.html" class="Module">foundation.distributivity-of-dependent-functions-over-dependent-pairs</a>
<a id="12500" class="Keyword">open</a> <a id="12505" class="Keyword">import</a> <a id="12512" href="foundation.double-negation.html" class="Module">foundation.double-negation</a>
<a id="12539" class="Keyword">open</a> <a id="12544" class="Keyword">import</a> <a id="12551" href="foundation.double-powersets.html" class="Module">foundation.double-powersets</a>
<a id="12579" class="Keyword">open</a> <a id="12584" class="Keyword">import</a> <a id="12591" href="foundation.dubuc-penon-compact-types.html" class="Module">foundation.dubuc-penon-compact-types</a>
<a id="12628" class="Keyword">open</a> <a id="12633" class="Keyword">import</a> <a id="12640" href="foundation.effective-maps-equivalence-relations.html" class="Module">foundation.effective-maps-equivalence-relations</a>
<a id="12688" class="Keyword">open</a> <a id="12693" class="Keyword">import</a> <a id="12700" href="foundation.elementhood-relation-w-types.html" class="Module">foundation.elementhood-relation-w-types</a>
<a id="12740" class="Keyword">open</a> <a id="12745" class="Keyword">import</a> <a id="12752" href="foundation.embeddings.html" class="Module">foundation.embeddings</a>
<a id="12774" class="Keyword">open</a> <a id="12779" class="Keyword">import</a> <a id="12786" href="foundation.empty-types.html" class="Module">foundation.empty-types</a>
<a id="12809" class="Keyword">open</a> <a id="12814" class="Keyword">import</a> <a id="12821" href="foundation.endomorphisms.html" class="Module">foundation.endomorphisms</a>
<a id="12846" class="Keyword">open</a> <a id="12851" class="Keyword">import</a> <a id="12858" href="foundation.epimorphisms-with-respect-to-sets.html" class="Module">foundation.epimorphisms-with-respect-to-sets</a>
<a id="12903" class="Keyword">open</a> <a id="12908" class="Keyword">import</a> <a id="12915" href="foundation.equality-cartesian-product-types.html" class="Module">foundation.equality-cartesian-product-types</a>
<a id="12959" class="Keyword">open</a> <a id="12964" class="Keyword">import</a> <a id="12971" href="foundation.equality-coproduct-types.html" class="Module">foundation.equality-coproduct-types</a>
<a id="13007" class="Keyword">open</a> <a id="13012" class="Keyword">import</a> <a id="13019" href="foundation.equality-dependent-function-types.html" class="Module">foundation.equality-dependent-function-types</a>
<a id="13064" class="Keyword">open</a> <a id="13069" class="Keyword">import</a> <a id="13076" href="foundation.equality-dependent-pair-types.html" class="Module">foundation.equality-dependent-pair-types</a>
<a id="13117" class="Keyword">open</a> <a id="13122" class="Keyword">import</a> <a id="13129" href="foundation.equality-fibers-of-maps.html" class="Module">foundation.equality-fibers-of-maps</a>
<a id="13164" class="Keyword">open</a> <a id="13169" class="Keyword">import</a> <a id="13176" href="foundation.equivalence-classes.html" class="Module">foundation.equivalence-classes</a>
<a id="13207" class="Keyword">open</a> <a id="13212" class="Keyword">import</a> <a id="13219" href="foundation.equivalence-induction.html" class="Module">foundation.equivalence-induction</a>
<a id="13252" class="Keyword">open</a> <a id="13257" class="Keyword">import</a> <a id="13264" href="foundation.equivalence-relations.html" class="Module">foundation.equivalence-relations</a>
<a id="13297" class="Keyword">open</a> <a id="13302" class="Keyword">import</a> <a id="13309" href="foundation.equivalences-maybe.html" class="Module">foundation.equivalences-maybe</a>
<a id="13339" class="Keyword">open</a> <a id="13344" class="Keyword">import</a> <a id="13351" href="foundation.equivalences.html" class="Module">foundation.equivalences</a>
<a id="13375" class="Keyword">open</a> <a id="13380" class="Keyword">import</a> <a id="13387" href="foundation.existential-quantification.html" class="Module">foundation.existential-quantification</a>
<a id="13425" class="Keyword">open</a> <a id="13430" class="Keyword">import</a> <a id="13437" href="foundation.extensional-w-types.html" class="Module">foundation.extensional-w-types</a>
<a id="13468" class="Keyword">open</a> <a id="13473" class="Keyword">import</a> <a id="13480" href="foundation.faithful-maps.html" class="Module">foundation.faithful-maps</a>
<a id="13505" class="Keyword">open</a> <a id="13510" class="Keyword">import</a> <a id="13517" href="foundation.fiber-inclusions.html" class="Module">foundation.fiber-inclusions</a>
<a id="13545" class="Keyword">open</a> <a id="13550" class="Keyword">import</a> <a id="13557" href="foundation.fibered-maps.html" class="Module">foundation.fibered-maps</a>
<a id="13581" class="Keyword">open</a> <a id="13586" class="Keyword">import</a> <a id="13593" href="foundation.fibers-of-maps.html" class="Module">foundation.fibers-of-maps</a>
<a id="13619" class="Keyword">open</a> <a id="13624" class="Keyword">import</a> <a id="13631" href="foundation.function-extensionality.html" class="Module">foundation.function-extensionality</a>
<a id="13666" class="Keyword">open</a> <a id="13671" class="Keyword">import</a> <a id="13678" href="foundation.functions.html" class="Module">foundation.functions</a>
<a id="13699" class="Keyword">open</a> <a id="13704" class="Keyword">import</a> <a id="13711" href="foundation.functoriality-cartesian-product-types.html" class="Module">foundation.functoriality-cartesian-product-types</a>
<a id="13760" class="Keyword">open</a> <a id="13765" class="Keyword">import</a> <a id="13772" href="foundation.functoriality-coproduct-types.html" class="Module">foundation.functoriality-coproduct-types</a>
<a id="13813" class="Keyword">open</a> <a id="13818" class="Keyword">import</a> <a id="13825" href="foundation.functoriality-dependent-function-types.html" class="Module">foundation.functoriality-dependent-function-types</a>
<a id="13875" class="Keyword">open</a> <a id="13880" class="Keyword">import</a> <a id="13887" href="foundation.functoriality-dependent-pair-types.html" class="Module">foundation.functoriality-dependent-pair-types</a>
<a id="13933" class="Keyword">open</a> <a id="13938" class="Keyword">import</a> <a id="13945" href="foundation.functoriality-function-types.html" class="Module">foundation.functoriality-function-types</a>
<a id="13985" class="Keyword">open</a> <a id="13990" class="Keyword">import</a> <a id="13997" href="foundation.functoriality-propositional-truncation.html" class="Module">foundation.functoriality-propositional-truncation</a>
<a id="14047" class="Keyword">open</a> <a id="14052" class="Keyword">import</a> <a id="14059" href="foundation.functoriality-set-quotients.html" class="Module">foundation.functoriality-set-quotients</a>
<a id="14098" class="Keyword">open</a> <a id="14103" class="Keyword">import</a> <a id="14110" href="foundation.functoriality-set-truncation.html" class="Module">foundation.functoriality-set-truncation</a>
<a id="14150" class="Keyword">open</a> <a id="14155" class="Keyword">import</a> <a id="14162" href="foundation.functoriality-w-types.html" class="Module">foundation.functoriality-w-types</a>
<a id="14195" class="Keyword">open</a> <a id="14200" class="Keyword">import</a> <a id="14207" href="foundation.fundamental-theorem-of-identity-types.html" class="Module">foundation.fundamental-theorem-of-identity-types</a>
<a id="14256" class="Keyword">open</a> <a id="14261" class="Keyword">import</a> <a id="14268" href="foundation.global-choice.html" class="Module">foundation.global-choice</a>
<a id="14293" class="Keyword">open</a> <a id="14298" class="Keyword">import</a> <a id="14305" href="foundation.hilberts-epsilon-operators.html" class="Module">foundation.hilberts-epsilon-operators</a>
<a id="14343" class="Keyword">open</a> <a id="14348" class="Keyword">import</a> <a id="14355" href="foundation.homotopies.html" class="Module">foundation.homotopies</a>
<a id="14377" class="Keyword">open</a> <a id="14382" class="Keyword">import</a> <a id="14389" href="foundation.identity-systems.html" class="Module">foundation.identity-systems</a>
<a id="14417" class="Keyword">open</a> <a id="14422" class="Keyword">import</a> <a id="14429" href="foundation.identity-types.html" class="Module">foundation.identity-types</a>
<a id="14455" class="Keyword">open</a> <a id="14460" class="Keyword">import</a> <a id="14467" href="foundation.images.html" class="Module">foundation.images</a>
<a id="14485" class="Keyword">open</a> <a id="14490" class="Keyword">import</a> <a id="14497" href="foundation.impredicative-encodings.html" class="Module">foundation.impredicative-encodings</a>
<a id="14532" class="Keyword">open</a> <a id="14537" class="Keyword">import</a> <a id="14544" href="foundation.indexed-w-types.html" class="Module">foundation.indexed-w-types</a>
<a id="14571" class="Keyword">open</a> <a id="14576" class="Keyword">import</a> <a id="14583" href="foundation.induction-principle-propositional-truncation.html" class="Module">foundation.induction-principle-propositional-truncation</a>
<a id="14639" class="Keyword">open</a> <a id="14644" class="Keyword">import</a> <a id="14651" href="foundation.induction-w-types.html" class="Module">foundation.induction-w-types</a>
<a id="14680" class="Keyword">open</a> <a id="14685" class="Keyword">import</a> <a id="14692" href="foundation.inequality-w-types.html" class="Module">foundation.inequality-w-types</a>
<a id="14722" class="Keyword">open</a> <a id="14727" class="Keyword">import</a> <a id="14734" href="foundation.inhabited-types.html" class="Module">foundation.inhabited-types</a>
<a id="14761" class="Keyword">open</a> <a id="14766" class="Keyword">import</a> <a id="14773" href="foundation.injective-maps.html" class="Module">foundation.injective-maps</a>
<a id="14799" class="Keyword">open</a> <a id="14804" class="Keyword">import</a> <a id="14811" href="foundation.interchange-law.html" class="Module">foundation.interchange-law</a>
<a id="14838" class="Keyword">open</a> <a id="14843" class="Keyword">import</a> <a id="14850" href="foundation.intersection.html" class="Module">foundation.intersection</a>
<a id="14874" class="Keyword">open</a> <a id="14879" class="Keyword">import</a> <a id="14886" href="foundation.involutions.html" class="Module">foundation.involutions</a>
<a id="14909" class="Keyword">open</a> <a id="14914" class="Keyword">import</a> <a id="14921" href="foundation.isolated-points.html" class="Module">foundation.isolated-points</a>
<a id="14948" class="Keyword">open</a> <a id="14953" class="Keyword">import</a> <a id="14960" href="foundation.isomorphisms-of-sets.html" class="Module">foundation.isomorphisms-of-sets</a>
<a id="14992" class="Keyword">open</a> <a id="14997" class="Keyword">import</a> <a id="15004" href="foundation.iterating-automorphisms.html" class="Module">foundation.iterating-automorphisms</a>
<a id="15039" class="Keyword">open</a> <a id="15044" class="Keyword">import</a> <a id="15051" href="foundation.iterating-functions.html" class="Module">foundation.iterating-functions</a>
<a id="15082" class="Keyword">open</a> <a id="15087" class="Keyword">import</a> <a id="15094" href="foundation.iterating-involutions.html" class="Module">foundation.iterating-involutions</a>
<a id="15127" class="Keyword">open</a> <a id="15132" class="Keyword">import</a> <a id="15139" href="foundation.law-of-excluded-middle.html" class="Module">foundation.law-of-excluded-middle</a>
<a id="15173" class="Keyword">open</a> <a id="15178" class="Keyword">import</a> <a id="15185" href="foundation.lawveres-fixed-point-theorem.html" class="Module">foundation.lawveres-fixed-point-theorem</a>
<a id="15225" class="Keyword">open</a> <a id="15230" class="Keyword">import</a> <a id="15237" href="foundation.locally-small-types.html" class="Module">foundation.locally-small-types</a>
<a id="15268" class="Keyword">open</a> <a id="15273" class="Keyword">import</a> <a id="15280" href="foundation.logical-equivalences.html" class="Module">foundation.logical-equivalences</a>
<a id="15312" class="Keyword">open</a> <a id="15317" class="Keyword">import</a> <a id="15324" href="foundation.lower-types-w-types.html" class="Module">foundation.lower-types-w-types</a>
<a id="15355" class="Keyword">open</a> <a id="15360" class="Keyword">import</a> <a id="15367" href="foundation.maybe.html" class="Module">foundation.maybe</a>
<a id="15384" class="Keyword">open</a> <a id="15389" class="Keyword">import</a> <a id="15396" href="foundation.mere-equality.html" class="Module">foundation.mere-equality</a>
<a id="15421" class="Keyword">open</a> <a id="15426" class="Keyword">import</a> <a id="15433" href="foundation.mere-equivalences.html" class="Module">foundation.mere-equivalences</a>
<a id="15462" class="Keyword">open</a> <a id="15467" class="Keyword">import</a> <a id="15474" href="foundation.monomorphisms.html" class="Module">foundation.monomorphisms</a>
<a id="15499" class="Keyword">open</a> <a id="15504" class="Keyword">import</a> <a id="15511" href="foundation.multisets.html" class="Module">foundation.multisets</a>
<a id="15532" class="Keyword">open</a> <a id="15537" class="Keyword">import</a> <a id="15544" href="foundation.multisubsets.html" class="Module">foundation.multisubsets</a>
<a id="15568" class="Keyword">open</a> <a id="15573" class="Keyword">import</a> <a id="15580" href="foundation.negation.html" class="Module">foundation.negation</a>
<a id="15600" class="Keyword">open</a> <a id="15605" class="Keyword">import</a> <a id="15612" href="foundation.non-contractible-types.html" class="Module">foundation.non-contractible-types</a>
<a id="15646" class="Keyword">open</a> <a id="15651" class="Keyword">import</a> <a id="15658" href="foundation.pairs-of-distinct-elements.html" class="Module">foundation.pairs-of-distinct-elements</a>
<a id="15696" class="Keyword">open</a> <a id="15701" class="Keyword">import</a> <a id="15708" href="foundation.path-algebra.html" class="Module">foundation.path-algebra</a>
<a id="15732" class="Keyword">open</a> <a id="15737" class="Keyword">import</a> <a id="15744" href="foundation.path-split-maps.html" class="Module">foundation.path-split-maps</a>
<a id="15771" class="Keyword">open</a> <a id="15776" class="Keyword">import</a> <a id="15783" href="foundation.polynomial-endofunctors.html" class="Module">foundation.polynomial-endofunctors</a>
<a id="15818" class="Keyword">open</a> <a id="15823" class="Keyword">import</a> <a id="15830" href="foundation.powersets.html" class="Module">foundation.powersets</a>
<a id="15851" class="Keyword">open</a> <a id="15856" class="Keyword">import</a> <a id="15863" href="foundation.principle-of-omniscience.html" class="Module">foundation.principle-of-omniscience</a>
<a id="15899" class="Keyword">open</a> <a id="15904" class="Keyword">import</a> <a id="15911" href="foundation.products-unordered-pairs-of-types.html" class="Module">foundation.products-unordered-pairs-of-types</a>
<a id="15956" class="Keyword">open</a> <a id="15961" class="Keyword">import</a> <a id="15968" href="foundation.products-unordered-tuples-of-types.html" class="Module">foundation.products-unordered-tuples-of-types</a>
<a id="16014" class="Keyword">open</a> <a id="16019" class="Keyword">import</a> <a id="16026" href="foundation.propositional-extensionality.html" class="Module">foundation.propositional-extensionality</a>
<a id="16066" class="Keyword">open</a> <a id="16071" class="Keyword">import</a> <a id="16078" href="foundation.propositional-maps.html" class="Module">foundation.propositional-maps</a>
<a id="16108" class="Keyword">open</a> <a id="16113" class="Keyword">import</a> <a id="16120" href="foundation.propositional-truncations.html" class="Module">foundation.propositional-truncations</a>
<a id="16157" class="Keyword">open</a> <a id="16162" class="Keyword">import</a> <a id="16169" href="foundation.propositions.html" class="Module">foundation.propositions</a>
<a id="16193" class="Keyword">open</a> <a id="16198" class="Keyword">import</a> <a id="16205" href="foundation.pullbacks.html" class="Module">foundation.pullbacks</a>
<a id="16226" class="Keyword">open</a> <a id="16231" class="Keyword">import</a> <a id="16238" href="foundation.raising-universe-levels.html" class="Module">foundation.raising-universe-levels</a>
<a id="16273" class="Keyword">open</a> <a id="16278" class="Keyword">import</a> <a id="16285" href="foundation.ranks-of-elements-w-types.html" class="Module">foundation.ranks-of-elements-w-types</a>
<a id="16322" class="Keyword">open</a> <a id="16327" class="Keyword">import</a> <a id="16334" href="foundation.reflecting-maps-equivalence-relations.html" class="Module">foundation.reflecting-maps-equivalence-relations</a>
<a id="16383" class="Keyword">open</a> <a id="16388" class="Keyword">import</a> <a id="16395" href="foundation.repetitions-sequences.html" class="Module">foundation.repetitions-sequences</a>
<a id="16428" class="Keyword">open</a> <a id="16433" class="Keyword">import</a> <a id="16440" href="foundation.repetitions.html" class="Module">foundation.repetitions</a>
<a id="16463" class="Keyword">open</a> <a id="16468" class="Keyword">import</a> <a id="16475" href="foundation.replacement.html" class="Module">foundation.replacement</a>
<a id="16498" class="Keyword">open</a> <a id="16503" class="Keyword">import</a> <a id="16510" href="foundation.retractions.html" class="Module">foundation.retractions</a>
<a id="16533" class="Keyword">open</a> <a id="16538" class="Keyword">import</a> <a id="16545" href="foundation.russells-paradox.html" class="Module">foundation.russells-paradox</a>
<a id="16573" class="Keyword">open</a> <a id="16578" class="Keyword">import</a> <a id="16585" href="foundation.sections.html" class="Module">foundation.sections</a>
<a id="16605" class="Keyword">open</a> <a id="16610" class="Keyword">import</a> <a id="16617" href="foundation.sequences.html" class="Module">foundation.sequences</a>
<a id="16638" class="Keyword">open</a> <a id="16643" class="Keyword">import</a> <a id="16650" href="foundation.set-presented-types.html" class="Module">foundation.set-presented-types</a>
<a id="16681" class="Keyword">open</a> <a id="16686" class="Keyword">import</a> <a id="16693" href="foundation.set-truncations.html" class="Module">foundation.set-truncations</a>
<a id="16720" class="Keyword">open</a> <a id="16725" class="Keyword">import</a> <a id="16732" href="foundation.sets.html" class="Module">foundation.sets</a>
<a id="16748" class="Keyword">open</a> <a id="16753" class="Keyword">import</a> <a id="16760" href="foundation.singleton-induction.html" class="Module">foundation.singleton-induction</a>
<a id="16791" class="Keyword">open</a> <a id="16796" class="Keyword">import</a> <a id="16803" href="foundation.slice.html" class="Module">foundation.slice</a>
<a id="16820" class="Keyword">open</a> <a id="16825" class="Keyword">import</a> <a id="16832" href="foundation.small-maps.html" class="Module">foundation.small-maps</a>
<a id="16854" class="Keyword">open</a> <a id="16859" class="Keyword">import</a> <a id="16866" href="foundation.small-multisets.html" class="Module">foundation.small-multisets</a>
<a id="16893" class="Keyword">open</a> <a id="16898" class="Keyword">import</a> <a id="16905" href="foundation.small-types.html" class="Module">foundation.small-types</a>
<a id="16928" class="Keyword">open</a> <a id="16933" class="Keyword">import</a> <a id="16940" href="foundation.small-universes.html" class="Module">foundation.small-universes</a>
<a id="16967" class="Keyword">open</a> <a id="16972" class="Keyword">import</a> <a id="16979" href="foundation.split-surjective-maps.html" class="Module">foundation.split-surjective-maps</a>
<a id="17012" class="Keyword">open</a> <a id="17017" class="Keyword">import</a> <a id="17024" href="foundation.structure-identity-principle.html" class="Module">foundation.structure-identity-principle</a>
<a id="17064" class="Keyword">open</a> <a id="17069" class="Keyword">import</a> <a id="17076" href="foundation.structure.html" class="Module">foundation.structure</a>
<a id="17097" class="Keyword">open</a> <a id="17102" class="Keyword">import</a> <a id="17109" href="foundation.subterminal-types.html" class="Module">foundation.subterminal-types</a>
<a id="17138" class="Keyword">open</a> <a id="17143" class="Keyword">import</a> <a id="17150" href="foundation.subtype-identity-principle.html" class="Module">foundation.subtype-identity-principle</a>
<a id="17188" class="Keyword">open</a> <a id="17193" class="Keyword">import</a> <a id="17200" href="foundation.subtypes.html" class="Module">foundation.subtypes</a>
<a id="17220" class="Keyword">open</a> <a id="17225" class="Keyword">import</a> <a id="17232" href="foundation.subuniverses.html" class="Module">foundation.subuniverses</a>
<a id="17256" class="Keyword">open</a> <a id="17261" class="Keyword">import</a> <a id="17268" href="foundation.surjective-maps.html" class="Module">foundation.surjective-maps</a>
<a id="17295" class="Keyword">open</a> <a id="17300" class="Keyword">import</a> <a id="17307" href="foundation.symmetric-difference.html" class="Module">foundation.symmetric-difference</a>
<a id="17339" class="Keyword">open</a> <a id="17344" class="Keyword">import</a> <a id="17351" href="foundation.truncated-equality.html" class="Module">foundation.truncated-equality</a>
<a id="17381" class="Keyword">open</a> <a id="17386" class="Keyword">import</a> <a id="17393" href="foundation.truncated-maps.html" class="Module">foundation.truncated-maps</a>
<a id="17419" class="Keyword">open</a> <a id="17424" class="Keyword">import</a> <a id="17431" href="foundation.truncated-types.html" class="Module">foundation.truncated-types</a>
<a id="17458" class="Keyword">open</a> <a id="17463" class="Keyword">import</a> <a id="17470" href="foundation.truncation-levels.html" class="Module">foundation.truncation-levels</a>
<a id="17499" class="Keyword">open</a> <a id="17504" class="Keyword">import</a> <a id="17511" href="foundation.truncations.html" class="Module">foundation.truncations</a>
<a id="17534" class="Keyword">open</a> <a id="17539" class="Keyword">import</a> <a id="17546" href="foundation.type-arithmetic-cartesian-product-types.html" class="Module">foundation.type-arithmetic-cartesian-product-types</a>
<a id="17597" class="Keyword">open</a> <a id="17602" class="Keyword">import</a> <a id="17609" href="foundation.type-arithmetic-coproduct-types.html" class="Module">foundation.type-arithmetic-coproduct-types</a>
<a id="17652" class="Keyword">open</a> <a id="17657" class="Keyword">import</a> <a id="17664" href="foundation.type-arithmetic-dependent-pair-types.html" class="Module">foundation.type-arithmetic-dependent-pair-types</a>
<a id="17712" class="Keyword">open</a> <a id="17717" class="Keyword">import</a> <a id="17724" href="foundation.type-arithmetic-empty-type.html" class="Module">foundation.type-arithmetic-empty-type</a>
<a id="17762" class="Keyword">open</a> <a id="17767" class="Keyword">import</a> <a id="17774" href="foundation.type-arithmetic-unit-type.html" class="Module">foundation.type-arithmetic-unit-type</a>
<a id="17811" class="Keyword">open</a> <a id="17816" class="Keyword">import</a> <a id="17823" href="foundation.union.html" class="Module">foundation.union</a>
<a id="17840" class="Keyword">open</a> <a id="17845" class="Keyword">import</a> <a id="17852" href="foundation.uniqueness-image.html" class="Module">foundation.uniqueness-image</a>
<a id="17880" class="Keyword">open</a> <a id="17885" class="Keyword">import</a> <a id="17892" href="foundation.uniqueness-set-quotients.html" class="Module">foundation.uniqueness-set-quotients</a>
<a id="17928" class="Keyword">open</a> <a id="17933" class="Keyword">import</a> <a id="17940" href="foundation.uniqueness-set-truncations.html" class="Module">foundation.uniqueness-set-truncations</a>
<a id="17978" class="Keyword">open</a> <a id="17983" class="Keyword">import</a> <a id="17990" href="foundation.uniqueness-truncation.html" class="Module">foundation.uniqueness-truncation</a>
<a id="18023" class="Keyword">open</a> <a id="18028" class="Keyword">import</a> <a id="18035" href="foundation.unit-type.html" class="Module">foundation.unit-type</a>
<a id="18056" class="Keyword">open</a> <a id="18061" class="Keyword">import</a> <a id="18068" href="foundation.univalence-implies-function-extensionality.html" class="Module">foundation.univalence-implies-function-extensionality</a>
<a id="18122" class="Keyword">open</a> <a id="18127" class="Keyword">import</a> <a id="18134" href="foundation.univalence.html" class="Module">foundation.univalence</a>
<a id="18156" class="Keyword">open</a> <a id="18161" class="Keyword">import</a> <a id="18168" href="foundation.univalent-type-families.html" class="Module">foundation.univalent-type-families</a>
<a id="18203" class="Keyword">open</a> <a id="18208" class="Keyword">import</a> <a id="18215" href="foundation.universal-multiset.html" class="Module">foundation.universal-multiset</a>
<a id="18245" class="Keyword">open</a> <a id="18250" class="Keyword">import</a> <a id="18257" href="foundation.universal-property-booleans.html" class="Module">foundation.universal-property-booleans</a>
<a id="18296" class="Keyword">open</a> <a id="18301" class="Keyword">import</a> <a id="18308" href="foundation.universal-property-cartesian-product-types.html" class="Module">foundation.universal-property-cartesian-product-types</a>
<a id="18362" class="Keyword">open</a> <a id="18367" class="Keyword">import</a> <a id="18374" href="foundation.universal-property-coproduct-types.html" class="Module">foundation.universal-property-coproduct-types</a>
<a id="18420" class="Keyword">open</a> <a id="18425" class="Keyword">import</a> <a id="18432" href="foundation.universal-property-dependent-pair-types.html" class="Module">foundation.universal-property-dependent-pair-types</a>
<a id="18483" class="Keyword">open</a> <a id="18488" class="Keyword">import</a> <a id="18495" href="foundation.universal-property-empty-type.html" class="Module">foundation.universal-property-empty-type</a>
<a id="18536" class="Keyword">open</a> <a id="18541" class="Keyword">import</a> <a id="18548" href="foundation.universal-property-fiber-products.html" class="Module">foundation.universal-property-fiber-products</a>
<a id="18593" class="Keyword">open</a> <a id="18598" class="Keyword">import</a> <a id="18605" href="foundation.universal-property-identity-types.html" class="Module">foundation.universal-property-identity-types</a>
<a id="18650" class="Keyword">open</a> <a id="18655" class="Keyword">import</a> <a id="18662" href="foundation.universal-property-image.html" class="Module">foundation.universal-property-image</a>
<a id="18698" class="Keyword">open</a> <a id="18703" class="Keyword">import</a> <a id="18710" href="foundation.universal-property-maybe.html" class="Module">foundation.universal-property-maybe</a>
<a id="18746" class="Keyword">open</a> <a id="18751" class="Keyword">import</a> <a id="18758" href="foundation.universal-property-propositional-truncation-into-sets.html" class="Module">foundation.universal-property-propositional-truncation-into-sets</a>
<a id="18823" class="Keyword">open</a> <a id="18828" class="Keyword">import</a> <a id="18835" href="foundation.universal-property-propositional-truncation.html" class="Module">foundation.universal-property-propositional-truncation</a>
<a id="18890" class="Keyword">open</a> <a id="18895" class="Keyword">import</a> <a id="18902" href="foundation.universal-property-pullbacks.html" class="Module">foundation.universal-property-pullbacks</a>
<a id="18942" class="Keyword">open</a> <a id="18947" class="Keyword">import</a> <a id="18954" href="foundation.universal-property-set-quotients.html" class="Module">foundation.universal-property-set-quotients</a>
<a id="18998" class="Keyword">open</a> <a id="19003" class="Keyword">import</a> <a id="19010" href="foundation.universal-property-set-truncation.html" class="Module">foundation.universal-property-set-truncation</a>
<a id="19055" class="Keyword">open</a> <a id="19060" class="Keyword">import</a> <a id="19067" href="foundation.universal-property-truncation.html" class="Module">foundation.universal-property-truncation</a>
<a id="19108" class="Keyword">open</a> <a id="19113" class="Keyword">import</a> <a id="19120" href="foundation.universal-property-unit-type.html" class="Module">foundation.universal-property-unit-type</a>
<a id="19160" class="Keyword">open</a> <a id="19165" class="Keyword">import</a> <a id="19172" href="foundation.universe-levels.html" class="Module">foundation.universe-levels</a>
<a id="19199" class="Keyword">open</a> <a id="19204" class="Keyword">import</a> <a id="19211" href="foundation.unordered-pairs-of-types.html" class="Module">foundation.unordered-pairs-of-types</a>
<a id="19247" class="Keyword">open</a> <a id="19252" class="Keyword">import</a> <a id="19259" href="foundation.unordered-pairs.html" class="Module">foundation.unordered-pairs</a>
<a id="19286" class="Keyword">open</a> <a id="19291" class="Keyword">import</a> <a id="19298" href="foundation.unordered-tuples-of-types.html" class="Module">foundation.unordered-tuples-of-types</a>
<a id="19335" class="Keyword">open</a> <a id="19340" class="Keyword">import</a> <a id="19347" href="foundation.unordered-tuples.html" class="Module">foundation.unordered-tuples</a>
<a id="19375" class="Keyword">open</a> <a id="19380" class="Keyword">import</a> <a id="19387" href="foundation.w-types.html" class="Module">foundation.w-types</a>
<a id="19406" class="Keyword">open</a> <a id="19411" class="Keyword">import</a> <a id="19418" href="foundation.weak-function-extensionality.html" class="Module">foundation.weak-function-extensionality</a>
<a id="19458" class="Keyword">open</a> <a id="19463" class="Keyword">import</a> <a id="19470" href="foundation.weakly-constant-maps.html" class="Module">foundation.weakly-constant-maps</a>
<a id="19502" class="Keyword">open</a> <a id="19507" class="Keyword">import</a> <a id="19514" href="foundation.xor.html" class="Module">foundation.xor</a>
</pre>
## Foundation Core

<pre class="Agda"><a id="19562" class="Keyword">open</a> <a id="19567" class="Keyword">import</a> <a id="19574" href="foundation-core.0-maps.html" class="Module">foundation-core.0-maps</a>
<a id="19597" class="Keyword">open</a> <a id="19602" class="Keyword">import</a> <a id="19609" href="foundation-core.1-types.html" class="Module">foundation-core.1-types</a>
<a id="19633" class="Keyword">open</a> <a id="19638" class="Keyword">import</a> <a id="19645" href="foundation-core.cartesian-product-types.html" class="Module">foundation-core.cartesian-product-types</a>
<a id="19685" class="Keyword">open</a> <a id="19690" class="Keyword">import</a> <a id="19697" href="foundation-core.coherently-invertible-maps.html" class="Module">foundation-core.coherently-invertible-maps</a>
<a id="19740" class="Keyword">open</a> <a id="19745" class="Keyword">import</a> <a id="19752" href="foundation-core.commuting-squares.html" class="Module">foundation-core.commuting-squares</a>
<a id="19786" class="Keyword">open</a> <a id="19791" class="Keyword">import</a> <a id="19798" href="foundation-core.cones-pullbacks.html" class="Module">foundation-core.cones-pullbacks</a>
<a id="19830" class="Keyword">open</a> <a id="19835" class="Keyword">import</a> <a id="19842" href="foundation-core.constant-maps.html" class="Module">foundation-core.constant-maps</a>
<a id="19872" class="Keyword">open</a> <a id="19877" class="Keyword">import</a> <a id="19884" href="foundation-core.contractible-maps.html" class="Module">foundation-core.contractible-maps</a>
<a id="19918" class="Keyword">open</a> <a id="19923" class="Keyword">import</a> <a id="19930" href="foundation-core.contractible-types.html" class="Module">foundation-core.contractible-types</a>
<a id="19965" class="Keyword">open</a> <a id="19970" class="Keyword">import</a> <a id="19977" href="foundation-core.dependent-pair-types.html" class="Module">foundation-core.dependent-pair-types</a>
<a id="20014" class="Keyword">open</a> <a id="20019" class="Keyword">import</a> <a id="20026" href="foundation-core.embeddings.html" class="Module">foundation-core.embeddings</a>
<a id="20053" class="Keyword">open</a> <a id="20058" class="Keyword">import</a> <a id="20065" href="foundation-core.empty-types.html" class="Module">foundation-core.empty-types</a>
<a id="20093" class="Keyword">open</a> <a id="20098" class="Keyword">import</a> <a id="20105" href="foundation-core.equality-cartesian-product-types.html" class="Module">foundation-core.equality-cartesian-product-types</a>
<a id="20154" class="Keyword">open</a> <a id="20159" class="Keyword">import</a> <a id="20166" href="foundation-core.equality-dependent-pair-types.html" class="Module">foundation-core.equality-dependent-pair-types</a>
<a id="20212" class="Keyword">open</a> <a id="20217" class="Keyword">import</a> <a id="20224" href="foundation-core.equality-fibers-of-maps.html" class="Module">foundation-core.equality-fibers-of-maps</a>
<a id="20264" class="Keyword">open</a> <a id="20269" class="Keyword">import</a> <a id="20276" href="foundation-core.equivalence-induction.html" class="Module">foundation-core.equivalence-induction</a>
<a id="20314" class="Keyword">open</a> <a id="20319" class="Keyword">import</a> <a id="20326" href="foundation-core.equivalences.html" class="Module">foundation-core.equivalences</a>
<a id="20355" class="Keyword">open</a> <a id="20360" class="Keyword">import</a> <a id="20367" href="foundation-core.faithful-maps.html" class="Module">foundation-core.faithful-maps</a>
<a id="20397" class="Keyword">open</a> <a id="20402" class="Keyword">import</a> <a id="20409" href="foundation-core.fibers-of-maps.html" class="Module">foundation-core.fibers-of-maps</a>
<a id="20440" class="Keyword">open</a> <a id="20445" class="Keyword">import</a> <a id="20452" href="foundation-core.function-extensionality.html" class="Module">foundation-core.function-extensionality</a>
<a id="20492" class="Keyword">open</a> <a id="20497" class="Keyword">import</a> <a id="20504" href="foundation-core.functions.html" class="Module">foundation-core.functions</a>
<a id="20530" class="Keyword">open</a> <a id="20535" class="Keyword">import</a> <a id="20542" href="foundation-core.functoriality-dependent-function-types.html" class="Module">foundation-core.functoriality-dependent-function-types</a>
<a id="20597" class="Keyword">open</a> <a id="20602" class="Keyword">import</a> <a id="20609" href="foundation-core.functoriality-dependent-pair-types.html" class="Module">foundation-core.functoriality-dependent-pair-types</a>
<a id="20660" class="Keyword">open</a> <a id="20665" class="Keyword">import</a> <a id="20672" href="foundation-core.functoriality-function-types.html" class="Module">foundation-core.functoriality-function-types</a>
<a id="20717" class="Keyword">open</a> <a id="20722" class="Keyword">import</a> <a id="20729" href="foundation-core.fundamental-theorem-of-identity-types.html" class="Module">foundation-core.fundamental-theorem-of-identity-types</a>
<a id="20783" class="Keyword">open</a> <a id="20788" class="Keyword">import</a> <a id="20795" href="foundation-core.homotopies.html" class="Module">foundation-core.homotopies</a>
<a id="20822" class="Keyword">open</a> <a id="20827" class="Keyword">import</a> <a id="20834" href="foundation-core.identity-systems.html" class="Module">foundation-core.identity-systems</a>
<a id="20867" class="Keyword">open</a> <a id="20872" class="Keyword">import</a> <a id="20879" href="foundation-core.identity-types.html" class="Module">foundation-core.identity-types</a>
<a id="20910" class="Keyword">open</a> <a id="20915" class="Keyword">import</a> <a id="20922" href="foundation-core.logical-equivalences.html" class="Module">foundation-core.logical-equivalences</a>
<a id="20959" class="Keyword">open</a> <a id="20964" class="Keyword">import</a> <a id="20971" href="foundation-core.negation.html" class="Module">foundation-core.negation</a>
<a id="20996" class="Keyword">open</a> <a id="21001" class="Keyword">import</a> <a id="21008" href="foundation-core.path-split-maps.html" class="Module">foundation-core.path-split-maps</a>
<a id="21040" class="Keyword">open</a> <a id="21045" class="Keyword">import</a> <a id="21052" href="foundation-core.propositional-maps.html" class="Module">foundation-core.propositional-maps</a>
<a id="21087" class="Keyword">open</a> <a id="21092" class="Keyword">import</a> <a id="21099" href="foundation-core.propositions.html" class="Module">foundation-core.propositions</a>
<a id="21128" class="Keyword">open</a> <a id="21133" class="Keyword">import</a> <a id="21140" href="foundation-core.pullbacks.html" class="Module">foundation-core.pullbacks</a>
<a id="21166" class="Keyword">open</a> <a id="21171" class="Keyword">import</a> <a id="21178" href="foundation-core.retractions.html" class="Module">foundation-core.retractions</a>
<a id="21206" class="Keyword">open</a> <a id="21211" class="Keyword">import</a> <a id="21218" href="foundation-core.sections.html" class="Module">foundation-core.sections</a>
<a id="21243" class="Keyword">open</a> <a id="21248" class="Keyword">import</a> <a id="21255" href="foundation-core.sets.html" class="Module">foundation-core.sets</a>
<a id="21276" class="Keyword">open</a> <a id="21281" class="Keyword">import</a> <a id="21288" href="foundation-core.singleton-induction.html" class="Module">foundation-core.singleton-induction</a>
<a id="21324" class="Keyword">open</a> <a id="21329" class="Keyword">import</a> <a id="21336" href="foundation-core.subtype-identity-principle.html" class="Module">foundation-core.subtype-identity-principle</a>
<a id="21379" class="Keyword">open</a> <a id="21384" class="Keyword">import</a> <a id="21391" href="foundation-core.subtypes.html" class="Module">foundation-core.subtypes</a>
<a id="21416" class="Keyword">open</a> <a id="21421" class="Keyword">import</a> <a id="21428" href="foundation-core.truncated-maps.html" class="Module">foundation-core.truncated-maps</a>
<a id="21459" class="Keyword">open</a> <a id="21464" class="Keyword">import</a> <a id="21471" href="foundation-core.truncated-types.html" class="Module">foundation-core.truncated-types</a>
<a id="21503" class="Keyword">open</a> <a id="21508" class="Keyword">import</a> <a id="21515" href="foundation-core.truncation-levels.html" class="Module">foundation-core.truncation-levels</a>
<a id="21549" class="Keyword">open</a> <a id="21554" class="Keyword">import</a> <a id="21561" href="foundation-core.type-arithmetic-cartesian-product-types.html" class="Module">foundation-core.type-arithmetic-cartesian-product-types</a>
<a id="21617" class="Keyword">open</a> <a id="21622" class="Keyword">import</a> <a id="21629" href="foundation-core.type-arithmetic-dependent-pair-types.html" class="Module">foundation-core.type-arithmetic-dependent-pair-types</a>
<a id="21682" class="Keyword">open</a> <a id="21687" class="Keyword">import</a> <a id="21694" href="foundation-core.univalence.html" class="Module">foundation-core.univalence</a>
<a id="21721" class="Keyword">open</a> <a id="21726" class="Keyword">import</a> <a id="21733" href="foundation-core.universal-property-pullbacks.html" class="Module">foundation-core.universal-property-pullbacks</a>
<a id="21778" class="Keyword">open</a> <a id="21783" class="Keyword">import</a> <a id="21790" href="foundation-core.universe-levels.html" class="Module">foundation-core.universe-levels</a>
</pre>
## Graph theory

<pre class="Agda"><a id="21852" class="Keyword">open</a> <a id="21857" class="Keyword">import</a> <a id="21864" href="graph-theory.html" class="Module">graph-theory</a>
<a id="21877" class="Keyword">open</a> <a id="21882" class="Keyword">import</a> <a id="21889" href="graph-theory.connected-undirected-graphs.html" class="Module">graph-theory.connected-undirected-graphs</a>
<a id="21930" class="Keyword">open</a> <a id="21935" class="Keyword">import</a> <a id="21942" href="graph-theory.directed-graphs.html" class="Module">graph-theory.directed-graphs</a>
<a id="21971" class="Keyword">open</a> <a id="21976" class="Keyword">import</a> <a id="21983" href="graph-theory.edge-coloured-undirected-graphs.html" class="Module">graph-theory.edge-coloured-undirected-graphs</a>
<a id="22028" class="Keyword">open</a> <a id="22033" class="Keyword">import</a> <a id="22040" href="graph-theory.equivalences-undirected-graphs.html" class="Module">graph-theory.equivalences-undirected-graphs</a>
<a id="22084" class="Keyword">open</a> <a id="22089" class="Keyword">import</a> <a id="22096" href="graph-theory.finite-graphs.html" class="Module">graph-theory.finite-graphs</a>
<a id="22123" class="Keyword">open</a> <a id="22128" class="Keyword">import</a> <a id="22135" href="graph-theory.incidence-undirected-graphs.html" class="Module">graph-theory.incidence-undirected-graphs</a>
<a id="22176" class="Keyword">open</a> <a id="22181" class="Keyword">import</a> <a id="22188" href="graph-theory.matchings.html" class="Module">graph-theory.matchings</a>
<a id="22211" class="Keyword">open</a> <a id="22216" class="Keyword">import</a> <a id="22223" href="graph-theory.mere-equivalences-undirected-graphs.html" class="Module">graph-theory.mere-equivalences-undirected-graphs</a>
<a id="22272" class="Keyword">open</a> <a id="22277" class="Keyword">import</a> <a id="22284" href="graph-theory.morphisms-directed-graphs.html" class="Module">graph-theory.morphisms-directed-graphs</a>
<a id="22323" class="Keyword">open</a> <a id="22328" class="Keyword">import</a> <a id="22335" href="graph-theory.morphisms-undirected-graphs.html" class="Module">graph-theory.morphisms-undirected-graphs</a>
<a id="22376" class="Keyword">open</a> <a id="22381" class="Keyword">import</a> <a id="22388" href="graph-theory.orientations-undirected-graphs.html" class="Module">graph-theory.orientations-undirected-graphs</a>
<a id="22432" class="Keyword">open</a> <a id="22437" class="Keyword">import</a> <a id="22444" href="graph-theory.paths-undirected-graphs.html" class="Module">graph-theory.paths-undirected-graphs</a>
<a id="22481" class="Keyword">open</a> <a id="22486" class="Keyword">import</a> <a id="22493" href="graph-theory.polygons.html" class="Module">graph-theory.polygons</a>
<a id="22515" class="Keyword">open</a> <a id="22520" class="Keyword">import</a> <a id="22527" href="graph-theory.reflexive-graphs.html" class="Module">graph-theory.reflexive-graphs</a>
<a id="22557" class="Keyword">open</a> <a id="22562" class="Keyword">import</a> <a id="22569" href="graph-theory.regular-undirected-graphs.html" class="Module">graph-theory.regular-undirected-graphs</a>
<a id="22608" class="Keyword">open</a> <a id="22613" class="Keyword">import</a> <a id="22620" href="graph-theory.simple-undirected-graphs.html" class="Module">graph-theory.simple-undirected-graphs</a>
<a id="22658" class="Keyword">open</a> <a id="22663" class="Keyword">import</a> <a id="22670" href="graph-theory.undirected-graphs.html" class="Module">graph-theory.undirected-graphs</a>
<a id="22701" class="Keyword">open</a> <a id="22706" class="Keyword">import</a> <a id="22713" href="graph-theory.vertex-covers.html" class="Module">graph-theory.vertex-covers</a>
<a id="22740" class="Keyword">open</a> <a id="22745" class="Keyword">import</a> <a id="22752" href="graph-theory.voltage-graphs.html" class="Module">graph-theory.voltage-graphs</a>
</pre>
## Group theory

<pre class="Agda"><a id="22810" class="Keyword">open</a> <a id="22815" class="Keyword">import</a> <a id="22822" href="group-theory.html" class="Module">group-theory</a>
<a id="22835" class="Keyword">open</a> <a id="22840" class="Keyword">import</a> <a id="22847" href="group-theory.abelian-groups.html" class="Module">group-theory.abelian-groups</a>
<a id="22875" class="Keyword">open</a> <a id="22880" class="Keyword">import</a> <a id="22887" href="group-theory.abelian-subgroups.html" class="Module">group-theory.abelian-subgroups</a>
<a id="22918" class="Keyword">open</a> <a id="22923" class="Keyword">import</a> <a id="22930" href="group-theory.abstract-group-torsors.html" class="Module">group-theory.abstract-group-torsors</a>
<a id="22966" class="Keyword">open</a> <a id="22971" class="Keyword">import</a> <a id="22978" href="group-theory.addition-homomorphisms-abelian-groups.html" class="Module">group-theory.addition-homomorphisms-abelian-groups</a>
<a id="23029" class="Keyword">open</a> <a id="23034" class="Keyword">import</a> <a id="23041" href="group-theory.automorphism-groups.html" class="Module">group-theory.automorphism-groups</a>
<a id="23074" class="Keyword">open</a> <a id="23079" class="Keyword">import</a> <a id="23086" href="group-theory.category-of-groups.html" class="Module">group-theory.category-of-groups</a>
<a id="23118" class="Keyword">open</a> <a id="23123" class="Keyword">import</a> <a id="23130" href="group-theory.category-of-semigroups.html" class="Module">group-theory.category-of-semigroups</a>
<a id="23166" class="Keyword">open</a> <a id="23171" class="Keyword">import</a> <a id="23178" href="group-theory.cayleys-theorem.html" class="Module">group-theory.cayleys-theorem</a>
<a id="23207" class="Keyword">open</a> <a id="23212" class="Keyword">import</a> <a id="23219" href="group-theory.concrete-group-actions.html" class="Module">group-theory.concrete-group-actions</a>
<a id="23255" class="Keyword">open</a> <a id="23260" class="Keyword">import</a> <a id="23267" href="group-theory.concrete-groups.html" class="Module">group-theory.concrete-groups</a>
<a id="23296" class="Keyword">open</a> <a id="23301" class="Keyword">import</a> <a id="23308" href="group-theory.concrete-subgroups.html" class="Module">group-theory.concrete-subgroups</a>
<a id="23340" class="Keyword">open</a> <a id="23345" class="Keyword">import</a> <a id="23352" href="group-theory.conjugation.html" class="Module">group-theory.conjugation</a>
<a id="23377" class="Keyword">open</a> <a id="23382" class="Keyword">import</a> <a id="23389" href="group-theory.embeddings-groups.html" class="Module">group-theory.embeddings-groups</a>
<a id="23420" class="Keyword">open</a> <a id="23425" class="Keyword">import</a> <a id="23432" href="group-theory.endomorphism-rings-abelian-groups.html" class="Module">group-theory.endomorphism-rings-abelian-groups</a>
<a id="23479" class="Keyword">open</a> <a id="23484" class="Keyword">import</a> <a id="23491" href="group-theory.epimorphisms-groups.html" class="Module">group-theory.epimorphisms-groups</a>
<a id="23524" class="Keyword">open</a> <a id="23529" class="Keyword">import</a> <a id="23536" href="group-theory.equivalences-group-actions.html" class="Module">group-theory.equivalences-group-actions</a>
<a id="23576" class="Keyword">open</a> <a id="23581" class="Keyword">import</a> <a id="23588" href="group-theory.equivalences-semigroups.html" class="Module">group-theory.equivalences-semigroups</a>
<a id="23625" class="Keyword">open</a> <a id="23630" class="Keyword">import</a> <a id="23637" href="group-theory.examples-higher-groups.html" class="Module">group-theory.examples-higher-groups</a>
<a id="23673" class="Keyword">open</a> <a id="23678" class="Keyword">import</a> <a id="23685" href="group-theory.furstenberg-groups.html" class="Module">group-theory.furstenberg-groups</a>
<a id="23717" class="Keyword">open</a> <a id="23722" class="Keyword">import</a> <a id="23729" href="group-theory.group-actions.html" class="Module">group-theory.group-actions</a>
<a id="23756" class="Keyword">open</a> <a id="23761" class="Keyword">import</a> <a id="23768" href="group-theory.groups.html" class="Module">group-theory.groups</a>
<a id="23788" class="Keyword">open</a> <a id="23793" class="Keyword">import</a> <a id="23800" href="group-theory.higher-groups.html" class="Module">group-theory.higher-groups</a>
<a id="23827" class="Keyword">open</a> <a id="23832" class="Keyword">import</a> <a id="23839" href="group-theory.homomorphisms-abelian-groups.html" class="Module">group-theory.homomorphisms-abelian-groups</a>
<a id="23881" class="Keyword">open</a> <a id="23886" class="Keyword">import</a> <a id="23893" href="group-theory.homomorphisms-generated-subgroups.html" class="Module">group-theory.homomorphisms-generated-subgroups</a>
<a id="23940" class="Keyword">open</a> <a id="23945" class="Keyword">import</a> <a id="23952" href="group-theory.homomorphisms-group-actions.html" class="Module">group-theory.homomorphisms-group-actions</a>
<a id="23993" class="Keyword">open</a> <a id="23998" class="Keyword">import</a> <a id="24005" href="group-theory.homomorphisms-groups.html" class="Module">group-theory.homomorphisms-groups</a>
<a id="24039" class="Keyword">open</a> <a id="24044" class="Keyword">import</a> <a id="24051" href="group-theory.homomorphisms-monoids.html" class="Module">group-theory.homomorphisms-monoids</a>
<a id="24086" class="Keyword">open</a> <a id="24091" class="Keyword">import</a> <a id="24098" href="group-theory.homomorphisms-semigroups.html" class="Module">group-theory.homomorphisms-semigroups</a>
<a id="24136" class="Keyword">open</a> <a id="24141" class="Keyword">import</a> <a id="24148" href="group-theory.inverse-semigroups.html" class="Module">group-theory.inverse-semigroups</a>
<a id="24180" class="Keyword">open</a> <a id="24185" class="Keyword">import</a> <a id="24192" href="group-theory.invertible-elements-monoids.html" class="Module">group-theory.invertible-elements-monoids</a>
<a id="24233" class="Keyword">open</a> <a id="24238" class="Keyword">import</a> <a id="24245" href="group-theory.isomorphisms-abelian-groups.html" class="Module">group-theory.isomorphisms-abelian-groups</a>
<a id="24286" class="Keyword">open</a> <a id="24291" class="Keyword">import</a> <a id="24298" href="group-theory.isomorphisms-group-actions.html" class="Module">group-theory.isomorphisms-group-actions</a>
<a id="24338" class="Keyword">open</a> <a id="24343" class="Keyword">import</a> <a id="24350" href="group-theory.isomorphisms-groups.html" class="Module">group-theory.isomorphisms-groups</a>
<a id="24383" class="Keyword">open</a> <a id="24388" class="Keyword">import</a> <a id="24395" href="group-theory.isomorphisms-semigroups.html" class="Module">group-theory.isomorphisms-semigroups</a>
<a id="24432" class="Keyword">open</a> <a id="24437" class="Keyword">import</a> <a id="24444" href="group-theory.mere-equivalences-group-actions.html" class="Module">group-theory.mere-equivalences-group-actions</a>
<a id="24489" class="Keyword">open</a> <a id="24494" class="Keyword">import</a> <a id="24501" href="group-theory.monoid-actions.html" class="Module">group-theory.monoid-actions</a>
<a id="24529" class="Keyword">open</a> <a id="24534" class="Keyword">import</a> <a id="24541" href="group-theory.monoids.html" class="Module">group-theory.monoids</a>
<a id="24562" class="Keyword">open</a> <a id="24567" class="Keyword">import</a> <a id="24574" href="group-theory.monomorphisms-groups.html" class="Module">group-theory.monomorphisms-groups</a>
<a id="24608" class="Keyword">open</a> <a id="24613" class="Keyword">import</a> <a id="24620" href="group-theory.orbits-group-actions.html" class="Module">group-theory.orbits-group-actions</a>
<a id="24654" class="Keyword">open</a> <a id="24659" class="Keyword">import</a> <a id="24666" href="group-theory.orbits-monoid-actions.html" class="Module">group-theory.orbits-monoid-actions</a>
<a id="24701" class="Keyword">open</a> <a id="24706" class="Keyword">import</a> <a id="24713" href="group-theory.precategory-of-group-actions.html" class="Module">group-theory.precategory-of-group-actions</a>
<a id="24755" class="Keyword">open</a> <a id="24760" class="Keyword">import</a> <a id="24767" href="group-theory.precategory-of-groups.html" class="Module">group-theory.precategory-of-groups</a>
<a id="24802" class="Keyword">open</a> <a id="24807" class="Keyword">import</a> <a id="24814" href="group-theory.precategory-of-semigroups.html" class="Module">group-theory.precategory-of-semigroups</a>
<a id="24853" class="Keyword">open</a> <a id="24858" class="Keyword">import</a> <a id="24865" href="group-theory.principal-group-actions.html" class="Module">group-theory.principal-group-actions</a>
<a id="24902" class="Keyword">open</a> <a id="24907" class="Keyword">import</a> <a id="24914" href="group-theory.semigroups.html" class="Module">group-theory.semigroups</a>
<a id="24938" class="Keyword">open</a> <a id="24943" class="Keyword">import</a> <a id="24950" href="group-theory.sheargroups.html" class="Module">group-theory.sheargroups</a>
<a id="24975" class="Keyword">open</a> <a id="24980" class="Keyword">import</a> <a id="24987" href="group-theory.stabilizer-groups.html" class="Module">group-theory.stabilizer-groups</a>
<a id="25018" class="Keyword">open</a> <a id="25023" class="Keyword">import</a> <a id="25030" href="group-theory.subgroups-generated-by-subsets-groups.html" class="Module">group-theory.subgroups-generated-by-subsets-groups</a>
<a id="25081" class="Keyword">open</a> <a id="25086" class="Keyword">import</a> <a id="25093" href="group-theory.subgroups.html" class="Module">group-theory.subgroups</a>
<a id="25116" class="Keyword">open</a> <a id="25121" class="Keyword">import</a> <a id="25128" href="group-theory.substitution-functor-group-actions.html" class="Module">group-theory.substitution-functor-group-actions</a>
<a id="25176" class="Keyword">open</a> <a id="25181" class="Keyword">import</a> <a id="25188" href="group-theory.symmetric-groups.html" class="Module">group-theory.symmetric-groups</a>
<a id="25218" class="Keyword">open</a> <a id="25223" class="Keyword">import</a> <a id="25230" href="group-theory.transitive-group-actions.html" class="Module">group-theory.transitive-group-actions</a>
</pre>
## Linear algebra

<pre class="Agda"><a id="25300" class="Keyword">open</a> <a id="25305" class="Keyword">import</a> <a id="25312" href="linear-algebra.html" class="Module">linear-algebra</a>
<a id="25327" class="Keyword">open</a> <a id="25332" class="Keyword">import</a> <a id="25339" href="linear-algebra.constant-matrices.html" class="Module">linear-algebra.constant-matrices</a>
<a id="25372" class="Keyword">open</a> <a id="25377" class="Keyword">import</a> <a id="25384" href="linear-algebra.constant-vectors.html" class="Module">linear-algebra.constant-vectors</a>
<a id="25416" class="Keyword">open</a> <a id="25421" class="Keyword">import</a> <a id="25428" href="linear-algebra.diagonal-matrices-on-rings.html" class="Module">linear-algebra.diagonal-matrices-on-rings</a>
<a id="25470" class="Keyword">open</a> <a id="25475" class="Keyword">import</a> <a id="25482" href="linear-algebra.functoriality-matrices.html" class="Module">linear-algebra.functoriality-matrices</a>
<a id="25520" class="Keyword">open</a> <a id="25525" class="Keyword">import</a> <a id="25532" href="linear-algebra.functoriality-vectors.html" class="Module">linear-algebra.functoriality-vectors</a>
<a id="25569" class="Keyword">open</a> <a id="25574" class="Keyword">import</a> <a id="25581" href="linear-algebra.matrices-on-rings.html" class="Module">linear-algebra.matrices-on-rings</a>
<a id="25614" class="Keyword">open</a> <a id="25619" class="Keyword">import</a> <a id="25626" href="linear-algebra.matrices.html" class="Module">linear-algebra.matrices</a>
<a id="25650" class="Keyword">open</a> <a id="25655" class="Keyword">import</a> <a id="25662" href="linear-algebra.multiplication-matrices.html" class="Module">linear-algebra.multiplication-matrices</a>
<a id="25701" class="Keyword">open</a> <a id="25706" class="Keyword">import</a> <a id="25713" href="linear-algebra.scalar-multiplication-matrices.html" class="Module">linear-algebra.scalar-multiplication-matrices</a>
<a id="25759" class="Keyword">open</a> <a id="25764" class="Keyword">import</a> <a id="25771" href="linear-algebra.scalar-multiplication-vectors.html" class="Module">linear-algebra.scalar-multiplication-vectors</a>
<a id="25816" class="Keyword">open</a> <a id="25821" class="Keyword">import</a> <a id="25828" href="linear-algebra.transposition-matrices.html" class="Module">linear-algebra.transposition-matrices</a>
<a id="25866" class="Keyword">open</a> <a id="25871" class="Keyword">import</a> <a id="25878" href="linear-algebra.vectors-on-rings.html" class="Module">linear-algebra.vectors-on-rings</a>
<a id="25910" class="Keyword">open</a> <a id="25915" class="Keyword">import</a> <a id="25922" href="linear-algebra.vectors.html" class="Module">linear-algebra.vectors</a>
</pre>
## Order theory

<pre class="Agda"><a id="25975" class="Keyword">open</a> <a id="25980" class="Keyword">import</a> <a id="25987" href="order-theory.html" class="Module">order-theory</a>
<a id="26000" class="Keyword">open</a> <a id="26005" class="Keyword">import</a> <a id="26012" href="order-theory.chains-posets.html" class="Module">order-theory.chains-posets</a>
<a id="26039" class="Keyword">open</a> <a id="26044" class="Keyword">import</a> <a id="26051" href="order-theory.chains-preorders.html" class="Module">order-theory.chains-preorders</a>
<a id="26081" class="Keyword">open</a> <a id="26086" class="Keyword">import</a> <a id="26093" href="order-theory.decidable-subposets.html" class="Module">order-theory.decidable-subposets</a>
<a id="26126" class="Keyword">open</a> <a id="26131" class="Keyword">import</a> <a id="26138" href="order-theory.decidable-subpreorders.html" class="Module">order-theory.decidable-subpreorders</a>
<a id="26174" class="Keyword">open</a> <a id="26179" class="Keyword">import</a> <a id="26186" href="order-theory.finite-posets.html" class="Module">order-theory.finite-posets</a>
<a id="26213" class="Keyword">open</a> <a id="26218" class="Keyword">import</a> <a id="26225" href="order-theory.finite-preorders.html" class="Module">order-theory.finite-preorders</a>
<a id="26255" class="Keyword">open</a> <a id="26260" class="Keyword">import</a> <a id="26267" href="order-theory.finitely-graded-posets.html" class="Module">order-theory.finitely-graded-posets</a>
<a id="26303" class="Keyword">open</a> <a id="26308" class="Keyword">import</a> <a id="26315" href="order-theory.greatest-lower-bounds-posets.html" class="Module">order-theory.greatest-lower-bounds-posets</a>
<a id="26357" class="Keyword">open</a> <a id="26362" class="Keyword">import</a> <a id="26369" href="order-theory.interval-subposets.html" class="Module">order-theory.interval-subposets</a>
<a id="26401" class="Keyword">open</a> <a id="26406" class="Keyword">import</a> <a id="26413" href="order-theory.join-semilattices.html" class="Module">order-theory.join-semilattices</a>
<a id="26444" class="Keyword">open</a> <a id="26449" class="Keyword">import</a> <a id="26456" href="order-theory.large-posets.html" class="Module">order-theory.large-posets</a>
<a id="26482" class="Keyword">open</a> <a id="26487" class="Keyword">import</a> <a id="26494" href="order-theory.large-preorders.html" class="Module">order-theory.large-preorders</a>
<a id="26523" class="Keyword">open</a> <a id="26528" class="Keyword">import</a> <a id="26535" href="order-theory.largest-elements-posets.html" class="Module">order-theory.largest-elements-posets</a>
<a id="26572" class="Keyword">open</a> <a id="26577" class="Keyword">import</a> <a id="26584" href="order-theory.largest-elements-preorders.html" class="Module">order-theory.largest-elements-preorders</a>
<a id="26624" class="Keyword">open</a> <a id="26629" class="Keyword">import</a> <a id="26636" href="order-theory.lattices.html" class="Module">order-theory.lattices</a>
<a id="26658" class="Keyword">open</a> <a id="26663" class="Keyword">import</a> <a id="26670" href="order-theory.least-elements-posets.html" class="Module">order-theory.least-elements-posets</a>
<a id="26705" class="Keyword">open</a> <a id="26710" class="Keyword">import</a> <a id="26717" href="order-theory.least-elements-preorders.html" class="Module">order-theory.least-elements-preorders</a>
<a id="26755" class="Keyword">open</a> <a id="26760" class="Keyword">import</a> <a id="26767" href="order-theory.least-upper-bounds-posets.html" class="Module">order-theory.least-upper-bounds-posets</a>
<a id="26806" class="Keyword">open</a> <a id="26811" class="Keyword">import</a> <a id="26818" href="order-theory.locally-finite-posets.html" class="Module">order-theory.locally-finite-posets</a>
<a id="26853" class="Keyword">open</a> <a id="26858" class="Keyword">import</a> <a id="26865" href="order-theory.maximal-chains-posets.html" class="Module">order-theory.maximal-chains-posets</a>
<a id="26900" class="Keyword">open</a> <a id="26905" class="Keyword">import</a> <a id="26912" href="order-theory.maximal-chains-preorders.html" class="Module">order-theory.maximal-chains-preorders</a>
<a id="26950" class="Keyword">open</a> <a id="26955" class="Keyword">import</a> <a id="26962" href="order-theory.meet-semilattices.html" class="Module">order-theory.meet-semilattices</a>
<a id="26993" class="Keyword">open</a> <a id="26998" class="Keyword">import</a> <a id="27005" href="order-theory.order-preserving-maps-posets.html" class="Module">order-theory.order-preserving-maps-posets</a>
<a id="27047" class="Keyword">open</a> <a id="27052" class="Keyword">import</a> <a id="27059" href="order-theory.order-preserving-maps-preorders.html" class="Module">order-theory.order-preserving-maps-preorders</a>
<a id="27104" class="Keyword">open</a> <a id="27109" class="Keyword">import</a> <a id="27116" href="order-theory.planar-binary-trees.html" class="Module">order-theory.planar-binary-trees</a>
<a id="27149" class="Keyword">open</a> <a id="27154" class="Keyword">import</a> <a id="27161" href="order-theory.posets.html" class="Module">order-theory.posets</a>
<a id="27181" class="Keyword">open</a> <a id="27186" class="Keyword">import</a> <a id="27193" href="order-theory.preorders.html" class="Module">order-theory.preorders</a>
<a id="27216" class="Keyword">open</a> <a id="27221" class="Keyword">import</a> <a id="27228" href="order-theory.subposets.html" class="Module">order-theory.subposets</a>
<a id="27251" class="Keyword">open</a> <a id="27256" class="Keyword">import</a> <a id="27263" href="order-theory.subpreorders.html" class="Module">order-theory.subpreorders</a>
<a id="27289" class="Keyword">open</a> <a id="27294" class="Keyword">import</a> <a id="27301" href="order-theory.total-posets.html" class="Module">order-theory.total-posets</a>
<a id="27327" class="Keyword">open</a> <a id="27332" class="Keyword">import</a> <a id="27339" href="order-theory.total-preorders.html" class="Module">order-theory.total-preorders</a>
</pre>
## Polytopes

<pre class="Agda"><a id="27395" class="Keyword">open</a> <a id="27400" class="Keyword">import</a> <a id="27407" href="polytopes.html" class="Module">polytopes</a>
<a id="27417" class="Keyword">open</a> <a id="27422" class="Keyword">import</a> <a id="27429" href="polytopes.abstract-polytopes.html" class="Module">polytopes.abstract-polytopes</a>
</pre>
## Ring theory

<pre class="Agda"><a id="27487" class="Keyword">open</a> <a id="27492" class="Keyword">import</a> <a id="27499" href="ring-theory.html" class="Module">ring-theory</a>
<a id="27511" class="Keyword">open</a> <a id="27516" class="Keyword">import</a> <a id="27523" href="ring-theory.division-rings.html" class="Module">ring-theory.division-rings</a>
<a id="27550" class="Keyword">open</a> <a id="27555" class="Keyword">import</a> <a id="27562" href="ring-theory.homomorphisms-rings.html" class="Module">ring-theory.homomorphisms-rings</a>
<a id="27594" class="Keyword">open</a> <a id="27599" class="Keyword">import</a> <a id="27606" href="ring-theory.ideals-generated-by-subsets-rings.html" class="Module">ring-theory.ideals-generated-by-subsets-rings</a>
<a id="27652" class="Keyword">open</a> <a id="27657" class="Keyword">import</a> <a id="27664" href="ring-theory.ideals-rings.html" class="Module">ring-theory.ideals-rings</a>
<a id="27689" class="Keyword">open</a> <a id="27694" class="Keyword">import</a> <a id="27701" href="ring-theory.invertible-elements-rings.html" class="Module">ring-theory.invertible-elements-rings</a>
<a id="27739" class="Keyword">open</a> <a id="27744" class="Keyword">import</a> <a id="27751" href="ring-theory.isomorphisms-rings.html" class="Module">ring-theory.isomorphisms-rings</a>
<a id="27782" class="Keyword">open</a> <a id="27787" class="Keyword">import</a> <a id="27794" href="ring-theory.localizations-rings.html" class="Module">ring-theory.localizations-rings</a>
<a id="27826" class="Keyword">open</a> <a id="27831" class="Keyword">import</a> <a id="27838" href="ring-theory.nontrivial-rings.html" class="Module">ring-theory.nontrivial-rings</a>
<a id="27867" class="Keyword">open</a> <a id="27872" class="Keyword">import</a> <a id="27879" href="ring-theory.opposite-rings.html" class="Module">ring-theory.opposite-rings</a>
<a id="27906" class="Keyword">open</a> <a id="27911" class="Keyword">import</a> <a id="27918" href="ring-theory.products-rings.html" class="Module">ring-theory.products-rings</a>
<a id="27945" class="Keyword">open</a> <a id="27950" class="Keyword">import</a> <a id="27957" href="ring-theory.rings.html" class="Module">ring-theory.rings</a>
<a id="27975" class="Keyword">open</a> <a id="27980" class="Keyword">import</a> <a id="27987" href="ring-theory.subsets-rings.html" class="Module">ring-theory.subsets-rings</a>
</pre>
## Set theory

<pre class="Agda"><a id="28041" class="Keyword">open</a> <a id="28046" class="Keyword">import</a> <a id="28053" href="set-theory.html" class="Module">set-theory</a>
<a id="28064" class="Keyword">open</a> <a id="28069" class="Keyword">import</a> <a id="28076" href="set-theory.cantor-schroder-bernstein.html" class="Module">set-theory.cantor-schroder-bernstein</a>
<a id="28113" class="Keyword">open</a> <a id="28118" class="Keyword">import</a> <a id="28125" href="set-theory.countable-sets.html" class="Module">set-theory.countable-sets</a>
<a id="28151" class="Keyword">open</a> <a id="28156" class="Keyword">import</a> <a id="28163" href="set-theory.uncountable-sets.html" class="Module">set-theory.uncountable-sets</a>
</pre>
## Structured types

<pre class="Agda"><a id="28225" class="Keyword">open</a> <a id="28230" class="Keyword">import</a> <a id="28237" href="structured-types.html" class="Module">structured-types</a>
<a id="28254" class="Keyword">open</a> <a id="28259" class="Keyword">import</a> <a id="28266" href="structured-types.contractible-pointed-types.html" class="Module">structured-types.contractible-pointed-types</a>
<a id="28310" class="Keyword">open</a> <a id="28315" class="Keyword">import</a> <a id="28322" href="structured-types.equivalences-types-equipped-with-endomorphisms.html" class="Module">structured-types.equivalences-types-equipped-with-endomorphisms</a>
<a id="28386" class="Keyword">open</a> <a id="28391" class="Keyword">import</a> <a id="28398" href="structured-types.finite-multiplication-magmas.html" class="Module">structured-types.finite-multiplication-magmas</a>
<a id="28444" class="Keyword">open</a> <a id="28449" class="Keyword">import</a> <a id="28456" href="structured-types.magmas.html" class="Module">structured-types.magmas</a>
<a id="28480" class="Keyword">open</a> <a id="28485" class="Keyword">import</a> <a id="28492" href="structured-types.mere-equivalences-types-equipped-with-endomorphisms.html" class="Module">structured-types.mere-equivalences-types-equipped-with-endomorphisms</a>
<a id="28561" class="Keyword">open</a> <a id="28566" class="Keyword">import</a> <a id="28573" href="structured-types.morphisms-magmas.html" class="Module">structured-types.morphisms-magmas</a>
<a id="28607" class="Keyword">open</a> <a id="28612" class="Keyword">import</a> <a id="28619" href="structured-types.morphisms-types-equipped-with-endomorphisms.html" class="Module">structured-types.morphisms-types-equipped-with-endomorphisms</a>
<a id="28680" class="Keyword">open</a> <a id="28685" class="Keyword">import</a> <a id="28692" href="structured-types.morphisms-wild-unital-magmas.html" class="Module">structured-types.morphisms-wild-unital-magmas</a>
<a id="28738" class="Keyword">open</a> <a id="28743" class="Keyword">import</a> <a id="28750" href="structured-types.pointed-dependent-functions.html" class="Module">structured-types.pointed-dependent-functions</a>
<a id="28795" class="Keyword">open</a> <a id="28800" class="Keyword">import</a> <a id="28807" href="structured-types.pointed-equivalences.html" class="Module">structured-types.pointed-equivalences</a>
<a id="28845" class="Keyword">open</a> <a id="28850" class="Keyword">import</a> <a id="28857" href="structured-types.pointed-families-of-types.html" class="Module">structured-types.pointed-families-of-types</a>
<a id="28900" class="Keyword">open</a> <a id="28905" class="Keyword">import</a> <a id="28912" href="structured-types.pointed-homotopies.html" class="Module">structured-types.pointed-homotopies</a>
<a id="28948" class="Keyword">open</a> <a id="28953" class="Keyword">import</a> <a id="28960" href="structured-types.pointed-maps.html" class="Module">structured-types.pointed-maps</a>
<a id="28990" class="Keyword">open</a> <a id="28995" class="Keyword">import</a> <a id="29002" href="structured-types.pointed-types.html" class="Module">structured-types.pointed-types</a>
<a id="29033" class="Keyword">open</a> <a id="29038" class="Keyword">import</a> <a id="29045" href="structured-types.types-equipped-with-endomorphisms.html" class="Module">structured-types.types-equipped-with-endomorphisms</a>
<a id="29096" class="Keyword">open</a> <a id="29101" class="Keyword">import</a> <a id="29108" href="structured-types.universal-property-lists-wild-monoids.html" class="Module">structured-types.universal-property-lists-wild-monoids</a>
<a id="29163" class="Keyword">open</a> <a id="29168" class="Keyword">import</a> <a id="29175" href="structured-types.wild-groups.html" class="Module">structured-types.wild-groups</a>
<a id="29204" class="Keyword">open</a> <a id="29209" class="Keyword">import</a> <a id="29216" href="structured-types.wild-loops.html" class="Module">structured-types.wild-loops</a>
<a id="29244" class="Keyword">open</a> <a id="29249" class="Keyword">import</a> <a id="29256" href="structured-types.wild-monoids.html" class="Module">structured-types.wild-monoids</a>
<a id="29286" class="Keyword">open</a> <a id="29291" class="Keyword">import</a> <a id="29298" href="structured-types.wild-quasigroups.html" class="Module">structured-types.wild-quasigroups</a>
<a id="29332" class="Keyword">open</a> <a id="29337" class="Keyword">import</a> <a id="29344" href="structured-types.wild-semigroups.html" class="Module">structured-types.wild-semigroups</a>
<a id="29377" class="Keyword">open</a> <a id="29382" class="Keyword">import</a> <a id="29389" href="structured-types.wild-unital-magmas.html" class="Module">structured-types.wild-unital-magmas</a>
</pre>
## Synthetic homotopy theory

<pre class="Agda"><a id="29468" class="Keyword">open</a> <a id="29473" class="Keyword">import</a> <a id="29480" href="synthetic-homotopy-theory.html" class="Module">synthetic-homotopy-theory</a>
<a id="29506" class="Keyword">open</a> <a id="29511" class="Keyword">import</a> <a id="29518" href="synthetic-homotopy-theory.23-pullbacks.html" class="Module">synthetic-homotopy-theory.23-pullbacks</a>
<a id="29557" class="Keyword">open</a> <a id="29562" class="Keyword">import</a> <a id="29569" href="synthetic-homotopy-theory.24-pushouts.html" class="Module">synthetic-homotopy-theory.24-pushouts</a>
<a id="29607" class="Keyword">open</a> <a id="29612" class="Keyword">import</a> <a id="29619" href="synthetic-homotopy-theory.25-cubical-diagrams.html" class="Module">synthetic-homotopy-theory.25-cubical-diagrams</a>
<a id="29665" class="Keyword">open</a> <a id="29670" class="Keyword">import</a> <a id="29677" href="synthetic-homotopy-theory.26-descent.html" class="Module">synthetic-homotopy-theory.26-descent</a>
<a id="29714" class="Keyword">open</a> <a id="29719" class="Keyword">import</a> <a id="29726" href="synthetic-homotopy-theory.26-id-pushout.html" class="Module">synthetic-homotopy-theory.26-id-pushout</a>
<a id="29766" class="Keyword">open</a> <a id="29771" class="Keyword">import</a> <a id="29778" href="synthetic-homotopy-theory.27-sequences.html" class="Module">synthetic-homotopy-theory.27-sequences</a>
<a id="29817" class="Keyword">open</a> <a id="29822" class="Keyword">import</a> <a id="29829" href="synthetic-homotopy-theory.circle.html" class="Module">synthetic-homotopy-theory.circle</a>
<a id="29862" class="Keyword">open</a> <a id="29867" class="Keyword">import</a> <a id="29874" href="synthetic-homotopy-theory.cofibers.html" class="Module">synthetic-homotopy-theory.cofibers</a>
<a id="29909" class="Keyword">open</a> <a id="29914" class="Keyword">import</a> <a id="29921" href="synthetic-homotopy-theory.cyclic-types.html" class="Module">synthetic-homotopy-theory.cyclic-types</a>
<a id="29960" class="Keyword">open</a> <a id="29965" class="Keyword">import</a> <a id="29972" href="synthetic-homotopy-theory.double-loop-spaces.html" class="Module">synthetic-homotopy-theory.double-loop-spaces</a>
<a id="30017" class="Keyword">open</a> <a id="30022" class="Keyword">import</a> <a id="30029" href="synthetic-homotopy-theory.functoriality-loop-spaces.html" class="Module">synthetic-homotopy-theory.functoriality-loop-spaces</a>
<a id="30081" class="Keyword">open</a> <a id="30086" class="Keyword">import</a> <a id="30093" href="synthetic-homotopy-theory.groups-of-loops-in-1-types.html" class="Module">synthetic-homotopy-theory.groups-of-loops-in-1-types</a>
<a id="30146" class="Keyword">open</a> <a id="30151" class="Keyword">import</a> <a id="30158" href="synthetic-homotopy-theory.infinite-cyclic-types.html" class="Module">synthetic-homotopy-theory.infinite-cyclic-types</a>
<a id="30206" class="Keyword">open</a> <a id="30211" class="Keyword">import</a> <a id="30218" href="synthetic-homotopy-theory.interval-type.html" class="Module">synthetic-homotopy-theory.interval-type</a>
<a id="30258" class="Keyword">open</a> <a id="30263" class="Keyword">import</a> <a id="30270" href="synthetic-homotopy-theory.iterated-loop-spaces.html" class="Module">synthetic-homotopy-theory.iterated-loop-spaces</a>
<a id="30317" class="Keyword">open</a> <a id="30322" class="Keyword">import</a> <a id="30329" href="synthetic-homotopy-theory.joins-of-types.html" class="Module">synthetic-homotopy-theory.joins-of-types</a>
<a id="30370" class="Keyword">open</a> <a id="30375" class="Keyword">import</a> <a id="30382" href="synthetic-homotopy-theory.loop-spaces.html" class="Module">synthetic-homotopy-theory.loop-spaces</a>
<a id="30420" class="Keyword">open</a> <a id="30425" class="Keyword">import</a> <a id="30432" href="synthetic-homotopy-theory.triple-loop-spaces.html" class="Module">synthetic-homotopy-theory.triple-loop-spaces</a>
<a id="30477" class="Keyword">open</a> <a id="30482" class="Keyword">import</a> <a id="30489" href="synthetic-homotopy-theory.universal-cover-circle.html" class="Module">synthetic-homotopy-theory.universal-cover-circle</a>
<a id="30538" class="Keyword">open</a> <a id="30543" class="Keyword">import</a> <a id="30550" href="synthetic-homotopy-theory.wedges-of-pointed-types.html" class="Module">synthetic-homotopy-theory.wedges-of-pointed-types</a>
</pre>
## Tutorials

<pre class="Agda"><a id="30627" class="Keyword">open</a> <a id="30632" class="Keyword">import</a> <a id="30639" href="tutorials.basic-agda.html" class="Module">tutorials.basic-agda</a>
</pre>
## Type theories

<pre class="Agda"><a id="30691" class="Keyword">open</a> <a id="30696" class="Keyword">import</a> <a id="30703" href="type-theories.html" class="Module">type-theories</a>
<a id="30717" class="Keyword">open</a> <a id="30722" class="Keyword">import</a> <a id="30729" href="type-theories.comprehension-type-theories.html" class="Module">type-theories.comprehension-type-theories</a>
<a id="30771" class="Keyword">open</a> <a id="30776" class="Keyword">import</a> <a id="30783" href="type-theories.dependent-type-theories.html" class="Module">type-theories.dependent-type-theories</a>
<a id="30821" class="Keyword">open</a> <a id="30826" class="Keyword">import</a> <a id="30833" href="type-theories.fibered-dependent-type-theories.html" class="Module">type-theories.fibered-dependent-type-theories</a>
<a id="30879" class="Keyword">open</a> <a id="30884" class="Keyword">import</a> <a id="30891" href="type-theories.sections-dependent-type-theories.html" class="Module">type-theories.sections-dependent-type-theories</a>
<a id="30938" class="Keyword">open</a> <a id="30943" class="Keyword">import</a> <a id="30950" href="type-theories.simple-type-theories.html" class="Module">type-theories.simple-type-theories</a>
<a id="30985" class="Keyword">open</a> <a id="30990" class="Keyword">import</a> <a id="30997" href="type-theories.unityped-type-theories.html" class="Module">type-theories.unityped-type-theories</a>
</pre>
## Univalent combinatorics

<pre class="Agda"><a id="31075" class="Keyword">open</a> <a id="31080" class="Keyword">import</a> <a id="31087" href="univalent-combinatorics.html" class="Module">univalent-combinatorics</a>
<a id="31111" class="Keyword">open</a> <a id="31116" class="Keyword">import</a> <a id="31123" href="univalent-combinatorics.2-element-decidable-subtypes.html" class="Module">univalent-combinatorics.2-element-decidable-subtypes</a>
<a id="31176" class="Keyword">open</a> <a id="31181" class="Keyword">import</a> <a id="31188" href="univalent-combinatorics.2-element-subtypes.html" class="Module">univalent-combinatorics.2-element-subtypes</a>
<a id="31231" class="Keyword">open</a> <a id="31236" class="Keyword">import</a> <a id="31243" href="univalent-combinatorics.2-element-types.html" class="Module">univalent-combinatorics.2-element-types</a>
<a id="31283" class="Keyword">open</a> <a id="31288" class="Keyword">import</a> <a id="31295" href="univalent-combinatorics.binomial-types.html" class="Module">univalent-combinatorics.binomial-types</a>
<a id="31334" class="Keyword">open</a> <a id="31339" class="Keyword">import</a> <a id="31346" href="univalent-combinatorics.cartesian-product-types.html" class="Module">univalent-combinatorics.cartesian-product-types</a>
<a id="31394" class="Keyword">open</a> <a id="31399" class="Keyword">import</a> <a id="31406" href="univalent-combinatorics.classical-finite-types.html" class="Module">univalent-combinatorics.classical-finite-types</a>
<a id="31453" class="Keyword">open</a> <a id="31458" class="Keyword">import</a> <a id="31465" href="univalent-combinatorics.complements-isolated-points.html" class="Module">univalent-combinatorics.complements-isolated-points</a>
<a id="31517" class="Keyword">open</a> <a id="31522" class="Keyword">import</a> <a id="31529" href="univalent-combinatorics.composition-species.html" class="Module">univalent-combinatorics.composition-species</a>
<a id="31573" class="Keyword">open</a> <a id="31578" class="Keyword">import</a> <a id="31585" href="univalent-combinatorics.coproduct-types.html" class="Module">univalent-combinatorics.coproduct-types</a>
<a id="31625" class="Keyword">open</a> <a id="31630" class="Keyword">import</a> <a id="31637" href="univalent-combinatorics.counting-decidable-subtypes.html" class="Module">univalent-combinatorics.counting-decidable-subtypes</a>
<a id="31689" class="Keyword">open</a> <a id="31694" class="Keyword">import</a> <a id="31701" href="univalent-combinatorics.counting-dependent-pair-types.html" class="Module">univalent-combinatorics.counting-dependent-pair-types</a>
<a id="31755" class="Keyword">open</a> <a id="31760" class="Keyword">import</a> <a id="31767" href="univalent-combinatorics.counting-fibers-of-maps.html" class="Module">univalent-combinatorics.counting-fibers-of-maps</a>
<a id="31815" class="Keyword">open</a> <a id="31820" class="Keyword">import</a> <a id="31827" href="univalent-combinatorics.counting-maybe.html" class="Module">univalent-combinatorics.counting-maybe</a>
<a id="31866" class="Keyword">open</a> <a id="31871" class="Keyword">import</a> <a id="31878" href="univalent-combinatorics.counting.html" class="Module">univalent-combinatorics.counting</a>
<a id="31911" class="Keyword">open</a> <a id="31916" class="Keyword">import</a> <a id="31923" href="univalent-combinatorics.cubes.html" class="Module">univalent-combinatorics.cubes</a>
<a id="31953" class="Keyword">open</a> <a id="31958" class="Keyword">import</a> <a id="31965" href="univalent-combinatorics.decidable-dependent-function-types.html" class="Module">univalent-combinatorics.decidable-dependent-function-types</a>
<a id="32024" class="Keyword">open</a> <a id="32029" class="Keyword">import</a> <a id="32036" href="univalent-combinatorics.decidable-dependent-pair-types.html" class="Module">univalent-combinatorics.decidable-dependent-pair-types</a>
<a id="32091" class="Keyword">open</a> <a id="32096" class="Keyword">import</a> <a id="32103" href="univalent-combinatorics.decidable-propositions.html" class="Module">univalent-combinatorics.decidable-propositions</a>
<a id="32150" class="Keyword">open</a> <a id="32155" class="Keyword">import</a> <a id="32162" href="univalent-combinatorics.decidable-subtypes.html" class="Module">univalent-combinatorics.decidable-subtypes</a>
<a id="32205" class="Keyword">open</a> <a id="32210" class="Keyword">import</a> <a id="32217" href="univalent-combinatorics.dedekind-finite-sets.html" class="Module">univalent-combinatorics.dedekind-finite-sets</a>
<a id="32262" class="Keyword">open</a> <a id="32267" class="Keyword">import</a> <a id="32274" href="univalent-combinatorics.dependent-function-types.html" class="Module">univalent-combinatorics.dependent-function-types</a>
<a id="32323" class="Keyword">open</a> <a id="32328" class="Keyword">import</a> <a id="32335" href="univalent-combinatorics.dependent-sum-finite-types.html" class="Module">univalent-combinatorics.dependent-sum-finite-types</a>
<a id="32386" class="Keyword">open</a> <a id="32391" class="Keyword">import</a> <a id="32398" href="univalent-combinatorics.distributivity-of-set-truncation-over-finite-products.html" class="Module">univalent-combinatorics.distributivity-of-set-truncation-over-finite-products</a>
<a id="32476" class="Keyword">open</a> <a id="32481" class="Keyword">import</a> <a id="32488" href="univalent-combinatorics.double-counting.html" class="Module">univalent-combinatorics.double-counting</a>
<a id="32528" class="Keyword">open</a> <a id="32533" class="Keyword">import</a> <a id="32540" href="univalent-combinatorics.embeddings-standard-finite-types.html" class="Module">univalent-combinatorics.embeddings-standard-finite-types</a>
<a id="32597" class="Keyword">open</a> <a id="32602" class="Keyword">import</a> <a id="32609" href="univalent-combinatorics.embeddings.html" class="Module">univalent-combinatorics.embeddings</a>
<a id="32644" class="Keyword">open</a> <a id="32649" class="Keyword">import</a> <a id="32656" href="univalent-combinatorics.equality-finite-types.html" class="Module">univalent-combinatorics.equality-finite-types</a>
<a id="32702" class="Keyword">open</a> <a id="32707" class="Keyword">import</a> <a id="32714" href="univalent-combinatorics.equality-standard-finite-types.html" class="Module">univalent-combinatorics.equality-standard-finite-types</a>
<a id="32769" class="Keyword">open</a> <a id="32774" class="Keyword">import</a> <a id="32781" href="univalent-combinatorics.equivalences-cubes.html" class="Module">univalent-combinatorics.equivalences-cubes</a>
<a id="32824" class="Keyword">open</a> <a id="32829" class="Keyword">import</a> <a id="32836" href="univalent-combinatorics.equivalences-standard-finite-types.html" class="Module">univalent-combinatorics.equivalences-standard-finite-types</a>
<a id="32895" class="Keyword">open</a> <a id="32900" class="Keyword">import</a> <a id="32907" href="univalent-combinatorics.equivalences.html" class="Module">univalent-combinatorics.equivalences</a>
<a id="32944" class="Keyword">open</a> <a id="32949" class="Keyword">import</a> <a id="32956" href="univalent-combinatorics.ferrers-diagrams.html" class="Module">univalent-combinatorics.ferrers-diagrams</a>
<a id="32997" class="Keyword">open</a> <a id="33002" class="Keyword">import</a> <a id="33009" href="univalent-combinatorics.fibers-of-maps.html" class="Module">univalent-combinatorics.fibers-of-maps</a>
<a id="33048" class="Keyword">open</a> <a id="33053" class="Keyword">import</a> <a id="33060" href="univalent-combinatorics.finite-choice.html" class="Module">univalent-combinatorics.finite-choice</a>
<a id="33098" class="Keyword">open</a> <a id="33103" class="Keyword">import</a> <a id="33110" href="univalent-combinatorics.finite-connected-components.html" class="Module">univalent-combinatorics.finite-connected-components</a>
<a id="33162" class="Keyword">open</a> <a id="33167" class="Keyword">import</a> <a id="33174" href="univalent-combinatorics.finite-presentations.html" class="Module">univalent-combinatorics.finite-presentations</a>
<a id="33219" class="Keyword">open</a> <a id="33224" class="Keyword">import</a> <a id="33231" href="univalent-combinatorics.finite-types.html" class="Module">univalent-combinatorics.finite-types</a>
<a id="33268" class="Keyword">open</a> <a id="33273" class="Keyword">import</a> <a id="33280" href="univalent-combinatorics.finitely-presented-types.html" class="Module">univalent-combinatorics.finitely-presented-types</a>
<a id="33329" class="Keyword">open</a> <a id="33334" class="Keyword">import</a> <a id="33341" href="univalent-combinatorics.function-types.html" class="Module">univalent-combinatorics.function-types</a>
<a id="33380" class="Keyword">open</a> <a id="33385" class="Keyword">import</a> <a id="33392" href="univalent-combinatorics.image-of-maps.html" class="Module">univalent-combinatorics.image-of-maps</a>
<a id="33430" class="Keyword">open</a> <a id="33435" class="Keyword">import</a> <a id="33442" href="univalent-combinatorics.inequality-types-with-counting.html" class="Module">univalent-combinatorics.inequality-types-with-counting</a>
<a id="33497" class="Keyword">open</a> <a id="33502" class="Keyword">import</a> <a id="33509" href="univalent-combinatorics.injective-maps.html" class="Module">univalent-combinatorics.injective-maps</a>
<a id="33548" class="Keyword">open</a> <a id="33553" class="Keyword">import</a> <a id="33560" href="univalent-combinatorics.isotopies-latin-squares.html" class="Module">univalent-combinatorics.isotopies-latin-squares</a>
<a id="33608" class="Keyword">open</a> <a id="33613" class="Keyword">import</a> <a id="33620" href="univalent-combinatorics.kuratowsky-finite-sets.html" class="Module">univalent-combinatorics.kuratowsky-finite-sets</a>
<a id="33667" class="Keyword">open</a> <a id="33672" class="Keyword">import</a> <a id="33679" href="univalent-combinatorics.latin-squares.html" class="Module">univalent-combinatorics.latin-squares</a>
<a id="33717" class="Keyword">open</a> <a id="33722" class="Keyword">import</a> <a id="33729" href="univalent-combinatorics.lists.html" class="Module">univalent-combinatorics.lists</a>
<a id="33759" class="Keyword">open</a> <a id="33764" class="Keyword">import</a> <a id="33771" href="univalent-combinatorics.main-classes-of-latin-hypercubes.html" class="Module">univalent-combinatorics.main-classes-of-latin-hypercubes</a>
<a id="33828" class="Keyword">open</a> <a id="33833" class="Keyword">import</a> <a id="33840" href="univalent-combinatorics.main-classes-of-latin-squares.html" class="Module">univalent-combinatorics.main-classes-of-latin-squares</a>
<a id="33894" class="Keyword">open</a> <a id="33899" class="Keyword">import</a> <a id="33906" href="univalent-combinatorics.maybe.html" class="Module">univalent-combinatorics.maybe</a>
<a id="33936" class="Keyword">open</a> <a id="33941" class="Keyword">import</a> <a id="33948" href="univalent-combinatorics.orientations-complete-undirected-graph.html" class="Module">univalent-combinatorics.orientations-complete-undirected-graph</a>
<a id="34011" class="Keyword">open</a> <a id="34016" class="Keyword">import</a> <a id="34023" href="univalent-combinatorics.orientations-cubes.html" class="Module">univalent-combinatorics.orientations-cubes</a>
<a id="34066" class="Keyword">open</a> <a id="34071" class="Keyword">import</a> <a id="34078" href="univalent-combinatorics.petri-nets.html" class="Module">univalent-combinatorics.petri-nets</a>
<a id="34113" class="Keyword">open</a> <a id="34118" class="Keyword">import</a> <a id="34125" href="univalent-combinatorics.pi-finite-types.html" class="Module">univalent-combinatorics.pi-finite-types</a>
<a id="34165" class="Keyword">open</a> <a id="34170" class="Keyword">import</a> <a id="34177" href="univalent-combinatorics.pigeonhole-principle.html" class="Module">univalent-combinatorics.pigeonhole-principle</a>
<a id="34222" class="Keyword">open</a> <a id="34227" class="Keyword">import</a> <a id="34234" href="univalent-combinatorics.presented-pi-finite-types.html" class="Module">univalent-combinatorics.presented-pi-finite-types</a>
<a id="34284" class="Keyword">open</a> <a id="34289" class="Keyword">import</a> <a id="34296" href="univalent-combinatorics.ramsey-theory.html" class="Module">univalent-combinatorics.ramsey-theory</a>
<a id="34334" class="Keyword">open</a> <a id="34339" class="Keyword">import</a> <a id="34346" href="univalent-combinatorics.retracts-of-finite-types.html" class="Module">univalent-combinatorics.retracts-of-finite-types</a>
<a id="34395" class="Keyword">open</a> <a id="34400" class="Keyword">import</a> <a id="34407" href="univalent-combinatorics.sequences-finite-types.html" class="Module">univalent-combinatorics.sequences-finite-types</a>
<a id="34454" class="Keyword">open</a> <a id="34459" class="Keyword">import</a> <a id="34466" href="univalent-combinatorics.skipping-element-standard-finite-types.html" class="Module">univalent-combinatorics.skipping-element-standard-finite-types</a>
<a id="34529" class="Keyword">open</a> <a id="34534" class="Keyword">import</a> <a id="34541" href="univalent-combinatorics.species.html" class="Module">univalent-combinatorics.species</a>
<a id="34573" class="Keyword">open</a> <a id="34578" class="Keyword">import</a> <a id="34585" href="univalent-combinatorics.standard-finite-pruned-trees.html" class="Module">univalent-combinatorics.standard-finite-pruned-trees</a>
<a id="34638" class="Keyword">open</a> <a id="34643" class="Keyword">import</a> <a id="34650" href="univalent-combinatorics.standard-finite-trees.html" class="Module">univalent-combinatorics.standard-finite-trees</a>
<a id="34696" class="Keyword">open</a> <a id="34701" class="Keyword">import</a> <a id="34708" href="univalent-combinatorics.standard-finite-types.html" class="Module">univalent-combinatorics.standard-finite-types</a>
<a id="34754" class="Keyword">open</a> <a id="34759" class="Keyword">import</a> <a id="34766" href="univalent-combinatorics.sums-of-natural-numbers.html" class="Module">univalent-combinatorics.sums-of-natural-numbers</a>
<a id="34814" class="Keyword">open</a> <a id="34819" class="Keyword">import</a> <a id="34826" href="univalent-combinatorics.surjective-maps.html" class="Module">univalent-combinatorics.surjective-maps</a>
<a id="34866" class="Keyword">open</a> <a id="34871" class="Keyword">import</a> <a id="34878" href="univalent-combinatorics.symmetric-difference.html" class="Module">univalent-combinatorics.symmetric-difference</a>
<a id="34923" class="Keyword">open</a> <a id="34928" class="Keyword">import</a> <a id="34935" href="univalent-combinatorics.universal-property-standard-finite-types.html" class="Module">univalent-combinatorics.universal-property-standard-finite-types</a>
</pre>