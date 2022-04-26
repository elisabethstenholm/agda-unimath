# Univalent mathematics in Agda

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

<pre class="Agda"><a id="2967" class="Symbol">{-#</a> <a id="2971" class="Keyword">OPTIONS</a> <a id="2979" class="Pragma">--without-K</a> <a id="2991" class="Pragma">--exact-split</a> <a id="3005" class="Pragma">--guardedness</a> <a id="3019" class="Symbol">#-}</a>
</pre>
## Category theory

<pre class="Agda"><a id="3056" class="Keyword">open</a> <a id="3061" class="Keyword">import</a> <a id="3068" href="category-theory.html" class="Module">category-theory</a>
<a id="3084" class="Keyword">open</a> <a id="3089" class="Keyword">import</a> <a id="3096" href="category-theory.adjunctions-large-precategories.html" class="Module">category-theory.adjunctions-large-precategories</a>
<a id="3144" class="Keyword">open</a> <a id="3149" class="Keyword">import</a> <a id="3156" href="category-theory.anafunctors.html" class="Module">category-theory.anafunctors</a>
<a id="3184" class="Keyword">open</a> <a id="3189" class="Keyword">import</a> <a id="3196" href="category-theory.categories.html" class="Module">category-theory.categories</a>
<a id="3223" class="Keyword">open</a> <a id="3228" class="Keyword">import</a> <a id="3235" href="category-theory.epimorphisms-large-precategories.html" class="Module">category-theory.epimorphisms-large-precategories</a>
<a id="3284" class="Keyword">open</a> <a id="3289" class="Keyword">import</a> <a id="3296" href="category-theory.equivalences-categories.html" class="Module">category-theory.equivalences-categories</a>
<a id="3336" class="Keyword">open</a> <a id="3341" class="Keyword">import</a> <a id="3348" href="category-theory.equivalences-large-precategories.html" class="Module">category-theory.equivalences-large-precategories</a>
<a id="3397" class="Keyword">open</a> <a id="3402" class="Keyword">import</a> <a id="3409" href="category-theory.equivalences-precategories.html" class="Module">category-theory.equivalences-precategories</a>
<a id="3452" class="Keyword">open</a> <a id="3457" class="Keyword">import</a> <a id="3464" href="category-theory.functors-categories.html" class="Module">category-theory.functors-categories</a>
<a id="3500" class="Keyword">open</a> <a id="3505" class="Keyword">import</a> <a id="3512" href="category-theory.functors-large-precategories.html" class="Module">category-theory.functors-large-precategories</a>
<a id="3557" class="Keyword">open</a> <a id="3562" class="Keyword">import</a> <a id="3569" href="category-theory.functors-precategories.html" class="Module">category-theory.functors-precategories</a>
<a id="3608" class="Keyword">open</a> <a id="3613" class="Keyword">import</a> <a id="3620" href="category-theory.homotopies-natural-transformations-large-precategories.html" class="Module">category-theory.homotopies-natural-transformations-large-precategories</a>
<a id="3691" class="Keyword">open</a> <a id="3696" class="Keyword">import</a> <a id="3703" href="category-theory.initial-objects-precategories.html" class="Module">category-theory.initial-objects-precategories</a>
<a id="3749" class="Keyword">open</a> <a id="3754" class="Keyword">import</a> <a id="3761" href="category-theory.isomorphisms-categories.html" class="Module">category-theory.isomorphisms-categories</a>
<a id="3801" class="Keyword">open</a> <a id="3806" class="Keyword">import</a> <a id="3813" href="category-theory.isomorphisms-large-precategories.html" class="Module">category-theory.isomorphisms-large-precategories</a>
<a id="3862" class="Keyword">open</a> <a id="3867" class="Keyword">import</a> <a id="3874" href="category-theory.isomorphisms-precategories.html" class="Module">category-theory.isomorphisms-precategories</a>
<a id="3917" class="Keyword">open</a> <a id="3922" class="Keyword">import</a> <a id="3929" href="category-theory.large-categories.html" class="Module">category-theory.large-categories</a>
<a id="3962" class="Keyword">open</a> <a id="3967" class="Keyword">import</a> <a id="3974" href="category-theory.large-precategories.html" class="Module">category-theory.large-precategories</a>
<a id="4010" class="Keyword">open</a> <a id="4015" class="Keyword">import</a> <a id="4022" href="category-theory.monomorphisms-large-precategories.html" class="Module">category-theory.monomorphisms-large-precategories</a>
<a id="4072" class="Keyword">open</a> <a id="4077" class="Keyword">import</a> <a id="4084" href="category-theory.natural-isomorphisms-categories.html" class="Module">category-theory.natural-isomorphisms-categories</a>
<a id="4132" class="Keyword">open</a> <a id="4137" class="Keyword">import</a> <a id="4144" href="category-theory.natural-isomorphisms-large-precategories.html" class="Module">category-theory.natural-isomorphisms-large-precategories</a>
<a id="4201" class="Keyword">open</a> <a id="4206" class="Keyword">import</a> <a id="4213" href="category-theory.natural-isomorphisms-precategories.html" class="Module">category-theory.natural-isomorphisms-precategories</a>
<a id="4264" class="Keyword">open</a> <a id="4269" class="Keyword">import</a> <a id="4276" href="category-theory.natural-transformations-categories.html" class="Module">category-theory.natural-transformations-categories</a>
<a id="4327" class="Keyword">open</a> <a id="4332" class="Keyword">import</a> <a id="4339" href="category-theory.natural-transformations-large-precategories.html" class="Module">category-theory.natural-transformations-large-precategories</a>
<a id="4399" class="Keyword">open</a> <a id="4404" class="Keyword">import</a> <a id="4411" href="category-theory.natural-transformations-precategories.html" class="Module">category-theory.natural-transformations-precategories</a>
<a id="4465" class="Keyword">open</a> <a id="4470" class="Keyword">import</a> <a id="4477" href="category-theory.precategories.html" class="Module">category-theory.precategories</a>
<a id="4507" class="Keyword">open</a> <a id="4512" class="Keyword">import</a> <a id="4519" href="category-theory.slice-precategories.html" class="Module">category-theory.slice-precategories</a>
<a id="4555" class="Keyword">open</a> <a id="4560" class="Keyword">import</a> <a id="4567" href="category-theory.terminal-objects-precategories.html" class="Module">category-theory.terminal-objects-precategories</a>
</pre>
## Commutative algebra

<pre class="Agda"><a id="4651" class="Keyword">open</a> <a id="4656" class="Keyword">import</a> <a id="4663" href="commutative-algebra.html" class="Module">commutative-algebra</a>
<a id="4683" class="Keyword">open</a> <a id="4688" class="Keyword">import</a> <a id="4695" href="commutative-algebra.commutative-rings.html" class="Module">commutative-algebra.commutative-rings</a>
<a id="4733" class="Keyword">open</a> <a id="4738" class="Keyword">import</a> <a id="4745" href="commutative-algebra.discrete-fields.html" class="Module">commutative-algebra.discrete-fields</a>
<a id="4781" class="Keyword">open</a> <a id="4786" class="Keyword">import</a> <a id="4793" href="commutative-algebra.eisenstein-integers.html" class="Module">commutative-algebra.eisenstein-integers</a>
<a id="4833" class="Keyword">open</a> <a id="4838" class="Keyword">import</a> <a id="4845" href="commutative-algebra.gaussian-integers.html" class="Module">commutative-algebra.gaussian-integers</a>
<a id="4883" class="Keyword">open</a> <a id="4888" class="Keyword">import</a> <a id="4895" href="commutative-algebra.homomorphisms-commutative-rings.html" class="Module">commutative-algebra.homomorphisms-commutative-rings</a>
<a id="4947" class="Keyword">open</a> <a id="4952" class="Keyword">import</a> <a id="4959" href="commutative-algebra.ideals-commutative-rings.html" class="Module">commutative-algebra.ideals-commutative-rings</a>
<a id="5004" class="Keyword">open</a> <a id="5009" class="Keyword">import</a> <a id="5016" href="commutative-algebra.isomorphisms-commutative-rings.html" class="Module">commutative-algebra.isomorphisms-commutative-rings</a>
</pre>
## Elementary number theory

<pre class="Agda"><a id="5109" class="Keyword">open</a> <a id="5114" class="Keyword">import</a> <a id="5121" href="elementary-number-theory.html" class="Module">elementary-number-theory</a>
<a id="5146" class="Keyword">open</a> <a id="5151" class="Keyword">import</a> <a id="5158" href="elementary-number-theory.absolute-value-integers.html" class="Module">elementary-number-theory.absolute-value-integers</a>
<a id="5207" class="Keyword">open</a> <a id="5212" class="Keyword">import</a> <a id="5219" href="elementary-number-theory.addition-integers.html" class="Module">elementary-number-theory.addition-integers</a>
<a id="5262" class="Keyword">open</a> <a id="5267" class="Keyword">import</a> <a id="5274" href="elementary-number-theory.addition-natural-numbers.html" class="Module">elementary-number-theory.addition-natural-numbers</a>
<a id="5324" class="Keyword">open</a> <a id="5329" class="Keyword">import</a> <a id="5336" href="elementary-number-theory.arithmetic-functions.html" class="Module">elementary-number-theory.arithmetic-functions</a>
<a id="5382" class="Keyword">open</a> <a id="5387" class="Keyword">import</a> <a id="5394" href="elementary-number-theory.binomial-coefficients.html" class="Module">elementary-number-theory.binomial-coefficients</a>
<a id="5441" class="Keyword">open</a> <a id="5446" class="Keyword">import</a> <a id="5453" href="elementary-number-theory.bounded-sums-arithmetic-functions.html" class="Module">elementary-number-theory.bounded-sums-arithmetic-functions</a>
<a id="5512" class="Keyword">open</a> <a id="5517" class="Keyword">import</a> <a id="5524" href="elementary-number-theory.catalan-numbers.html" class="Module">elementary-number-theory.catalan-numbers</a>
<a id="5565" class="Keyword">open</a> <a id="5570" class="Keyword">import</a> <a id="5577" href="elementary-number-theory.collatz-bijection.html" class="Module">elementary-number-theory.collatz-bijection</a>
<a id="5620" class="Keyword">open</a> <a id="5625" class="Keyword">import</a> <a id="5632" href="elementary-number-theory.collatz-conjecture.html" class="Module">elementary-number-theory.collatz-conjecture</a>
<a id="5676" class="Keyword">open</a> <a id="5681" class="Keyword">import</a> <a id="5688" href="elementary-number-theory.congruence-integers.html" class="Module">elementary-number-theory.congruence-integers</a>
<a id="5733" class="Keyword">open</a> <a id="5738" class="Keyword">import</a> <a id="5745" href="elementary-number-theory.congruence-natural-numbers.html" class="Module">elementary-number-theory.congruence-natural-numbers</a>
<a id="5797" class="Keyword">open</a> <a id="5802" class="Keyword">import</a> <a id="5809" href="elementary-number-theory.decidable-dependent-function-types.html" class="Module">elementary-number-theory.decidable-dependent-function-types</a>
<a id="5869" class="Keyword">open</a> <a id="5874" class="Keyword">import</a> <a id="5881" href="elementary-number-theory.decidable-types.html" class="Module">elementary-number-theory.decidable-types</a>
<a id="5922" class="Keyword">open</a> <a id="5927" class="Keyword">import</a> <a id="5934" href="elementary-number-theory.difference-integers.html" class="Module">elementary-number-theory.difference-integers</a>
<a id="5979" class="Keyword">open</a> <a id="5984" class="Keyword">import</a> <a id="5991" href="elementary-number-theory.dirichlet-convolution.html" class="Module">elementary-number-theory.dirichlet-convolution</a>
<a id="6038" class="Keyword">open</a> <a id="6043" class="Keyword">import</a> <a id="6050" href="elementary-number-theory.distance-integers.html" class="Module">elementary-number-theory.distance-integers</a>
<a id="6093" class="Keyword">open</a> <a id="6098" class="Keyword">import</a> <a id="6105" href="elementary-number-theory.distance-natural-numbers.html" class="Module">elementary-number-theory.distance-natural-numbers</a>
<a id="6155" class="Keyword">open</a> <a id="6160" class="Keyword">import</a> <a id="6167" href="elementary-number-theory.divisibility-integers.html" class="Module">elementary-number-theory.divisibility-integers</a>
<a id="6214" class="Keyword">open</a> <a id="6219" class="Keyword">import</a> <a id="6226" href="elementary-number-theory.divisibility-modular-arithmetic.html" class="Module">elementary-number-theory.divisibility-modular-arithmetic</a>
<a id="6283" class="Keyword">open</a> <a id="6288" class="Keyword">import</a> <a id="6295" href="elementary-number-theory.divisibility-natural-numbers.html" class="Module">elementary-number-theory.divisibility-natural-numbers</a>
<a id="6349" class="Keyword">open</a> <a id="6354" class="Keyword">import</a> <a id="6361" href="elementary-number-theory.divisibility-standard-finite-types.html" class="Module">elementary-number-theory.divisibility-standard-finite-types</a>
<a id="6421" class="Keyword">open</a> <a id="6426" class="Keyword">import</a> <a id="6433" href="elementary-number-theory.equality-integers.html" class="Module">elementary-number-theory.equality-integers</a>
<a id="6476" class="Keyword">open</a> <a id="6481" class="Keyword">import</a> <a id="6488" href="elementary-number-theory.equality-natural-numbers.html" class="Module">elementary-number-theory.equality-natural-numbers</a>
<a id="6538" class="Keyword">open</a> <a id="6543" class="Keyword">import</a> <a id="6550" href="elementary-number-theory.euclidean-division-natural-numbers.html" class="Module">elementary-number-theory.euclidean-division-natural-numbers</a>
<a id="6610" class="Keyword">open</a> <a id="6615" class="Keyword">import</a> <a id="6622" href="elementary-number-theory.eulers-totient-function.html" class="Module">elementary-number-theory.eulers-totient-function</a>
<a id="6671" class="Keyword">open</a> <a id="6676" class="Keyword">import</a> <a id="6683" href="elementary-number-theory.exponentiation-natural-numbers.html" class="Module">elementary-number-theory.exponentiation-natural-numbers</a>
<a id="6739" class="Keyword">open</a> <a id="6744" class="Keyword">import</a> <a id="6751" href="elementary-number-theory.factorials.html" class="Module">elementary-number-theory.factorials</a>
<a id="6787" class="Keyword">open</a> <a id="6792" class="Keyword">import</a> <a id="6799" href="elementary-number-theory.falling-factorials.html" class="Module">elementary-number-theory.falling-factorials</a>
<a id="6843" class="Keyword">open</a> <a id="6848" class="Keyword">import</a> <a id="6855" href="elementary-number-theory.fibonacci-sequence.html" class="Module">elementary-number-theory.fibonacci-sequence</a>
<a id="6899" class="Keyword">open</a> <a id="6904" class="Keyword">import</a> <a id="6911" href="elementary-number-theory.finitary-natural-numbers.html" class="Module">elementary-number-theory.finitary-natural-numbers</a>
<a id="6961" class="Keyword">open</a> <a id="6966" class="Keyword">import</a> <a id="6973" href="elementary-number-theory.finitely-cyclic-maps.html" class="Module">elementary-number-theory.finitely-cyclic-maps</a>
<a id="7019" class="Keyword">open</a> <a id="7024" class="Keyword">import</a> <a id="7031" href="elementary-number-theory.fractions.html" class="Module">elementary-number-theory.fractions</a>
<a id="7066" class="Keyword">open</a> <a id="7071" class="Keyword">import</a> <a id="7078" href="elementary-number-theory.goldbach-conjecture.html" class="Module">elementary-number-theory.goldbach-conjecture</a>
<a id="7123" class="Keyword">open</a> <a id="7128" class="Keyword">import</a> <a id="7135" href="elementary-number-theory.greatest-common-divisor-integers.html" class="Module">elementary-number-theory.greatest-common-divisor-integers</a>
<a id="7193" class="Keyword">open</a> <a id="7198" class="Keyword">import</a> <a id="7205" href="elementary-number-theory.greatest-common-divisor-natural-numbers.html" class="Module">elementary-number-theory.greatest-common-divisor-natural-numbers</a>
<a id="7270" class="Keyword">open</a> <a id="7275" class="Keyword">import</a> <a id="7282" href="elementary-number-theory.group-of-integers.html" class="Module">elementary-number-theory.group-of-integers</a>
<a id="7325" class="Keyword">open</a> <a id="7330" class="Keyword">import</a> <a id="7337" href="elementary-number-theory.groups-of-modular-arithmetic.html" class="Module">elementary-number-theory.groups-of-modular-arithmetic</a>
<a id="7391" class="Keyword">open</a> <a id="7396" class="Keyword">import</a> <a id="7403" href="elementary-number-theory.inequality-integers.html" class="Module">elementary-number-theory.inequality-integers</a>
<a id="7448" class="Keyword">open</a> <a id="7453" class="Keyword">import</a> <a id="7460" href="elementary-number-theory.inequality-natural-numbers.html" class="Module">elementary-number-theory.inequality-natural-numbers</a>
<a id="7512" class="Keyword">open</a> <a id="7517" class="Keyword">import</a> <a id="7524" href="elementary-number-theory.inequality-standard-finite-types.html" class="Module">elementary-number-theory.inequality-standard-finite-types</a>
<a id="7582" class="Keyword">open</a> <a id="7587" class="Keyword">import</a> <a id="7594" href="elementary-number-theory.infinitude-of-primes.html" class="Module">elementary-number-theory.infinitude-of-primes</a>
<a id="7640" class="Keyword">open</a> <a id="7645" class="Keyword">import</a> <a id="7652" href="elementary-number-theory.integer-partitions.html" class="Module">elementary-number-theory.integer-partitions</a>
<a id="7696" class="Keyword">open</a> <a id="7701" class="Keyword">import</a> <a id="7708" href="elementary-number-theory.integers.html" class="Module">elementary-number-theory.integers</a>
<a id="7742" class="Keyword">open</a> <a id="7747" class="Keyword">import</a> <a id="7754" href="elementary-number-theory.iterating-functions.html" class="Module">elementary-number-theory.iterating-functions</a>
<a id="7799" class="Keyword">open</a> <a id="7804" class="Keyword">import</a> <a id="7811" href="elementary-number-theory.lower-bounds-natural-numbers.html" class="Module">elementary-number-theory.lower-bounds-natural-numbers</a>
<a id="7865" class="Keyword">open</a> <a id="7870" class="Keyword">import</a> <a id="7877" href="elementary-number-theory.maximum-natural-numbers.html" class="Module">elementary-number-theory.maximum-natural-numbers</a>
<a id="7926" class="Keyword">open</a> <a id="7931" class="Keyword">import</a> <a id="7938" href="elementary-number-theory.mersenne-primes.html" class="Module">elementary-number-theory.mersenne-primes</a>
<a id="7979" class="Keyword">open</a> <a id="7984" class="Keyword">import</a> <a id="7991" href="elementary-number-theory.minimum-natural-numbers.html" class="Module">elementary-number-theory.minimum-natural-numbers</a>
<a id="8040" class="Keyword">open</a> <a id="8045" class="Keyword">import</a> <a id="8052" href="elementary-number-theory.modular-arithmetic-standard-finite-types.html" class="Module">elementary-number-theory.modular-arithmetic-standard-finite-types</a>
<a id="8118" class="Keyword">open</a> <a id="8123" class="Keyword">import</a> <a id="8130" href="elementary-number-theory.modular-arithmetic.html" class="Module">elementary-number-theory.modular-arithmetic</a>
<a id="8174" class="Keyword">open</a> <a id="8179" class="Keyword">import</a> <a id="8186" href="elementary-number-theory.multiplication-integers.html" class="Module">elementary-number-theory.multiplication-integers</a>
<a id="8235" class="Keyword">open</a> <a id="8240" class="Keyword">import</a> <a id="8247" href="elementary-number-theory.multiplication-natural-numbers.html" class="Module">elementary-number-theory.multiplication-natural-numbers</a>
<a id="8303" class="Keyword">open</a> <a id="8308" class="Keyword">import</a> <a id="8315" href="elementary-number-theory.natural-numbers.html" class="Module">elementary-number-theory.natural-numbers</a>
<a id="8356" class="Keyword">open</a> <a id="8361" class="Keyword">import</a> <a id="8368" href="elementary-number-theory.nonzero-natural-numbers.html" class="Module">elementary-number-theory.nonzero-natural-numbers</a>
<a id="8417" class="Keyword">open</a> <a id="8422" class="Keyword">import</a> <a id="8429" href="elementary-number-theory.ordinal-induction-natural-numbers.html" class="Module">elementary-number-theory.ordinal-induction-natural-numbers</a>
<a id="8488" class="Keyword">open</a> <a id="8493" class="Keyword">import</a> <a id="8500" href="elementary-number-theory.prime-numbers.html" class="Module">elementary-number-theory.prime-numbers</a>
<a id="8539" class="Keyword">open</a> <a id="8544" class="Keyword">import</a> <a id="8551" href="elementary-number-theory.products-of-natural-numbers.html" class="Module">elementary-number-theory.products-of-natural-numbers</a>
<a id="8604" class="Keyword">open</a> <a id="8609" class="Keyword">import</a> <a id="8616" href="elementary-number-theory.proper-divisors-natural-numbers.html" class="Module">elementary-number-theory.proper-divisors-natural-numbers</a>
<a id="8673" class="Keyword">open</a> <a id="8678" class="Keyword">import</a> <a id="8685" href="elementary-number-theory.rational-numbers.html" class="Module">elementary-number-theory.rational-numbers</a>
<a id="8727" class="Keyword">open</a> <a id="8732" class="Keyword">import</a> <a id="8739" href="elementary-number-theory.relatively-prime-integers.html" class="Module">elementary-number-theory.relatively-prime-integers</a>
<a id="8790" class="Keyword">open</a> <a id="8795" class="Keyword">import</a> <a id="8802" href="elementary-number-theory.relatively-prime-natural-numbers.html" class="Module">elementary-number-theory.relatively-prime-natural-numbers</a>
<a id="8860" class="Keyword">open</a> <a id="8865" class="Keyword">import</a> <a id="8872" href="elementary-number-theory.repeating-element-standard-finite-type.html" class="Module">elementary-number-theory.repeating-element-standard-finite-type</a>
<a id="8936" class="Keyword">open</a> <a id="8941" class="Keyword">import</a> <a id="8948" href="elementary-number-theory.retracts-of-natural-numbers.html" class="Module">elementary-number-theory.retracts-of-natural-numbers</a>
<a id="9001" class="Keyword">open</a> <a id="9006" class="Keyword">import</a> <a id="9013" href="elementary-number-theory.square-free-natural-numbers.html" class="Module">elementary-number-theory.square-free-natural-numbers</a>
<a id="9066" class="Keyword">open</a> <a id="9071" class="Keyword">import</a> <a id="9078" href="elementary-number-theory.stirling-numbers-of-the-second-kind.html" class="Module">elementary-number-theory.stirling-numbers-of-the-second-kind</a>
<a id="9139" class="Keyword">open</a> <a id="9144" class="Keyword">import</a> <a id="9151" href="elementary-number-theory.strong-induction-natural-numbers.html" class="Module">elementary-number-theory.strong-induction-natural-numbers</a>
<a id="9209" class="Keyword">open</a> <a id="9214" class="Keyword">import</a> <a id="9221" href="elementary-number-theory.sums-of-natural-numbers.html" class="Module">elementary-number-theory.sums-of-natural-numbers</a>
<a id="9270" class="Keyword">open</a> <a id="9275" class="Keyword">import</a> <a id="9282" href="elementary-number-theory.telephone-numbers.html" class="Module">elementary-number-theory.telephone-numbers</a>
<a id="9325" class="Keyword">open</a> <a id="9330" class="Keyword">import</a> <a id="9337" href="elementary-number-theory.triangular-numbers.html" class="Module">elementary-number-theory.triangular-numbers</a>
<a id="9381" class="Keyword">open</a> <a id="9386" class="Keyword">import</a> <a id="9393" href="elementary-number-theory.twin-prime-conjecture.html" class="Module">elementary-number-theory.twin-prime-conjecture</a>
<a id="9440" class="Keyword">open</a> <a id="9445" class="Keyword">import</a> <a id="9452" href="elementary-number-theory.unit-elements-standard-finite-types.html" class="Module">elementary-number-theory.unit-elements-standard-finite-types</a>
<a id="9513" class="Keyword">open</a> <a id="9518" class="Keyword">import</a> <a id="9525" href="elementary-number-theory.unit-similarity-standard-finite-types.html" class="Module">elementary-number-theory.unit-similarity-standard-finite-types</a>
<a id="9588" class="Keyword">open</a> <a id="9593" class="Keyword">import</a> <a id="9600" href="elementary-number-theory.universal-property-natural-numbers.html" class="Module">elementary-number-theory.universal-property-natural-numbers</a>
<a id="9660" class="Keyword">open</a> <a id="9665" class="Keyword">import</a> <a id="9672" href="elementary-number-theory.upper-bounds-natural-numbers.html" class="Module">elementary-number-theory.upper-bounds-natural-numbers</a>
<a id="9726" class="Keyword">open</a> <a id="9731" class="Keyword">import</a> <a id="9738" href="elementary-number-theory.well-ordering-principle-natural-numbers.html" class="Module">elementary-number-theory.well-ordering-principle-natural-numbers</a>
<a id="9803" class="Keyword">open</a> <a id="9808" class="Keyword">import</a> <a id="9815" href="elementary-number-theory.well-ordering-principle-standard-finite-types.html" class="Module">elementary-number-theory.well-ordering-principle-standard-finite-types</a>
</pre>
## Finite group theory

<pre class="Agda"><a id="9923" class="Keyword">open</a> <a id="9928" class="Keyword">import</a> <a id="9935" href="finite-group-theory.html" class="Module">finite-group-theory</a>
<a id="9955" class="Keyword">open</a> <a id="9960" class="Keyword">import</a> <a id="9967" href="finite-group-theory.abstract-quaternion-group.html" class="Module">finite-group-theory.abstract-quaternion-group</a>
<a id="10013" class="Keyword">open</a> <a id="10018" class="Keyword">import</a> <a id="10025" href="finite-group-theory.concrete-quaternion-group.html" class="Module">finite-group-theory.concrete-quaternion-group</a>
<a id="10071" class="Keyword">open</a> <a id="10076" class="Keyword">import</a> <a id="10083" href="finite-group-theory.finite-groups.html" class="Module">finite-group-theory.finite-groups</a>
<a id="10117" class="Keyword">open</a> <a id="10122" class="Keyword">import</a> <a id="10129" href="finite-group-theory.finite-monoids.html" class="Module">finite-group-theory.finite-monoids</a>
<a id="10164" class="Keyword">open</a> <a id="10169" class="Keyword">import</a> <a id="10176" href="finite-group-theory.finite-semigroups.html" class="Module">finite-group-theory.finite-semigroups</a>
<a id="10214" class="Keyword">open</a> <a id="10219" class="Keyword">import</a> <a id="10226" href="finite-group-theory.groups-of-order-2.html" class="Module">finite-group-theory.groups-of-order-2</a>
<a id="10264" class="Keyword">open</a> <a id="10269" class="Keyword">import</a> <a id="10276" href="finite-group-theory.orbits-permutations.html" class="Module">finite-group-theory.orbits-permutations</a>
<a id="10316" class="Keyword">open</a> <a id="10321" class="Keyword">import</a> <a id="10328" href="finite-group-theory.permutations.html" class="Module">finite-group-theory.permutations</a>
<a id="10361" class="Keyword">open</a> <a id="10366" class="Keyword">import</a> <a id="10373" href="finite-group-theory.sign-homomorphism.html" class="Module">finite-group-theory.sign-homomorphism</a>
<a id="10411" class="Keyword">open</a> <a id="10416" class="Keyword">import</a> <a id="10423" href="finite-group-theory.transpositions.html" class="Module">finite-group-theory.transpositions</a>
</pre>
## Foundation

<pre class="Agda"><a id="10486" class="Keyword">open</a> <a id="10491" class="Keyword">import</a> <a id="10498" href="foundation.html" class="Module">foundation</a>
<a id="10509" class="Keyword">open</a> <a id="10514" class="Keyword">import</a> <a id="10521" href="foundation.0-maps.html" class="Module">foundation.0-maps</a>
<a id="10539" class="Keyword">open</a> <a id="10544" class="Keyword">import</a> <a id="10551" href="foundation.1-types.html" class="Module">foundation.1-types</a>
<a id="10570" class="Keyword">open</a> <a id="10575" class="Keyword">import</a> <a id="10582" href="foundation.2-types.html" class="Module">foundation.2-types</a>
<a id="10601" class="Keyword">open</a> <a id="10606" class="Keyword">import</a> <a id="10613" href="foundation.algebras-polynomial-endofunctors.html" class="Module">foundation.algebras-polynomial-endofunctors</a>
<a id="10657" class="Keyword">open</a> <a id="10662" class="Keyword">import</a> <a id="10669" href="foundation.automorphisms.html" class="Module">foundation.automorphisms</a>
<a id="10694" class="Keyword">open</a> <a id="10699" class="Keyword">import</a> <a id="10706" href="foundation.axiom-of-choice.html" class="Module">foundation.axiom-of-choice</a>
<a id="10733" class="Keyword">open</a> <a id="10738" class="Keyword">import</a> <a id="10745" href="foundation.binary-embeddings.html" class="Module">foundation.binary-embeddings</a>
<a id="10774" class="Keyword">open</a> <a id="10779" class="Keyword">import</a> <a id="10786" href="foundation.binary-equivalences.html" class="Module">foundation.binary-equivalences</a>
<a id="10817" class="Keyword">open</a> <a id="10822" class="Keyword">import</a> <a id="10829" href="foundation.binary-relations.html" class="Module">foundation.binary-relations</a>
<a id="10857" class="Keyword">open</a> <a id="10862" class="Keyword">import</a> <a id="10869" href="foundation.boolean-reflection.html" class="Module">foundation.boolean-reflection</a>
<a id="10899" class="Keyword">open</a> <a id="10904" class="Keyword">import</a> <a id="10911" href="foundation.booleans.html" class="Module">foundation.booleans</a>
<a id="10931" class="Keyword">open</a> <a id="10936" class="Keyword">import</a> <a id="10943" href="foundation.cantors-diagonal-argument.html" class="Module">foundation.cantors-diagonal-argument</a>
<a id="10980" class="Keyword">open</a> <a id="10985" class="Keyword">import</a> <a id="10992" href="foundation.cartesian-product-types.html" class="Module">foundation.cartesian-product-types</a>
<a id="11027" class="Keyword">open</a> <a id="11032" class="Keyword">import</a> <a id="11039" href="foundation.choice-of-representatives-equivalence-relation.html" class="Module">foundation.choice-of-representatives-equivalence-relation</a>
<a id="11097" class="Keyword">open</a> <a id="11102" class="Keyword">import</a> <a id="11109" href="foundation.coherently-invertible-maps.html" class="Module">foundation.coherently-invertible-maps</a>
<a id="11147" class="Keyword">open</a> <a id="11152" class="Keyword">import</a> <a id="11159" href="foundation.commuting-squares.html" class="Module">foundation.commuting-squares</a>
<a id="11188" class="Keyword">open</a> <a id="11193" class="Keyword">import</a> <a id="11200" href="foundation.complements.html" class="Module">foundation.complements</a>
<a id="11223" class="Keyword">open</a> <a id="11228" class="Keyword">import</a> <a id="11235" href="foundation.conjunction.html" class="Module">foundation.conjunction</a>
<a id="11258" class="Keyword">open</a> <a id="11263" class="Keyword">import</a> <a id="11270" href="foundation.connected-components-universes.html" class="Module">foundation.connected-components-universes</a>
<a id="11312" class="Keyword">open</a> <a id="11317" class="Keyword">import</a> <a id="11324" href="foundation.connected-components.html" class="Module">foundation.connected-components</a>
<a id="11356" class="Keyword">open</a> <a id="11361" class="Keyword">import</a> <a id="11368" href="foundation.connected-types.html" class="Module">foundation.connected-types</a>
<a id="11395" class="Keyword">open</a> <a id="11400" class="Keyword">import</a> <a id="11407" href="foundation.constant-maps.html" class="Module">foundation.constant-maps</a>
<a id="11432" class="Keyword">open</a> <a id="11437" class="Keyword">import</a> <a id="11444" href="foundation.contractible-maps.html" class="Module">foundation.contractible-maps</a>
<a id="11473" class="Keyword">open</a> <a id="11478" class="Keyword">import</a> <a id="11485" href="foundation.contractible-types.html" class="Module">foundation.contractible-types</a>
<a id="11515" class="Keyword">open</a> <a id="11520" class="Keyword">import</a> <a id="11527" href="foundation.coproduct-types.html" class="Module">foundation.coproduct-types</a>
<a id="11554" class="Keyword">open</a> <a id="11559" class="Keyword">import</a> <a id="11566" href="foundation.coslice.html" class="Module">foundation.coslice</a>
<a id="11585" class="Keyword">open</a> <a id="11590" class="Keyword">import</a> <a id="11597" href="foundation.decidable-dependent-function-types.html" class="Module">foundation.decidable-dependent-function-types</a>
<a id="11643" class="Keyword">open</a> <a id="11648" class="Keyword">import</a> <a id="11655" href="foundation.decidable-dependent-pair-types.html" class="Module">foundation.decidable-dependent-pair-types</a>
<a id="11697" class="Keyword">open</a> <a id="11702" class="Keyword">import</a> <a id="11709" href="foundation.decidable-embeddings.html" class="Module">foundation.decidable-embeddings</a>
<a id="11741" class="Keyword">open</a> <a id="11746" class="Keyword">import</a> <a id="11753" href="foundation.decidable-equality.html" class="Module">foundation.decidable-equality</a>
<a id="11783" class="Keyword">open</a> <a id="11788" class="Keyword">import</a> <a id="11795" href="foundation.decidable-maps.html" class="Module">foundation.decidable-maps</a>
<a id="11821" class="Keyword">open</a> <a id="11826" class="Keyword">import</a> <a id="11833" href="foundation.decidable-propositions.html" class="Module">foundation.decidable-propositions</a>
<a id="11867" class="Keyword">open</a> <a id="11872" class="Keyword">import</a> <a id="11879" href="foundation.decidable-subtypes.html" class="Module">foundation.decidable-subtypes</a>
<a id="11909" class="Keyword">open</a> <a id="11914" class="Keyword">import</a> <a id="11921" href="foundation.decidable-types.html" class="Module">foundation.decidable-types</a>
<a id="11948" class="Keyword">open</a> <a id="11953" class="Keyword">import</a> <a id="11960" href="foundation.dependent-pair-types.html" class="Module">foundation.dependent-pair-types</a>
<a id="11992" class="Keyword">open</a> <a id="11997" class="Keyword">import</a> <a id="12004" href="foundation.diagonal-maps-of-types.html" class="Module">foundation.diagonal-maps-of-types</a>
<a id="12038" class="Keyword">open</a> <a id="12043" class="Keyword">import</a> <a id="12050" href="foundation.disjunction.html" class="Module">foundation.disjunction</a>
<a id="12073" class="Keyword">open</a> <a id="12078" class="Keyword">import</a> <a id="12085" href="foundation.distributivity-of-dependent-functions-over-coproduct-types.html" class="Module">foundation.distributivity-of-dependent-functions-over-coproduct-types</a>
<a id="12155" class="Keyword">open</a> <a id="12160" class="Keyword">import</a> <a id="12167" href="foundation.distributivity-of-dependent-functions-over-dependent-pairs.html" class="Module">foundation.distributivity-of-dependent-functions-over-dependent-pairs</a>
<a id="12237" class="Keyword">open</a> <a id="12242" class="Keyword">import</a> <a id="12249" href="foundation.double-negation.html" class="Module">foundation.double-negation</a>
<a id="12276" class="Keyword">open</a> <a id="12281" class="Keyword">import</a> <a id="12288" href="foundation.double-powersets.html" class="Module">foundation.double-powersets</a>
<a id="12316" class="Keyword">open</a> <a id="12321" class="Keyword">import</a> <a id="12328" href="foundation.dubuc-penon-compact-types.html" class="Module">foundation.dubuc-penon-compact-types</a>
<a id="12365" class="Keyword">open</a> <a id="12370" class="Keyword">import</a> <a id="12377" href="foundation.effective-maps-equivalence-relations.html" class="Module">foundation.effective-maps-equivalence-relations</a>
<a id="12425" class="Keyword">open</a> <a id="12430" class="Keyword">import</a> <a id="12437" href="foundation.elementhood-relation-w-types.html" class="Module">foundation.elementhood-relation-w-types</a>
<a id="12477" class="Keyword">open</a> <a id="12482" class="Keyword">import</a> <a id="12489" href="foundation.embeddings.html" class="Module">foundation.embeddings</a>
<a id="12511" class="Keyword">open</a> <a id="12516" class="Keyword">import</a> <a id="12523" href="foundation.empty-types.html" class="Module">foundation.empty-types</a>
<a id="12546" class="Keyword">open</a> <a id="12551" class="Keyword">import</a> <a id="12558" href="foundation.epimorphisms-with-respect-to-sets.html" class="Module">foundation.epimorphisms-with-respect-to-sets</a>
<a id="12603" class="Keyword">open</a> <a id="12608" class="Keyword">import</a> <a id="12615" href="foundation.equality-cartesian-product-types.html" class="Module">foundation.equality-cartesian-product-types</a>
<a id="12659" class="Keyword">open</a> <a id="12664" class="Keyword">import</a> <a id="12671" href="foundation.equality-coproduct-types.html" class="Module">foundation.equality-coproduct-types</a>
<a id="12707" class="Keyword">open</a> <a id="12712" class="Keyword">import</a> <a id="12719" href="foundation.equality-dependent-function-types.html" class="Module">foundation.equality-dependent-function-types</a>
<a id="12764" class="Keyword">open</a> <a id="12769" class="Keyword">import</a> <a id="12776" href="foundation.equality-dependent-pair-types.html" class="Module">foundation.equality-dependent-pair-types</a>
<a id="12817" class="Keyword">open</a> <a id="12822" class="Keyword">import</a> <a id="12829" href="foundation.equality-fibers-of-maps.html" class="Module">foundation.equality-fibers-of-maps</a>
<a id="12864" class="Keyword">open</a> <a id="12869" class="Keyword">import</a> <a id="12876" href="foundation.equivalence-classes.html" class="Module">foundation.equivalence-classes</a>
<a id="12907" class="Keyword">open</a> <a id="12912" class="Keyword">import</a> <a id="12919" href="foundation.equivalence-induction.html" class="Module">foundation.equivalence-induction</a>
<a id="12952" class="Keyword">open</a> <a id="12957" class="Keyword">import</a> <a id="12964" href="foundation.equivalence-relations.html" class="Module">foundation.equivalence-relations</a>
<a id="12997" class="Keyword">open</a> <a id="13002" class="Keyword">import</a> <a id="13009" href="foundation.equivalences-maybe.html" class="Module">foundation.equivalences-maybe</a>
<a id="13039" class="Keyword">open</a> <a id="13044" class="Keyword">import</a> <a id="13051" href="foundation.equivalences.html" class="Module">foundation.equivalences</a>
<a id="13075" class="Keyword">open</a> <a id="13080" class="Keyword">import</a> <a id="13087" href="foundation.existential-quantification.html" class="Module">foundation.existential-quantification</a>
<a id="13125" class="Keyword">open</a> <a id="13130" class="Keyword">import</a> <a id="13137" href="foundation.extensional-w-types.html" class="Module">foundation.extensional-w-types</a>
<a id="13168" class="Keyword">open</a> <a id="13173" class="Keyword">import</a> <a id="13180" href="foundation.faithful-maps.html" class="Module">foundation.faithful-maps</a>
<a id="13205" class="Keyword">open</a> <a id="13210" class="Keyword">import</a> <a id="13217" href="foundation.fiber-inclusions.html" class="Module">foundation.fiber-inclusions</a>
<a id="13245" class="Keyword">open</a> <a id="13250" class="Keyword">import</a> <a id="13257" href="foundation.fibered-maps.html" class="Module">foundation.fibered-maps</a>
<a id="13281" class="Keyword">open</a> <a id="13286" class="Keyword">import</a> <a id="13293" href="foundation.fibers-of-maps.html" class="Module">foundation.fibers-of-maps</a>
<a id="13319" class="Keyword">open</a> <a id="13324" class="Keyword">import</a> <a id="13331" href="foundation.function-extensionality.html" class="Module">foundation.function-extensionality</a>
<a id="13366" class="Keyword">open</a> <a id="13371" class="Keyword">import</a> <a id="13378" href="foundation.functions.html" class="Module">foundation.functions</a>
<a id="13399" class="Keyword">open</a> <a id="13404" class="Keyword">import</a> <a id="13411" href="foundation.functoriality-cartesian-product-types.html" class="Module">foundation.functoriality-cartesian-product-types</a>
<a id="13460" class="Keyword">open</a> <a id="13465" class="Keyword">import</a> <a id="13472" href="foundation.functoriality-coproduct-types.html" class="Module">foundation.functoriality-coproduct-types</a>
<a id="13513" class="Keyword">open</a> <a id="13518" class="Keyword">import</a> <a id="13525" href="foundation.functoriality-dependent-function-types.html" class="Module">foundation.functoriality-dependent-function-types</a>
<a id="13575" class="Keyword">open</a> <a id="13580" class="Keyword">import</a> <a id="13587" href="foundation.functoriality-dependent-pair-types.html" class="Module">foundation.functoriality-dependent-pair-types</a>
<a id="13633" class="Keyword">open</a> <a id="13638" class="Keyword">import</a> <a id="13645" href="foundation.functoriality-function-types.html" class="Module">foundation.functoriality-function-types</a>
<a id="13685" class="Keyword">open</a> <a id="13690" class="Keyword">import</a> <a id="13697" href="foundation.functoriality-propositional-truncation.html" class="Module">foundation.functoriality-propositional-truncation</a>
<a id="13747" class="Keyword">open</a> <a id="13752" class="Keyword">import</a> <a id="13759" href="foundation.functoriality-set-quotients.html" class="Module">foundation.functoriality-set-quotients</a>
<a id="13798" class="Keyword">open</a> <a id="13803" class="Keyword">import</a> <a id="13810" href="foundation.functoriality-set-truncation.html" class="Module">foundation.functoriality-set-truncation</a>
<a id="13850" class="Keyword">open</a> <a id="13855" class="Keyword">import</a> <a id="13862" href="foundation.functoriality-w-types.html" class="Module">foundation.functoriality-w-types</a>
<a id="13895" class="Keyword">open</a> <a id="13900" class="Keyword">import</a> <a id="13907" href="foundation.fundamental-theorem-of-identity-types.html" class="Module">foundation.fundamental-theorem-of-identity-types</a>
<a id="13956" class="Keyword">open</a> <a id="13961" class="Keyword">import</a> <a id="13968" href="foundation.global-choice.html" class="Module">foundation.global-choice</a>
<a id="13993" class="Keyword">open</a> <a id="13998" class="Keyword">import</a> <a id="14005" href="foundation.hilberts-epsilon-operators.html" class="Module">foundation.hilberts-epsilon-operators</a>
<a id="14043" class="Keyword">open</a> <a id="14048" class="Keyword">import</a> <a id="14055" href="foundation.homotopies.html" class="Module">foundation.homotopies</a>
<a id="14077" class="Keyword">open</a> <a id="14082" class="Keyword">import</a> <a id="14089" href="foundation.identity-systems.html" class="Module">foundation.identity-systems</a>
<a id="14117" class="Keyword">open</a> <a id="14122" class="Keyword">import</a> <a id="14129" href="foundation.identity-types.html" class="Module">foundation.identity-types</a>
<a id="14155" class="Keyword">open</a> <a id="14160" class="Keyword">import</a> <a id="14167" href="foundation.images.html" class="Module">foundation.images</a>
<a id="14185" class="Keyword">open</a> <a id="14190" class="Keyword">import</a> <a id="14197" href="foundation.impredicative-encodings.html" class="Module">foundation.impredicative-encodings</a>
<a id="14232" class="Keyword">open</a> <a id="14237" class="Keyword">import</a> <a id="14244" href="foundation.indexed-w-types.html" class="Module">foundation.indexed-w-types</a>
<a id="14271" class="Keyword">open</a> <a id="14276" class="Keyword">import</a> <a id="14283" href="foundation.induction-principle-propositional-truncation.html" class="Module">foundation.induction-principle-propositional-truncation</a>
<a id="14339" class="Keyword">open</a> <a id="14344" class="Keyword">import</a> <a id="14351" href="foundation.induction-w-types.html" class="Module">foundation.induction-w-types</a>
<a id="14380" class="Keyword">open</a> <a id="14385" class="Keyword">import</a> <a id="14392" href="foundation.inequality-w-types.html" class="Module">foundation.inequality-w-types</a>
<a id="14422" class="Keyword">open</a> <a id="14427" class="Keyword">import</a> <a id="14434" href="foundation.injective-maps.html" class="Module">foundation.injective-maps</a>
<a id="14460" class="Keyword">open</a> <a id="14465" class="Keyword">import</a> <a id="14472" href="foundation.interchange-law.html" class="Module">foundation.interchange-law</a>
<a id="14499" class="Keyword">open</a> <a id="14504" class="Keyword">import</a> <a id="14511" href="foundation.intersection.html" class="Module">foundation.intersection</a>
<a id="14535" class="Keyword">open</a> <a id="14540" class="Keyword">import</a> <a id="14547" href="foundation.involutions.html" class="Module">foundation.involutions</a>
<a id="14570" class="Keyword">open</a> <a id="14575" class="Keyword">import</a> <a id="14582" href="foundation.isolated-points.html" class="Module">foundation.isolated-points</a>
<a id="14609" class="Keyword">open</a> <a id="14614" class="Keyword">import</a> <a id="14621" href="foundation.isomorphisms-of-sets.html" class="Module">foundation.isomorphisms-of-sets</a>
<a id="14653" class="Keyword">open</a> <a id="14658" class="Keyword">import</a> <a id="14665" href="foundation.law-of-excluded-middle.html" class="Module">foundation.law-of-excluded-middle</a>
<a id="14699" class="Keyword">open</a> <a id="14704" class="Keyword">import</a> <a id="14711" href="foundation.lawveres-fixed-point-theorem.html" class="Module">foundation.lawveres-fixed-point-theorem</a>
<a id="14751" class="Keyword">open</a> <a id="14756" class="Keyword">import</a> <a id="14763" href="foundation.locally-small-types.html" class="Module">foundation.locally-small-types</a>
<a id="14794" class="Keyword">open</a> <a id="14799" class="Keyword">import</a> <a id="14806" href="foundation.logical-equivalences.html" class="Module">foundation.logical-equivalences</a>
<a id="14838" class="Keyword">open</a> <a id="14843" class="Keyword">import</a> <a id="14850" href="foundation.lower-types-w-types.html" class="Module">foundation.lower-types-w-types</a>
<a id="14881" class="Keyword">open</a> <a id="14886" class="Keyword">import</a> <a id="14893" href="foundation.maybe.html" class="Module">foundation.maybe</a>
<a id="14910" class="Keyword">open</a> <a id="14915" class="Keyword">import</a> <a id="14922" href="foundation.mere-equality.html" class="Module">foundation.mere-equality</a>
<a id="14947" class="Keyword">open</a> <a id="14952" class="Keyword">import</a> <a id="14959" href="foundation.mere-equivalences.html" class="Module">foundation.mere-equivalences</a>
<a id="14988" class="Keyword">open</a> <a id="14993" class="Keyword">import</a> <a id="15000" href="foundation.monomorphisms.html" class="Module">foundation.monomorphisms</a>
<a id="15025" class="Keyword">open</a> <a id="15030" class="Keyword">import</a> <a id="15037" href="foundation.multisets.html" class="Module">foundation.multisets</a>
<a id="15058" class="Keyword">open</a> <a id="15063" class="Keyword">import</a> <a id="15070" href="foundation.multisubsets.html" class="Module">foundation.multisubsets</a>
<a id="15094" class="Keyword">open</a> <a id="15099" class="Keyword">import</a> <a id="15106" href="foundation.negation.html" class="Module">foundation.negation</a>
<a id="15126" class="Keyword">open</a> <a id="15131" class="Keyword">import</a> <a id="15138" href="foundation.non-contractible-types.html" class="Module">foundation.non-contractible-types</a>
<a id="15172" class="Keyword">open</a> <a id="15177" class="Keyword">import</a> <a id="15184" href="foundation.pairs-of-distinct-elements.html" class="Module">foundation.pairs-of-distinct-elements</a>
<a id="15222" class="Keyword">open</a> <a id="15227" class="Keyword">import</a> <a id="15234" href="foundation.path-algebra.html" class="Module">foundation.path-algebra</a>
<a id="15258" class="Keyword">open</a> <a id="15263" class="Keyword">import</a> <a id="15270" href="foundation.path-split-maps.html" class="Module">foundation.path-split-maps</a>
<a id="15297" class="Keyword">open</a> <a id="15302" class="Keyword">import</a> <a id="15309" href="foundation.polynomial-endofunctors.html" class="Module">foundation.polynomial-endofunctors</a>
<a id="15344" class="Keyword">open</a> <a id="15349" class="Keyword">import</a> <a id="15356" href="foundation.powersets.html" class="Module">foundation.powersets</a>
<a id="15377" class="Keyword">open</a> <a id="15382" class="Keyword">import</a> <a id="15389" href="foundation.principle-of-omniscience.html" class="Module">foundation.principle-of-omniscience</a>
<a id="15425" class="Keyword">open</a> <a id="15430" class="Keyword">import</a> <a id="15437" href="foundation.propositional-extensionality.html" class="Module">foundation.propositional-extensionality</a>
<a id="15477" class="Keyword">open</a> <a id="15482" class="Keyword">import</a> <a id="15489" href="foundation.propositional-maps.html" class="Module">foundation.propositional-maps</a>
<a id="15519" class="Keyword">open</a> <a id="15524" class="Keyword">import</a> <a id="15531" href="foundation.propositional-truncations.html" class="Module">foundation.propositional-truncations</a>
<a id="15568" class="Keyword">open</a> <a id="15573" class="Keyword">import</a> <a id="15580" href="foundation.propositions.html" class="Module">foundation.propositions</a>
<a id="15604" class="Keyword">open</a> <a id="15609" class="Keyword">import</a> <a id="15616" href="foundation.pullbacks.html" class="Module">foundation.pullbacks</a>
<a id="15637" class="Keyword">open</a> <a id="15642" class="Keyword">import</a> <a id="15649" href="foundation.raising-universe-levels.html" class="Module">foundation.raising-universe-levels</a>
<a id="15684" class="Keyword">open</a> <a id="15689" class="Keyword">import</a> <a id="15696" href="foundation.ranks-of-elements-w-types.html" class="Module">foundation.ranks-of-elements-w-types</a>
<a id="15733" class="Keyword">open</a> <a id="15738" class="Keyword">import</a> <a id="15745" href="foundation.reflecting-maps-equivalence-relations.html" class="Module">foundation.reflecting-maps-equivalence-relations</a>
<a id="15794" class="Keyword">open</a> <a id="15799" class="Keyword">import</a> <a id="15806" href="foundation.replacement.html" class="Module">foundation.replacement</a>
<a id="15829" class="Keyword">open</a> <a id="15834" class="Keyword">import</a> <a id="15841" href="foundation.retractions.html" class="Module">foundation.retractions</a>
<a id="15864" class="Keyword">open</a> <a id="15869" class="Keyword">import</a> <a id="15876" href="foundation.russells-paradox.html" class="Module">foundation.russells-paradox</a>
<a id="15904" class="Keyword">open</a> <a id="15909" class="Keyword">import</a> <a id="15916" href="foundation.sections.html" class="Module">foundation.sections</a>
<a id="15936" class="Keyword">open</a> <a id="15941" class="Keyword">import</a> <a id="15948" href="foundation.set-presented-types.html" class="Module">foundation.set-presented-types</a>
<a id="15979" class="Keyword">open</a> <a id="15984" class="Keyword">import</a> <a id="15991" href="foundation.set-truncations.html" class="Module">foundation.set-truncations</a>
<a id="16018" class="Keyword">open</a> <a id="16023" class="Keyword">import</a> <a id="16030" href="foundation.sets.html" class="Module">foundation.sets</a>
<a id="16046" class="Keyword">open</a> <a id="16051" class="Keyword">import</a> <a id="16058" href="foundation.singleton-induction.html" class="Module">foundation.singleton-induction</a>
<a id="16089" class="Keyword">open</a> <a id="16094" class="Keyword">import</a> <a id="16101" href="foundation.slice.html" class="Module">foundation.slice</a>
<a id="16118" class="Keyword">open</a> <a id="16123" class="Keyword">import</a> <a id="16130" href="foundation.small-maps.html" class="Module">foundation.small-maps</a>
<a id="16152" class="Keyword">open</a> <a id="16157" class="Keyword">import</a> <a id="16164" href="foundation.small-multisets.html" class="Module">foundation.small-multisets</a>
<a id="16191" class="Keyword">open</a> <a id="16196" class="Keyword">import</a> <a id="16203" href="foundation.small-types.html" class="Module">foundation.small-types</a>
<a id="16226" class="Keyword">open</a> <a id="16231" class="Keyword">import</a> <a id="16238" href="foundation.small-universes.html" class="Module">foundation.small-universes</a>
<a id="16265" class="Keyword">open</a> <a id="16270" class="Keyword">import</a> <a id="16277" href="foundation.split-surjective-maps.html" class="Module">foundation.split-surjective-maps</a>
<a id="16310" class="Keyword">open</a> <a id="16315" class="Keyword">import</a> <a id="16322" href="foundation.structure-identity-principle.html" class="Module">foundation.structure-identity-principle</a>
<a id="16362" class="Keyword">open</a> <a id="16367" class="Keyword">import</a> <a id="16374" href="foundation.structure.html" class="Module">foundation.structure</a>
<a id="16395" class="Keyword">open</a> <a id="16400" class="Keyword">import</a> <a id="16407" href="foundation.subterminal-types.html" class="Module">foundation.subterminal-types</a>
<a id="16436" class="Keyword">open</a> <a id="16441" class="Keyword">import</a> <a id="16448" href="foundation.subtype-identity-principle.html" class="Module">foundation.subtype-identity-principle</a>
<a id="16486" class="Keyword">open</a> <a id="16491" class="Keyword">import</a> <a id="16498" href="foundation.subtypes.html" class="Module">foundation.subtypes</a>
<a id="16518" class="Keyword">open</a> <a id="16523" class="Keyword">import</a> <a id="16530" href="foundation.subuniverses.html" class="Module">foundation.subuniverses</a>
<a id="16554" class="Keyword">open</a> <a id="16559" class="Keyword">import</a> <a id="16566" href="foundation.surjective-maps.html" class="Module">foundation.surjective-maps</a>
<a id="16593" class="Keyword">open</a> <a id="16598" class="Keyword">import</a> <a id="16605" href="foundation.symmetric-difference.html" class="Module">foundation.symmetric-difference</a>
<a id="16637" class="Keyword">open</a> <a id="16642" class="Keyword">import</a> <a id="16649" href="foundation.truncated-equality.html" class="Module">foundation.truncated-equality</a>
<a id="16679" class="Keyword">open</a> <a id="16684" class="Keyword">import</a> <a id="16691" href="foundation.truncated-maps.html" class="Module">foundation.truncated-maps</a>
<a id="16717" class="Keyword">open</a> <a id="16722" class="Keyword">import</a> <a id="16729" href="foundation.truncated-types.html" class="Module">foundation.truncated-types</a>
<a id="16756" class="Keyword">open</a> <a id="16761" class="Keyword">import</a> <a id="16768" href="foundation.truncation-levels.html" class="Module">foundation.truncation-levels</a>
<a id="16797" class="Keyword">open</a> <a id="16802" class="Keyword">import</a> <a id="16809" href="foundation.truncations.html" class="Module">foundation.truncations</a>
<a id="16832" class="Keyword">open</a> <a id="16837" class="Keyword">import</a> <a id="16844" href="foundation.type-arithmetic-cartesian-product-types.html" class="Module">foundation.type-arithmetic-cartesian-product-types</a>
<a id="16895" class="Keyword">open</a> <a id="16900" class="Keyword">import</a> <a id="16907" href="foundation.type-arithmetic-coproduct-types.html" class="Module">foundation.type-arithmetic-coproduct-types</a>
<a id="16950" class="Keyword">open</a> <a id="16955" class="Keyword">import</a> <a id="16962" href="foundation.type-arithmetic-dependent-pair-types.html" class="Module">foundation.type-arithmetic-dependent-pair-types</a>
<a id="17010" class="Keyword">open</a> <a id="17015" class="Keyword">import</a> <a id="17022" href="foundation.type-arithmetic-empty-type.html" class="Module">foundation.type-arithmetic-empty-type</a>
<a id="17060" class="Keyword">open</a> <a id="17065" class="Keyword">import</a> <a id="17072" href="foundation.type-arithmetic-unit-type.html" class="Module">foundation.type-arithmetic-unit-type</a>
<a id="17109" class="Keyword">open</a> <a id="17114" class="Keyword">import</a> <a id="17121" href="foundation.union.html" class="Module">foundation.union</a>
<a id="17138" class="Keyword">open</a> <a id="17143" class="Keyword">import</a> <a id="17150" href="foundation.uniqueness-image.html" class="Module">foundation.uniqueness-image</a>
<a id="17178" class="Keyword">open</a> <a id="17183" class="Keyword">import</a> <a id="17190" href="foundation.uniqueness-set-quotients.html" class="Module">foundation.uniqueness-set-quotients</a>
<a id="17226" class="Keyword">open</a> <a id="17231" class="Keyword">import</a> <a id="17238" href="foundation.uniqueness-set-truncations.html" class="Module">foundation.uniqueness-set-truncations</a>
<a id="17276" class="Keyword">open</a> <a id="17281" class="Keyword">import</a> <a id="17288" href="foundation.uniqueness-truncation.html" class="Module">foundation.uniqueness-truncation</a>
<a id="17321" class="Keyword">open</a> <a id="17326" class="Keyword">import</a> <a id="17333" href="foundation.unit-type.html" class="Module">foundation.unit-type</a>
<a id="17354" class="Keyword">open</a> <a id="17359" class="Keyword">import</a> <a id="17366" href="foundation.univalence-implies-function-extensionality.html" class="Module">foundation.univalence-implies-function-extensionality</a>
<a id="17420" class="Keyword">open</a> <a id="17425" class="Keyword">import</a> <a id="17432" href="foundation.univalence.html" class="Module">foundation.univalence</a>
<a id="17454" class="Keyword">open</a> <a id="17459" class="Keyword">import</a> <a id="17466" href="foundation.univalent-type-families.html" class="Module">foundation.univalent-type-families</a>
<a id="17501" class="Keyword">open</a> <a id="17506" class="Keyword">import</a> <a id="17513" href="foundation.universal-multiset.html" class="Module">foundation.universal-multiset</a>
<a id="17543" class="Keyword">open</a> <a id="17548" class="Keyword">import</a> <a id="17555" href="foundation.universal-property-booleans.html" class="Module">foundation.universal-property-booleans</a>
<a id="17594" class="Keyword">open</a> <a id="17599" class="Keyword">import</a> <a id="17606" href="foundation.universal-property-cartesian-product-types.html" class="Module">foundation.universal-property-cartesian-product-types</a>
<a id="17660" class="Keyword">open</a> <a id="17665" class="Keyword">import</a> <a id="17672" href="foundation.universal-property-coproduct-types.html" class="Module">foundation.universal-property-coproduct-types</a>
<a id="17718" class="Keyword">open</a> <a id="17723" class="Keyword">import</a> <a id="17730" href="foundation.universal-property-dependent-pair-types.html" class="Module">foundation.universal-property-dependent-pair-types</a>
<a id="17781" class="Keyword">open</a> <a id="17786" class="Keyword">import</a> <a id="17793" href="foundation.universal-property-empty-type.html" class="Module">foundation.universal-property-empty-type</a>
<a id="17834" class="Keyword">open</a> <a id="17839" class="Keyword">import</a> <a id="17846" href="foundation.universal-property-fiber-products.html" class="Module">foundation.universal-property-fiber-products</a>
<a id="17891" class="Keyword">open</a> <a id="17896" class="Keyword">import</a> <a id="17903" href="foundation.universal-property-identity-types.html" class="Module">foundation.universal-property-identity-types</a>
<a id="17948" class="Keyword">open</a> <a id="17953" class="Keyword">import</a> <a id="17960" href="foundation.universal-property-image.html" class="Module">foundation.universal-property-image</a>
<a id="17996" class="Keyword">open</a> <a id="18001" class="Keyword">import</a> <a id="18008" href="foundation.universal-property-maybe.html" class="Module">foundation.universal-property-maybe</a>
<a id="18044" class="Keyword">open</a> <a id="18049" class="Keyword">import</a> <a id="18056" href="foundation.universal-property-propositional-truncation-into-sets.html" class="Module">foundation.universal-property-propositional-truncation-into-sets</a>
<a id="18121" class="Keyword">open</a> <a id="18126" class="Keyword">import</a> <a id="18133" href="foundation.universal-property-propositional-truncation.html" class="Module">foundation.universal-property-propositional-truncation</a>
<a id="18188" class="Keyword">open</a> <a id="18193" class="Keyword">import</a> <a id="18200" href="foundation.universal-property-pullbacks.html" class="Module">foundation.universal-property-pullbacks</a>
<a id="18240" class="Keyword">open</a> <a id="18245" class="Keyword">import</a> <a id="18252" href="foundation.universal-property-set-quotients.html" class="Module">foundation.universal-property-set-quotients</a>
<a id="18296" class="Keyword">open</a> <a id="18301" class="Keyword">import</a> <a id="18308" href="foundation.universal-property-set-truncation.html" class="Module">foundation.universal-property-set-truncation</a>
<a id="18353" class="Keyword">open</a> <a id="18358" class="Keyword">import</a> <a id="18365" href="foundation.universal-property-truncation.html" class="Module">foundation.universal-property-truncation</a>
<a id="18406" class="Keyword">open</a> <a id="18411" class="Keyword">import</a> <a id="18418" href="foundation.universal-property-unit-type.html" class="Module">foundation.universal-property-unit-type</a>
<a id="18458" class="Keyword">open</a> <a id="18463" class="Keyword">import</a> <a id="18470" href="foundation.universe-levels.html" class="Module">foundation.universe-levels</a>
<a id="18497" class="Keyword">open</a> <a id="18502" class="Keyword">import</a> <a id="18509" href="foundation.unordered-pairs.html" class="Module">foundation.unordered-pairs</a>
<a id="18536" class="Keyword">open</a> <a id="18541" class="Keyword">import</a> <a id="18548" href="foundation.w-types.html" class="Module">foundation.w-types</a>
<a id="18567" class="Keyword">open</a> <a id="18572" class="Keyword">import</a> <a id="18579" href="foundation.weak-function-extensionality.html" class="Module">foundation.weak-function-extensionality</a>
<a id="18619" class="Keyword">open</a> <a id="18624" class="Keyword">import</a> <a id="18631" href="foundation.weakly-constant-maps.html" class="Module">foundation.weakly-constant-maps</a>
<a id="18663" class="Keyword">open</a> <a id="18668" class="Keyword">import</a> <a id="18675" href="foundation.xor.html" class="Module">foundation.xor</a>
</pre>
## Foundation Core

<pre class="Agda"><a id="18723" class="Keyword">open</a> <a id="18728" class="Keyword">import</a> <a id="18735" href="foundation-core.0-maps.html" class="Module">foundation-core.0-maps</a>
<a id="18758" class="Keyword">open</a> <a id="18763" class="Keyword">import</a> <a id="18770" href="foundation-core.1-types.html" class="Module">foundation-core.1-types</a>
<a id="18794" class="Keyword">open</a> <a id="18799" class="Keyword">import</a> <a id="18806" href="foundation-core.cartesian-product-types.html" class="Module">foundation-core.cartesian-product-types</a>
<a id="18846" class="Keyword">open</a> <a id="18851" class="Keyword">import</a> <a id="18858" href="foundation-core.coherently-invertible-maps.html" class="Module">foundation-core.coherently-invertible-maps</a>
<a id="18901" class="Keyword">open</a> <a id="18906" class="Keyword">import</a> <a id="18913" href="foundation-core.commuting-squares.html" class="Module">foundation-core.commuting-squares</a>
<a id="18947" class="Keyword">open</a> <a id="18952" class="Keyword">import</a> <a id="18959" href="foundation-core.constant-maps.html" class="Module">foundation-core.constant-maps</a>
<a id="18989" class="Keyword">open</a> <a id="18994" class="Keyword">import</a> <a id="19001" href="foundation-core.contractible-maps.html" class="Module">foundation-core.contractible-maps</a>
<a id="19035" class="Keyword">open</a> <a id="19040" class="Keyword">import</a> <a id="19047" href="foundation-core.contractible-types.html" class="Module">foundation-core.contractible-types</a>
<a id="19082" class="Keyword">open</a> <a id="19087" class="Keyword">import</a> <a id="19094" href="foundation-core.dependent-pair-types.html" class="Module">foundation-core.dependent-pair-types</a>
<a id="19131" class="Keyword">open</a> <a id="19136" class="Keyword">import</a> <a id="19143" href="foundation-core.embeddings.html" class="Module">foundation-core.embeddings</a>
<a id="19170" class="Keyword">open</a> <a id="19175" class="Keyword">import</a> <a id="19182" href="foundation-core.empty-types.html" class="Module">foundation-core.empty-types</a>
<a id="19210" class="Keyword">open</a> <a id="19215" class="Keyword">import</a> <a id="19222" href="foundation-core.equality-cartesian-product-types.html" class="Module">foundation-core.equality-cartesian-product-types</a>
<a id="19271" class="Keyword">open</a> <a id="19276" class="Keyword">import</a> <a id="19283" href="foundation-core.equality-dependent-pair-types.html" class="Module">foundation-core.equality-dependent-pair-types</a>
<a id="19329" class="Keyword">open</a> <a id="19334" class="Keyword">import</a> <a id="19341" href="foundation-core.equality-fibers-of-maps.html" class="Module">foundation-core.equality-fibers-of-maps</a>
<a id="19381" class="Keyword">open</a> <a id="19386" class="Keyword">import</a> <a id="19393" href="foundation-core.equivalence-induction.html" class="Module">foundation-core.equivalence-induction</a>
<a id="19431" class="Keyword">open</a> <a id="19436" class="Keyword">import</a> <a id="19443" href="foundation-core.equivalences.html" class="Module">foundation-core.equivalences</a>
<a id="19472" class="Keyword">open</a> <a id="19477" class="Keyword">import</a> <a id="19484" href="foundation-core.faithful-maps.html" class="Module">foundation-core.faithful-maps</a>
<a id="19514" class="Keyword">open</a> <a id="19519" class="Keyword">import</a> <a id="19526" href="foundation-core.fibers-of-maps.html" class="Module">foundation-core.fibers-of-maps</a>
<a id="19557" class="Keyword">open</a> <a id="19562" class="Keyword">import</a> <a id="19569" href="foundation-core.functions.html" class="Module">foundation-core.functions</a>
<a id="19595" class="Keyword">open</a> <a id="19600" class="Keyword">import</a> <a id="19607" href="foundation-core.functoriality-dependent-pair-types.html" class="Module">foundation-core.functoriality-dependent-pair-types</a>
<a id="19658" class="Keyword">open</a> <a id="19663" class="Keyword">import</a> <a id="19670" href="foundation-core.fundamental-theorem-of-identity-types.html" class="Module">foundation-core.fundamental-theorem-of-identity-types</a>
<a id="19724" class="Keyword">open</a> <a id="19729" class="Keyword">import</a> <a id="19736" href="foundation-core.homotopies.html" class="Module">foundation-core.homotopies</a>
<a id="19763" class="Keyword">open</a> <a id="19768" class="Keyword">import</a> <a id="19775" href="foundation-core.identity-systems.html" class="Module">foundation-core.identity-systems</a>
<a id="19808" class="Keyword">open</a> <a id="19813" class="Keyword">import</a> <a id="19820" href="foundation-core.identity-types.html" class="Module">foundation-core.identity-types</a>
<a id="19851" class="Keyword">open</a> <a id="19856" class="Keyword">import</a> <a id="19863" href="foundation-core.logical-equivalences.html" class="Module">foundation-core.logical-equivalences</a>
<a id="19900" class="Keyword">open</a> <a id="19905" class="Keyword">import</a> <a id="19912" href="foundation-core.negation.html" class="Module">foundation-core.negation</a>
<a id="19937" class="Keyword">open</a> <a id="19942" class="Keyword">import</a> <a id="19949" href="foundation-core.path-split-maps.html" class="Module">foundation-core.path-split-maps</a>
<a id="19981" class="Keyword">open</a> <a id="19986" class="Keyword">import</a> <a id="19993" href="foundation-core.propositional-maps.html" class="Module">foundation-core.propositional-maps</a>
<a id="20028" class="Keyword">open</a> <a id="20033" class="Keyword">import</a> <a id="20040" href="foundation-core.propositions.html" class="Module">foundation-core.propositions</a>
<a id="20069" class="Keyword">open</a> <a id="20074" class="Keyword">import</a> <a id="20081" href="foundation-core.retractions.html" class="Module">foundation-core.retractions</a>
<a id="20109" class="Keyword">open</a> <a id="20114" class="Keyword">import</a> <a id="20121" href="foundation-core.sections.html" class="Module">foundation-core.sections</a>
<a id="20146" class="Keyword">open</a> <a id="20151" class="Keyword">import</a> <a id="20158" href="foundation-core.sets.html" class="Module">foundation-core.sets</a>
<a id="20179" class="Keyword">open</a> <a id="20184" class="Keyword">import</a> <a id="20191" href="foundation-core.singleton-induction.html" class="Module">foundation-core.singleton-induction</a>
<a id="20227" class="Keyword">open</a> <a id="20232" class="Keyword">import</a> <a id="20239" href="foundation-core.subtype-identity-principle.html" class="Module">foundation-core.subtype-identity-principle</a>
<a id="20282" class="Keyword">open</a> <a id="20287" class="Keyword">import</a> <a id="20294" href="foundation-core.subtypes.html" class="Module">foundation-core.subtypes</a>
<a id="20319" class="Keyword">open</a> <a id="20324" class="Keyword">import</a> <a id="20331" href="foundation-core.truncated-maps.html" class="Module">foundation-core.truncated-maps</a>
<a id="20362" class="Keyword">open</a> <a id="20367" class="Keyword">import</a> <a id="20374" href="foundation-core.truncated-types.html" class="Module">foundation-core.truncated-types</a>
<a id="20406" class="Keyword">open</a> <a id="20411" class="Keyword">import</a> <a id="20418" href="foundation-core.truncation-levels.html" class="Module">foundation-core.truncation-levels</a>
<a id="20452" class="Keyword">open</a> <a id="20457" class="Keyword">import</a> <a id="20464" href="foundation-core.type-arithmetic-cartesian-product-types.html" class="Module">foundation-core.type-arithmetic-cartesian-product-types</a>
<a id="20520" class="Keyword">open</a> <a id="20525" class="Keyword">import</a> <a id="20532" href="foundation-core.type-arithmetic-dependent-pair-types.html" class="Module">foundation-core.type-arithmetic-dependent-pair-types</a>
<a id="20585" class="Keyword">open</a> <a id="20590" class="Keyword">import</a> <a id="20597" href="foundation-core.univalence.html" class="Module">foundation-core.univalence</a>
<a id="20624" class="Keyword">open</a> <a id="20629" class="Keyword">import</a> <a id="20636" href="foundation-core.universe-levels.html" class="Module">foundation-core.universe-levels</a>
</pre>
## Graph theory

<pre class="Agda"><a id="20698" class="Keyword">open</a> <a id="20703" class="Keyword">import</a> <a id="20710" href="graph-theory.html" class="Module">graph-theory</a>
<a id="20723" class="Keyword">open</a> <a id="20728" class="Keyword">import</a> <a id="20735" href="graph-theory.connected-undirected-graphs.html" class="Module">graph-theory.connected-undirected-graphs</a>
<a id="20776" class="Keyword">open</a> <a id="20781" class="Keyword">import</a> <a id="20788" href="graph-theory.directed-graphs.html" class="Module">graph-theory.directed-graphs</a>
<a id="20817" class="Keyword">open</a> <a id="20822" class="Keyword">import</a> <a id="20829" href="graph-theory.edge-coloured-undirected-graphs.html" class="Module">graph-theory.edge-coloured-undirected-graphs</a>
<a id="20874" class="Keyword">open</a> <a id="20879" class="Keyword">import</a> <a id="20886" href="graph-theory.equivalences-undirected-graphs.html" class="Module">graph-theory.equivalences-undirected-graphs</a>
<a id="20930" class="Keyword">open</a> <a id="20935" class="Keyword">import</a> <a id="20942" href="graph-theory.finite-graphs.html" class="Module">graph-theory.finite-graphs</a>
<a id="20969" class="Keyword">open</a> <a id="20974" class="Keyword">import</a> <a id="20981" href="graph-theory.incidence-undirected-graphs.html" class="Module">graph-theory.incidence-undirected-graphs</a>
<a id="21022" class="Keyword">open</a> <a id="21027" class="Keyword">import</a> <a id="21034" href="graph-theory.matchings.html" class="Module">graph-theory.matchings</a>
<a id="21057" class="Keyword">open</a> <a id="21062" class="Keyword">import</a> <a id="21069" href="graph-theory.mere-equivalences-undirected-graphs.html" class="Module">graph-theory.mere-equivalences-undirected-graphs</a>
<a id="21118" class="Keyword">open</a> <a id="21123" class="Keyword">import</a> <a id="21130" href="graph-theory.morphisms-directed-graphs.html" class="Module">graph-theory.morphisms-directed-graphs</a>
<a id="21169" class="Keyword">open</a> <a id="21174" class="Keyword">import</a> <a id="21181" href="graph-theory.morphisms-undirected-graphs.html" class="Module">graph-theory.morphisms-undirected-graphs</a>
<a id="21222" class="Keyword">open</a> <a id="21227" class="Keyword">import</a> <a id="21234" href="graph-theory.orientations-undirected-graphs.html" class="Module">graph-theory.orientations-undirected-graphs</a>
<a id="21278" class="Keyword">open</a> <a id="21283" class="Keyword">import</a> <a id="21290" href="graph-theory.paths-undirected-graphs.html" class="Module">graph-theory.paths-undirected-graphs</a>
<a id="21327" class="Keyword">open</a> <a id="21332" class="Keyword">import</a> <a id="21339" href="graph-theory.polygons.html" class="Module">graph-theory.polygons</a>
<a id="21361" class="Keyword">open</a> <a id="21366" class="Keyword">import</a> <a id="21373" href="graph-theory.reflexive-graphs.html" class="Module">graph-theory.reflexive-graphs</a>
<a id="21403" class="Keyword">open</a> <a id="21408" class="Keyword">import</a> <a id="21415" href="graph-theory.regular-undirected-graphs.html" class="Module">graph-theory.regular-undirected-graphs</a>
<a id="21454" class="Keyword">open</a> <a id="21459" class="Keyword">import</a> <a id="21466" href="graph-theory.simple-undirected-graphs.html" class="Module">graph-theory.simple-undirected-graphs</a>
<a id="21504" class="Keyword">open</a> <a id="21509" class="Keyword">import</a> <a id="21516" href="graph-theory.undirected-graphs.html" class="Module">graph-theory.undirected-graphs</a>
<a id="21547" class="Keyword">open</a> <a id="21552" class="Keyword">import</a> <a id="21559" href="graph-theory.vertex-covers.html" class="Module">graph-theory.vertex-covers</a>
<a id="21586" class="Keyword">open</a> <a id="21591" class="Keyword">import</a> <a id="21598" href="graph-theory.voltage-graphs.html" class="Module">graph-theory.voltage-graphs</a>
</pre>
## Group theory

<pre class="Agda"><a id="21656" class="Keyword">open</a> <a id="21661" class="Keyword">import</a> <a id="21668" href="group-theory.html" class="Module">group-theory</a>
<a id="21681" class="Keyword">open</a> <a id="21686" class="Keyword">import</a> <a id="21693" href="group-theory.abelian-groups.html" class="Module">group-theory.abelian-groups</a>
<a id="21721" class="Keyword">open</a> <a id="21726" class="Keyword">import</a> <a id="21733" href="group-theory.abelian-subgroups.html" class="Module">group-theory.abelian-subgroups</a>
<a id="21764" class="Keyword">open</a> <a id="21769" class="Keyword">import</a> <a id="21776" href="group-theory.abstract-group-torsors.html" class="Module">group-theory.abstract-group-torsors</a>
<a id="21812" class="Keyword">open</a> <a id="21817" class="Keyword">import</a> <a id="21824" href="group-theory.addition-homomorphisms-abelian-groups.html" class="Module">group-theory.addition-homomorphisms-abelian-groups</a>
<a id="21875" class="Keyword">open</a> <a id="21880" class="Keyword">import</a> <a id="21887" href="group-theory.automorphism-groups.html" class="Module">group-theory.automorphism-groups</a>
<a id="21920" class="Keyword">open</a> <a id="21925" class="Keyword">import</a> <a id="21932" href="group-theory.category-of-groups.html" class="Module">group-theory.category-of-groups</a>
<a id="21964" class="Keyword">open</a> <a id="21969" class="Keyword">import</a> <a id="21976" href="group-theory.category-of-semigroups.html" class="Module">group-theory.category-of-semigroups</a>
<a id="22012" class="Keyword">open</a> <a id="22017" class="Keyword">import</a> <a id="22024" href="group-theory.cayleys-theorem.html" class="Module">group-theory.cayleys-theorem</a>
<a id="22053" class="Keyword">open</a> <a id="22058" class="Keyword">import</a> <a id="22065" href="group-theory.concrete-group-actions.html" class="Module">group-theory.concrete-group-actions</a>
<a id="22101" class="Keyword">open</a> <a id="22106" class="Keyword">import</a> <a id="22113" href="group-theory.concrete-groups.html" class="Module">group-theory.concrete-groups</a>
<a id="22142" class="Keyword">open</a> <a id="22147" class="Keyword">import</a> <a id="22154" href="group-theory.concrete-subgroups.html" class="Module">group-theory.concrete-subgroups</a>
<a id="22186" class="Keyword">open</a> <a id="22191" class="Keyword">import</a> <a id="22198" href="group-theory.conjugation.html" class="Module">group-theory.conjugation</a>
<a id="22223" class="Keyword">open</a> <a id="22228" class="Keyword">import</a> <a id="22235" href="group-theory.embeddings-groups.html" class="Module">group-theory.embeddings-groups</a>
<a id="22266" class="Keyword">open</a> <a id="22271" class="Keyword">import</a> <a id="22278" href="group-theory.endomorphism-rings-abelian-groups.html" class="Module">group-theory.endomorphism-rings-abelian-groups</a>
<a id="22325" class="Keyword">open</a> <a id="22330" class="Keyword">import</a> <a id="22337" href="group-theory.epimorphisms-groups.html" class="Module">group-theory.epimorphisms-groups</a>
<a id="22370" class="Keyword">open</a> <a id="22375" class="Keyword">import</a> <a id="22382" href="group-theory.equivalences-group-actions.html" class="Module">group-theory.equivalences-group-actions</a>
<a id="22422" class="Keyword">open</a> <a id="22427" class="Keyword">import</a> <a id="22434" href="group-theory.equivalences-semigroups.html" class="Module">group-theory.equivalences-semigroups</a>
<a id="22471" class="Keyword">open</a> <a id="22476" class="Keyword">import</a> <a id="22483" href="group-theory.examples-higher-groups.html" class="Module">group-theory.examples-higher-groups</a>
<a id="22519" class="Keyword">open</a> <a id="22524" class="Keyword">import</a> <a id="22531" href="group-theory.furstenberg-groups.html" class="Module">group-theory.furstenberg-groups</a>
<a id="22563" class="Keyword">open</a> <a id="22568" class="Keyword">import</a> <a id="22575" href="group-theory.group-actions.html" class="Module">group-theory.group-actions</a>
<a id="22602" class="Keyword">open</a> <a id="22607" class="Keyword">import</a> <a id="22614" href="group-theory.groups.html" class="Module">group-theory.groups</a>
<a id="22634" class="Keyword">open</a> <a id="22639" class="Keyword">import</a> <a id="22646" href="group-theory.higher-groups.html" class="Module">group-theory.higher-groups</a>
<a id="22673" class="Keyword">open</a> <a id="22678" class="Keyword">import</a> <a id="22685" href="group-theory.homomorphisms-abelian-groups.html" class="Module">group-theory.homomorphisms-abelian-groups</a>
<a id="22727" class="Keyword">open</a> <a id="22732" class="Keyword">import</a> <a id="22739" href="group-theory.homomorphisms-generated-subgroups.html" class="Module">group-theory.homomorphisms-generated-subgroups</a>
<a id="22786" class="Keyword">open</a> <a id="22791" class="Keyword">import</a> <a id="22798" href="group-theory.homomorphisms-group-actions.html" class="Module">group-theory.homomorphisms-group-actions</a>
<a id="22839" class="Keyword">open</a> <a id="22844" class="Keyword">import</a> <a id="22851" href="group-theory.homomorphisms-groups.html" class="Module">group-theory.homomorphisms-groups</a>
<a id="22885" class="Keyword">open</a> <a id="22890" class="Keyword">import</a> <a id="22897" href="group-theory.homomorphisms-monoids.html" class="Module">group-theory.homomorphisms-monoids</a>
<a id="22932" class="Keyword">open</a> <a id="22937" class="Keyword">import</a> <a id="22944" href="group-theory.homomorphisms-semigroups.html" class="Module">group-theory.homomorphisms-semigroups</a>
<a id="22982" class="Keyword">open</a> <a id="22987" class="Keyword">import</a> <a id="22994" href="group-theory.inverse-semigroups.html" class="Module">group-theory.inverse-semigroups</a>
<a id="23026" class="Keyword">open</a> <a id="23031" class="Keyword">import</a> <a id="23038" href="group-theory.invertible-elements-monoids.html" class="Module">group-theory.invertible-elements-monoids</a>
<a id="23079" class="Keyword">open</a> <a id="23084" class="Keyword">import</a> <a id="23091" href="group-theory.isomorphisms-abelian-groups.html" class="Module">group-theory.isomorphisms-abelian-groups</a>
<a id="23132" class="Keyword">open</a> <a id="23137" class="Keyword">import</a> <a id="23144" href="group-theory.isomorphisms-group-actions.html" class="Module">group-theory.isomorphisms-group-actions</a>
<a id="23184" class="Keyword">open</a> <a id="23189" class="Keyword">import</a> <a id="23196" href="group-theory.isomorphisms-groups.html" class="Module">group-theory.isomorphisms-groups</a>
<a id="23229" class="Keyword">open</a> <a id="23234" class="Keyword">import</a> <a id="23241" href="group-theory.isomorphisms-semigroups.html" class="Module">group-theory.isomorphisms-semigroups</a>
<a id="23278" class="Keyword">open</a> <a id="23283" class="Keyword">import</a> <a id="23290" href="group-theory.mere-equivalences-group-actions.html" class="Module">group-theory.mere-equivalences-group-actions</a>
<a id="23335" class="Keyword">open</a> <a id="23340" class="Keyword">import</a> <a id="23347" href="group-theory.monoids.html" class="Module">group-theory.monoids</a>
<a id="23368" class="Keyword">open</a> <a id="23373" class="Keyword">import</a> <a id="23380" href="group-theory.monomorphisms-groups.html" class="Module">group-theory.monomorphisms-groups</a>
<a id="23414" class="Keyword">open</a> <a id="23419" class="Keyword">import</a> <a id="23426" href="group-theory.orbits-group-actions.html" class="Module">group-theory.orbits-group-actions</a>
<a id="23460" class="Keyword">open</a> <a id="23465" class="Keyword">import</a> <a id="23472" href="group-theory.precategory-of-group-actions.html" class="Module">group-theory.precategory-of-group-actions</a>
<a id="23514" class="Keyword">open</a> <a id="23519" class="Keyword">import</a> <a id="23526" href="group-theory.precategory-of-groups.html" class="Module">group-theory.precategory-of-groups</a>
<a id="23561" class="Keyword">open</a> <a id="23566" class="Keyword">import</a> <a id="23573" href="group-theory.precategory-of-semigroups.html" class="Module">group-theory.precategory-of-semigroups</a>
<a id="23612" class="Keyword">open</a> <a id="23617" class="Keyword">import</a> <a id="23624" href="group-theory.principal-group-actions.html" class="Module">group-theory.principal-group-actions</a>
<a id="23661" class="Keyword">open</a> <a id="23666" class="Keyword">import</a> <a id="23673" href="group-theory.semigroups.html" class="Module">group-theory.semigroups</a>
<a id="23697" class="Keyword">open</a> <a id="23702" class="Keyword">import</a> <a id="23709" href="group-theory.sheargroups.html" class="Module">group-theory.sheargroups</a>
<a id="23734" class="Keyword">open</a> <a id="23739" class="Keyword">import</a> <a id="23746" href="group-theory.stabilizer-groups.html" class="Module">group-theory.stabilizer-groups</a>
<a id="23777" class="Keyword">open</a> <a id="23782" class="Keyword">import</a> <a id="23789" href="group-theory.subgroups-generated-by-subsets-groups.html" class="Module">group-theory.subgroups-generated-by-subsets-groups</a>
<a id="23840" class="Keyword">open</a> <a id="23845" class="Keyword">import</a> <a id="23852" href="group-theory.subgroups.html" class="Module">group-theory.subgroups</a>
<a id="23875" class="Keyword">open</a> <a id="23880" class="Keyword">import</a> <a id="23887" href="group-theory.substitution-functor-group-actions.html" class="Module">group-theory.substitution-functor-group-actions</a>
<a id="23935" class="Keyword">open</a> <a id="23940" class="Keyword">import</a> <a id="23947" href="group-theory.symmetric-groups.html" class="Module">group-theory.symmetric-groups</a>
<a id="23977" class="Keyword">open</a> <a id="23982" class="Keyword">import</a> <a id="23989" href="group-theory.transitive-group-actions.html" class="Module">group-theory.transitive-group-actions</a>
</pre>
## Linear algebra

<pre class="Agda"><a id="24059" class="Keyword">open</a> <a id="24064" class="Keyword">import</a> <a id="24071" href="linear-algebra.html" class="Module">linear-algebra</a>
<a id="24086" class="Keyword">open</a> <a id="24091" class="Keyword">import</a> <a id="24098" href="linear-algebra.constant-matrices.html" class="Module">linear-algebra.constant-matrices</a>
<a id="24131" class="Keyword">open</a> <a id="24136" class="Keyword">import</a> <a id="24143" href="linear-algebra.constant-vectors.html" class="Module">linear-algebra.constant-vectors</a>
<a id="24175" class="Keyword">open</a> <a id="24180" class="Keyword">import</a> <a id="24187" href="linear-algebra.diagonal-matrices-on-rings.html" class="Module">linear-algebra.diagonal-matrices-on-rings</a>
<a id="24229" class="Keyword">open</a> <a id="24234" class="Keyword">import</a> <a id="24241" href="linear-algebra.functoriality-matrices.html" class="Module">linear-algebra.functoriality-matrices</a>
<a id="24279" class="Keyword">open</a> <a id="24284" class="Keyword">import</a> <a id="24291" href="linear-algebra.functoriality-vectors.html" class="Module">linear-algebra.functoriality-vectors</a>
<a id="24328" class="Keyword">open</a> <a id="24333" class="Keyword">import</a> <a id="24340" href="linear-algebra.matrices-on-rings.html" class="Module">linear-algebra.matrices-on-rings</a>
<a id="24373" class="Keyword">open</a> <a id="24378" class="Keyword">import</a> <a id="24385" href="linear-algebra.matrices.html" class="Module">linear-algebra.matrices</a>
<a id="24409" class="Keyword">open</a> <a id="24414" class="Keyword">import</a> <a id="24421" href="linear-algebra.multiplication-matrices.html" class="Module">linear-algebra.multiplication-matrices</a>
<a id="24460" class="Keyword">open</a> <a id="24465" class="Keyword">import</a> <a id="24472" href="linear-algebra.scalar-multiplication-matrices.html" class="Module">linear-algebra.scalar-multiplication-matrices</a>
<a id="24518" class="Keyword">open</a> <a id="24523" class="Keyword">import</a> <a id="24530" href="linear-algebra.scalar-multiplication-vectors.html" class="Module">linear-algebra.scalar-multiplication-vectors</a>
<a id="24575" class="Keyword">open</a> <a id="24580" class="Keyword">import</a> <a id="24587" href="linear-algebra.transposition-matrices.html" class="Module">linear-algebra.transposition-matrices</a>
<a id="24625" class="Keyword">open</a> <a id="24630" class="Keyword">import</a> <a id="24637" href="linear-algebra.vectors-on-rings.html" class="Module">linear-algebra.vectors-on-rings</a>
<a id="24669" class="Keyword">open</a> <a id="24674" class="Keyword">import</a> <a id="24681" href="linear-algebra.vectors.html" class="Module">linear-algebra.vectors</a>
</pre>
## Order theory

<pre class="Agda"><a id="24734" class="Keyword">open</a> <a id="24739" class="Keyword">import</a> <a id="24746" href="order-theory.html" class="Module">order-theory</a>
<a id="24759" class="Keyword">open</a> <a id="24764" class="Keyword">import</a> <a id="24771" href="order-theory.chains-posets.html" class="Module">order-theory.chains-posets</a>
<a id="24798" class="Keyword">open</a> <a id="24803" class="Keyword">import</a> <a id="24810" href="order-theory.chains-preorders.html" class="Module">order-theory.chains-preorders</a>
<a id="24840" class="Keyword">open</a> <a id="24845" class="Keyword">import</a> <a id="24852" href="order-theory.decidable-subposets.html" class="Module">order-theory.decidable-subposets</a>
<a id="24885" class="Keyword">open</a> <a id="24890" class="Keyword">import</a> <a id="24897" href="order-theory.decidable-subpreorders.html" class="Module">order-theory.decidable-subpreorders</a>
<a id="24933" class="Keyword">open</a> <a id="24938" class="Keyword">import</a> <a id="24945" href="order-theory.finite-posets.html" class="Module">order-theory.finite-posets</a>
<a id="24972" class="Keyword">open</a> <a id="24977" class="Keyword">import</a> <a id="24984" href="order-theory.finite-preorders.html" class="Module">order-theory.finite-preorders</a>
<a id="25014" class="Keyword">open</a> <a id="25019" class="Keyword">import</a> <a id="25026" href="order-theory.finitely-graded-posets.html" class="Module">order-theory.finitely-graded-posets</a>
<a id="25062" class="Keyword">open</a> <a id="25067" class="Keyword">import</a> <a id="25074" href="order-theory.greatest-lower-bounds-posets.html" class="Module">order-theory.greatest-lower-bounds-posets</a>
<a id="25116" class="Keyword">open</a> <a id="25121" class="Keyword">import</a> <a id="25128" href="order-theory.interval-subposets.html" class="Module">order-theory.interval-subposets</a>
<a id="25160" class="Keyword">open</a> <a id="25165" class="Keyword">import</a> <a id="25172" href="order-theory.join-semilattices.html" class="Module">order-theory.join-semilattices</a>
<a id="25203" class="Keyword">open</a> <a id="25208" class="Keyword">import</a> <a id="25215" href="order-theory.large-posets.html" class="Module">order-theory.large-posets</a>
<a id="25241" class="Keyword">open</a> <a id="25246" class="Keyword">import</a> <a id="25253" href="order-theory.large-preorders.html" class="Module">order-theory.large-preorders</a>
<a id="25282" class="Keyword">open</a> <a id="25287" class="Keyword">import</a> <a id="25294" href="order-theory.largest-elements-posets.html" class="Module">order-theory.largest-elements-posets</a>
<a id="25331" class="Keyword">open</a> <a id="25336" class="Keyword">import</a> <a id="25343" href="order-theory.largest-elements-preorders.html" class="Module">order-theory.largest-elements-preorders</a>
<a id="25383" class="Keyword">open</a> <a id="25388" class="Keyword">import</a> <a id="25395" href="order-theory.least-elements-posets.html" class="Module">order-theory.least-elements-posets</a>
<a id="25430" class="Keyword">open</a> <a id="25435" class="Keyword">import</a> <a id="25442" href="order-theory.least-elements-preorders.html" class="Module">order-theory.least-elements-preorders</a>
<a id="25480" class="Keyword">open</a> <a id="25485" class="Keyword">import</a> <a id="25492" href="order-theory.least-upper-bounds-posets.html" class="Module">order-theory.least-upper-bounds-posets</a>
<a id="25531" class="Keyword">open</a> <a id="25536" class="Keyword">import</a> <a id="25543" href="order-theory.locally-finite-posets.html" class="Module">order-theory.locally-finite-posets</a>
<a id="25578" class="Keyword">open</a> <a id="25583" class="Keyword">import</a> <a id="25590" href="order-theory.maximal-chains-posets.html" class="Module">order-theory.maximal-chains-posets</a>
<a id="25625" class="Keyword">open</a> <a id="25630" class="Keyword">import</a> <a id="25637" href="order-theory.maximal-chains-preorders.html" class="Module">order-theory.maximal-chains-preorders</a>
<a id="25675" class="Keyword">open</a> <a id="25680" class="Keyword">import</a> <a id="25687" href="order-theory.meet-semilattices.html" class="Module">order-theory.meet-semilattices</a>
<a id="25718" class="Keyword">open</a> <a id="25723" class="Keyword">import</a> <a id="25730" href="order-theory.planar-binary-trees.html" class="Module">order-theory.planar-binary-trees</a>
<a id="25763" class="Keyword">open</a> <a id="25768" class="Keyword">import</a> <a id="25775" href="order-theory.posets.html" class="Module">order-theory.posets</a>
<a id="25795" class="Keyword">open</a> <a id="25800" class="Keyword">import</a> <a id="25807" href="order-theory.preorders.html" class="Module">order-theory.preorders</a>
<a id="25830" class="Keyword">open</a> <a id="25835" class="Keyword">import</a> <a id="25842" href="order-theory.subposets.html" class="Module">order-theory.subposets</a>
<a id="25865" class="Keyword">open</a> <a id="25870" class="Keyword">import</a> <a id="25877" href="order-theory.subpreorders.html" class="Module">order-theory.subpreorders</a>
<a id="25903" class="Keyword">open</a> <a id="25908" class="Keyword">import</a> <a id="25915" href="order-theory.total-posets.html" class="Module">order-theory.total-posets</a>
<a id="25941" class="Keyword">open</a> <a id="25946" class="Keyword">import</a> <a id="25953" href="order-theory.total-preorders.html" class="Module">order-theory.total-preorders</a>
</pre>
## Polytopes

<pre class="Agda"><a id="26009" class="Keyword">open</a> <a id="26014" class="Keyword">import</a> <a id="26021" href="polytopes.html" class="Module">polytopes</a>
<a id="26031" class="Keyword">open</a> <a id="26036" class="Keyword">import</a> <a id="26043" href="polytopes.abstract-polytopes.html" class="Module">polytopes.abstract-polytopes</a>
</pre>
## Ring theory

<pre class="Agda"><a id="26101" class="Keyword">open</a> <a id="26106" class="Keyword">import</a> <a id="26113" href="ring-theory.html" class="Module">ring-theory</a>
<a id="26125" class="Keyword">open</a> <a id="26130" class="Keyword">import</a> <a id="26137" href="ring-theory.division-rings.html" class="Module">ring-theory.division-rings</a>
<a id="26164" class="Keyword">open</a> <a id="26169" class="Keyword">import</a> <a id="26176" href="ring-theory.homomorphisms-rings.html" class="Module">ring-theory.homomorphisms-rings</a>
<a id="26208" class="Keyword">open</a> <a id="26213" class="Keyword">import</a> <a id="26220" href="ring-theory.ideals-generated-by-subsets-rings.html" class="Module">ring-theory.ideals-generated-by-subsets-rings</a>
<a id="26266" class="Keyword">open</a> <a id="26271" class="Keyword">import</a> <a id="26278" href="ring-theory.ideals-rings.html" class="Module">ring-theory.ideals-rings</a>
<a id="26303" class="Keyword">open</a> <a id="26308" class="Keyword">import</a> <a id="26315" href="ring-theory.invertible-elements-rings.html" class="Module">ring-theory.invertible-elements-rings</a>
<a id="26353" class="Keyword">open</a> <a id="26358" class="Keyword">import</a> <a id="26365" href="ring-theory.isomorphisms-rings.html" class="Module">ring-theory.isomorphisms-rings</a>
<a id="26396" class="Keyword">open</a> <a id="26401" class="Keyword">import</a> <a id="26408" href="ring-theory.localizations-rings.html" class="Module">ring-theory.localizations-rings</a>
<a id="26440" class="Keyword">open</a> <a id="26445" class="Keyword">import</a> <a id="26452" href="ring-theory.nontrivial-rings.html" class="Module">ring-theory.nontrivial-rings</a>
<a id="26481" class="Keyword">open</a> <a id="26486" class="Keyword">import</a> <a id="26493" href="ring-theory.opposite-rings.html" class="Module">ring-theory.opposite-rings</a>
<a id="26520" class="Keyword">open</a> <a id="26525" class="Keyword">import</a> <a id="26532" href="ring-theory.rings.html" class="Module">ring-theory.rings</a>
<a id="26550" class="Keyword">open</a> <a id="26555" class="Keyword">import</a> <a id="26562" href="ring-theory.subsets-rings.html" class="Module">ring-theory.subsets-rings</a>
</pre>
## Synthetic homotopy theory

<pre class="Agda"><a id="26631" class="Keyword">open</a> <a id="26636" class="Keyword">import</a> <a id="26643" href="synthetic-homotopy-theory.html" class="Module">synthetic-homotopy-theory</a>
<a id="26669" class="Keyword">open</a> <a id="26674" class="Keyword">import</a> <a id="26681" href="synthetic-homotopy-theory.23-pullbacks.html" class="Module">synthetic-homotopy-theory.23-pullbacks</a>
<a id="26720" class="Keyword">open</a> <a id="26725" class="Keyword">import</a> <a id="26732" href="synthetic-homotopy-theory.24-pushouts.html" class="Module">synthetic-homotopy-theory.24-pushouts</a>
<a id="26770" class="Keyword">open</a> <a id="26775" class="Keyword">import</a> <a id="26782" href="synthetic-homotopy-theory.25-cubical-diagrams.html" class="Module">synthetic-homotopy-theory.25-cubical-diagrams</a>
<a id="26828" class="Keyword">open</a> <a id="26833" class="Keyword">import</a> <a id="26840" href="synthetic-homotopy-theory.26-descent.html" class="Module">synthetic-homotopy-theory.26-descent</a>
<a id="26877" class="Keyword">open</a> <a id="26882" class="Keyword">import</a> <a id="26889" href="synthetic-homotopy-theory.26-id-pushout.html" class="Module">synthetic-homotopy-theory.26-id-pushout</a>
<a id="26929" class="Keyword">open</a> <a id="26934" class="Keyword">import</a> <a id="26941" href="synthetic-homotopy-theory.27-sequences.html" class="Module">synthetic-homotopy-theory.27-sequences</a>
<a id="26980" class="Keyword">open</a> <a id="26985" class="Keyword">import</a> <a id="26992" href="synthetic-homotopy-theory.circle.html" class="Module">synthetic-homotopy-theory.circle</a>
<a id="27025" class="Keyword">open</a> <a id="27030" class="Keyword">import</a> <a id="27037" href="synthetic-homotopy-theory.commutative-operations.html" class="Module">synthetic-homotopy-theory.commutative-operations</a>
<a id="27086" class="Keyword">open</a> <a id="27091" class="Keyword">import</a> <a id="27098" href="synthetic-homotopy-theory.cyclic-types.html" class="Module">synthetic-homotopy-theory.cyclic-types</a>
<a id="27137" class="Keyword">open</a> <a id="27142" class="Keyword">import</a> <a id="27149" href="synthetic-homotopy-theory.double-loop-spaces.html" class="Module">synthetic-homotopy-theory.double-loop-spaces</a>
<a id="27194" class="Keyword">open</a> <a id="27199" class="Keyword">import</a> <a id="27206" href="synthetic-homotopy-theory.functoriality-loop-spaces.html" class="Module">synthetic-homotopy-theory.functoriality-loop-spaces</a>
<a id="27258" class="Keyword">open</a> <a id="27263" class="Keyword">import</a> <a id="27270" href="synthetic-homotopy-theory.groups-of-loops-in-1-types.html" class="Module">synthetic-homotopy-theory.groups-of-loops-in-1-types</a>
<a id="27323" class="Keyword">open</a> <a id="27328" class="Keyword">import</a> <a id="27335" href="synthetic-homotopy-theory.infinite-cyclic-types.html" class="Module">synthetic-homotopy-theory.infinite-cyclic-types</a>
<a id="27383" class="Keyword">open</a> <a id="27388" class="Keyword">import</a> <a id="27395" href="synthetic-homotopy-theory.interval-type.html" class="Module">synthetic-homotopy-theory.interval-type</a>
<a id="27435" class="Keyword">open</a> <a id="27440" class="Keyword">import</a> <a id="27447" href="synthetic-homotopy-theory.iterated-loop-spaces.html" class="Module">synthetic-homotopy-theory.iterated-loop-spaces</a>
<a id="27494" class="Keyword">open</a> <a id="27499" class="Keyword">import</a> <a id="27506" href="synthetic-homotopy-theory.loop-spaces.html" class="Module">synthetic-homotopy-theory.loop-spaces</a>
<a id="27544" class="Keyword">open</a> <a id="27549" class="Keyword">import</a> <a id="27556" href="synthetic-homotopy-theory.pointed-dependent-functions.html" class="Module">synthetic-homotopy-theory.pointed-dependent-functions</a>
<a id="27610" class="Keyword">open</a> <a id="27615" class="Keyword">import</a> <a id="27622" href="synthetic-homotopy-theory.pointed-equivalences.html" class="Module">synthetic-homotopy-theory.pointed-equivalences</a>
<a id="27669" class="Keyword">open</a> <a id="27674" class="Keyword">import</a> <a id="27681" href="synthetic-homotopy-theory.pointed-families-of-types.html" class="Module">synthetic-homotopy-theory.pointed-families-of-types</a>
<a id="27733" class="Keyword">open</a> <a id="27738" class="Keyword">import</a> <a id="27745" href="synthetic-homotopy-theory.pointed-homotopies.html" class="Module">synthetic-homotopy-theory.pointed-homotopies</a>
<a id="27790" class="Keyword">open</a> <a id="27795" class="Keyword">import</a> <a id="27802" href="synthetic-homotopy-theory.pointed-maps.html" class="Module">synthetic-homotopy-theory.pointed-maps</a>
<a id="27841" class="Keyword">open</a> <a id="27846" class="Keyword">import</a> <a id="27853" href="synthetic-homotopy-theory.pointed-types.html" class="Module">synthetic-homotopy-theory.pointed-types</a>
<a id="27893" class="Keyword">open</a> <a id="27898" class="Keyword">import</a> <a id="27905" href="synthetic-homotopy-theory.spaces.html" class="Module">synthetic-homotopy-theory.spaces</a>
<a id="27938" class="Keyword">open</a> <a id="27943" class="Keyword">import</a> <a id="27950" href="synthetic-homotopy-theory.triple-loop-spaces.html" class="Module">synthetic-homotopy-theory.triple-loop-spaces</a>
<a id="27995" class="Keyword">open</a> <a id="28000" class="Keyword">import</a> <a id="28007" href="synthetic-homotopy-theory.universal-cover-circle.html" class="Module">synthetic-homotopy-theory.universal-cover-circle</a>
</pre>
## Tutorials

<pre class="Agda"><a id="28083" class="Keyword">open</a> <a id="28088" class="Keyword">import</a> <a id="28095" href="tutorials.basic-agda.html" class="Module">tutorials.basic-agda</a>
</pre>
## Type theories

<pre class="Agda"><a id="28147" class="Keyword">open</a> <a id="28152" class="Keyword">import</a> <a id="28159" href="type-theories.html" class="Module">type-theories</a>
<a id="28173" class="Keyword">open</a> <a id="28178" class="Keyword">import</a> <a id="28185" href="type-theories.comprehension-type-theories.html" class="Module">type-theories.comprehension-type-theories</a>
<a id="28227" class="Keyword">open</a> <a id="28232" class="Keyword">import</a> <a id="28239" href="type-theories.dependent-type-theories.html" class="Module">type-theories.dependent-type-theories</a>
<a id="28277" class="Keyword">open</a> <a id="28282" class="Keyword">import</a> <a id="28289" href="type-theories.fibered-dependent-type-theories.html" class="Module">type-theories.fibered-dependent-type-theories</a>
<a id="28335" class="Keyword">open</a> <a id="28340" class="Keyword">import</a> <a id="28347" href="type-theories.sections-dependent-type-theories.html" class="Module">type-theories.sections-dependent-type-theories</a>
<a id="28394" class="Keyword">open</a> <a id="28399" class="Keyword">import</a> <a id="28406" href="type-theories.simple-type-theories.html" class="Module">type-theories.simple-type-theories</a>
<a id="28441" class="Keyword">open</a> <a id="28446" class="Keyword">import</a> <a id="28453" href="type-theories.unityped-type-theories.html" class="Module">type-theories.unityped-type-theories</a>
</pre>
## Univalent combinatorics

<pre class="Agda"><a id="28531" class="Keyword">open</a> <a id="28536" class="Keyword">import</a> <a id="28543" href="univalent-combinatorics.html" class="Module">univalent-combinatorics</a>
<a id="28567" class="Keyword">open</a> <a id="28572" class="Keyword">import</a> <a id="28579" href="univalent-combinatorics.2-element-decidable-subtypes.html" class="Module">univalent-combinatorics.2-element-decidable-subtypes</a>
<a id="28632" class="Keyword">open</a> <a id="28637" class="Keyword">import</a> <a id="28644" href="univalent-combinatorics.2-element-subtypes.html" class="Module">univalent-combinatorics.2-element-subtypes</a>
<a id="28687" class="Keyword">open</a> <a id="28692" class="Keyword">import</a> <a id="28699" href="univalent-combinatorics.2-element-types.html" class="Module">univalent-combinatorics.2-element-types</a>
<a id="28739" class="Keyword">open</a> <a id="28744" class="Keyword">import</a> <a id="28751" href="univalent-combinatorics.binomial-types.html" class="Module">univalent-combinatorics.binomial-types</a>
<a id="28790" class="Keyword">open</a> <a id="28795" class="Keyword">import</a> <a id="28802" href="univalent-combinatorics.cartesian-product-types.html" class="Module">univalent-combinatorics.cartesian-product-types</a>
<a id="28850" class="Keyword">open</a> <a id="28855" class="Keyword">import</a> <a id="28862" href="univalent-combinatorics.classical-finite-types.html" class="Module">univalent-combinatorics.classical-finite-types</a>
<a id="28909" class="Keyword">open</a> <a id="28914" class="Keyword">import</a> <a id="28921" href="univalent-combinatorics.complements-isolated-points.html" class="Module">univalent-combinatorics.complements-isolated-points</a>
<a id="28973" class="Keyword">open</a> <a id="28978" class="Keyword">import</a> <a id="28985" href="univalent-combinatorics.coproduct-types.html" class="Module">univalent-combinatorics.coproduct-types</a>
<a id="29025" class="Keyword">open</a> <a id="29030" class="Keyword">import</a> <a id="29037" href="univalent-combinatorics.counting-decidable-subtypes.html" class="Module">univalent-combinatorics.counting-decidable-subtypes</a>
<a id="29089" class="Keyword">open</a> <a id="29094" class="Keyword">import</a> <a id="29101" href="univalent-combinatorics.counting-dependent-pair-types.html" class="Module">univalent-combinatorics.counting-dependent-pair-types</a>
<a id="29155" class="Keyword">open</a> <a id="29160" class="Keyword">import</a> <a id="29167" href="univalent-combinatorics.counting-fibers-of-maps.html" class="Module">univalent-combinatorics.counting-fibers-of-maps</a>
<a id="29215" class="Keyword">open</a> <a id="29220" class="Keyword">import</a> <a id="29227" href="univalent-combinatorics.counting-maybe.html" class="Module">univalent-combinatorics.counting-maybe</a>
<a id="29266" class="Keyword">open</a> <a id="29271" class="Keyword">import</a> <a id="29278" href="univalent-combinatorics.counting.html" class="Module">univalent-combinatorics.counting</a>
<a id="29311" class="Keyword">open</a> <a id="29316" class="Keyword">import</a> <a id="29323" href="univalent-combinatorics.cubes.html" class="Module">univalent-combinatorics.cubes</a>
<a id="29353" class="Keyword">open</a> <a id="29358" class="Keyword">import</a> <a id="29365" href="univalent-combinatorics.decidable-dependent-function-types.html" class="Module">univalent-combinatorics.decidable-dependent-function-types</a>
<a id="29424" class="Keyword">open</a> <a id="29429" class="Keyword">import</a> <a id="29436" href="univalent-combinatorics.decidable-dependent-pair-types.html" class="Module">univalent-combinatorics.decidable-dependent-pair-types</a>
<a id="29491" class="Keyword">open</a> <a id="29496" class="Keyword">import</a> <a id="29503" href="univalent-combinatorics.decidable-propositions.html" class="Module">univalent-combinatorics.decidable-propositions</a>
<a id="29550" class="Keyword">open</a> <a id="29555" class="Keyword">import</a> <a id="29562" href="univalent-combinatorics.decidable-subtypes.html" class="Module">univalent-combinatorics.decidable-subtypes</a>
<a id="29605" class="Keyword">open</a> <a id="29610" class="Keyword">import</a> <a id="29617" href="univalent-combinatorics.dedekind-finite-sets.html" class="Module">univalent-combinatorics.dedekind-finite-sets</a>
<a id="29662" class="Keyword">open</a> <a id="29667" class="Keyword">import</a> <a id="29674" href="univalent-combinatorics.dependent-function-types.html" class="Module">univalent-combinatorics.dependent-function-types</a>
<a id="29723" class="Keyword">open</a> <a id="29728" class="Keyword">import</a> <a id="29735" href="univalent-combinatorics.dependent-sum-finite-types.html" class="Module">univalent-combinatorics.dependent-sum-finite-types</a>
<a id="29786" class="Keyword">open</a> <a id="29791" class="Keyword">import</a> <a id="29798" href="univalent-combinatorics.distributivity-of-set-truncation-over-finite-products.html" class="Module">univalent-combinatorics.distributivity-of-set-truncation-over-finite-products</a>
<a id="29876" class="Keyword">open</a> <a id="29881" class="Keyword">import</a> <a id="29888" href="univalent-combinatorics.double-counting.html" class="Module">univalent-combinatorics.double-counting</a>
<a id="29928" class="Keyword">open</a> <a id="29933" class="Keyword">import</a> <a id="29940" href="univalent-combinatorics.embeddings-standard-finite-types.html" class="Module">univalent-combinatorics.embeddings-standard-finite-types</a>
<a id="29997" class="Keyword">open</a> <a id="30002" class="Keyword">import</a> <a id="30009" href="univalent-combinatorics.embeddings.html" class="Module">univalent-combinatorics.embeddings</a>
<a id="30044" class="Keyword">open</a> <a id="30049" class="Keyword">import</a> <a id="30056" href="univalent-combinatorics.equality-finite-types.html" class="Module">univalent-combinatorics.equality-finite-types</a>
<a id="30102" class="Keyword">open</a> <a id="30107" class="Keyword">import</a> <a id="30114" href="univalent-combinatorics.equality-standard-finite-types.html" class="Module">univalent-combinatorics.equality-standard-finite-types</a>
<a id="30169" class="Keyword">open</a> <a id="30174" class="Keyword">import</a> <a id="30181" href="univalent-combinatorics.equivalences-cubes.html" class="Module">univalent-combinatorics.equivalences-cubes</a>
<a id="30224" class="Keyword">open</a> <a id="30229" class="Keyword">import</a> <a id="30236" href="univalent-combinatorics.equivalences-standard-finite-types.html" class="Module">univalent-combinatorics.equivalences-standard-finite-types</a>
<a id="30295" class="Keyword">open</a> <a id="30300" class="Keyword">import</a> <a id="30307" href="univalent-combinatorics.equivalences.html" class="Module">univalent-combinatorics.equivalences</a>
<a id="30344" class="Keyword">open</a> <a id="30349" class="Keyword">import</a> <a id="30356" href="univalent-combinatorics.ferrers-diagrams.html" class="Module">univalent-combinatorics.ferrers-diagrams</a>
<a id="30397" class="Keyword">open</a> <a id="30402" class="Keyword">import</a> <a id="30409" href="univalent-combinatorics.fibers-of-maps.html" class="Module">univalent-combinatorics.fibers-of-maps</a>
<a id="30448" class="Keyword">open</a> <a id="30453" class="Keyword">import</a> <a id="30460" href="univalent-combinatorics.finite-choice.html" class="Module">univalent-combinatorics.finite-choice</a>
<a id="30498" class="Keyword">open</a> <a id="30503" class="Keyword">import</a> <a id="30510" href="univalent-combinatorics.finite-connected-components.html" class="Module">univalent-combinatorics.finite-connected-components</a>
<a id="30562" class="Keyword">open</a> <a id="30567" class="Keyword">import</a> <a id="30574" href="univalent-combinatorics.finite-presentations.html" class="Module">univalent-combinatorics.finite-presentations</a>
<a id="30619" class="Keyword">open</a> <a id="30624" class="Keyword">import</a> <a id="30631" href="univalent-combinatorics.finite-types.html" class="Module">univalent-combinatorics.finite-types</a>
<a id="30668" class="Keyword">open</a> <a id="30673" class="Keyword">import</a> <a id="30680" href="univalent-combinatorics.finitely-presented-types.html" class="Module">univalent-combinatorics.finitely-presented-types</a>
<a id="30729" class="Keyword">open</a> <a id="30734" class="Keyword">import</a> <a id="30741" href="univalent-combinatorics.function-types.html" class="Module">univalent-combinatorics.function-types</a>
<a id="30780" class="Keyword">open</a> <a id="30785" class="Keyword">import</a> <a id="30792" href="univalent-combinatorics.image-of-maps.html" class="Module">univalent-combinatorics.image-of-maps</a>
<a id="30830" class="Keyword">open</a> <a id="30835" class="Keyword">import</a> <a id="30842" href="univalent-combinatorics.inequality-types-with-counting.html" class="Module">univalent-combinatorics.inequality-types-with-counting</a>
<a id="30897" class="Keyword">open</a> <a id="30902" class="Keyword">import</a> <a id="30909" href="univalent-combinatorics.injective-maps.html" class="Module">univalent-combinatorics.injective-maps</a>
<a id="30948" class="Keyword">open</a> <a id="30953" class="Keyword">import</a> <a id="30960" href="univalent-combinatorics.kuratowsky-finite-sets.html" class="Module">univalent-combinatorics.kuratowsky-finite-sets</a>
<a id="31007" class="Keyword">open</a> <a id="31012" class="Keyword">import</a> <a id="31019" href="univalent-combinatorics.lists.html" class="Module">univalent-combinatorics.lists</a>
<a id="31049" class="Keyword">open</a> <a id="31054" class="Keyword">import</a> <a id="31061" href="univalent-combinatorics.maybe.html" class="Module">univalent-combinatorics.maybe</a>
<a id="31091" class="Keyword">open</a> <a id="31096" class="Keyword">import</a> <a id="31103" href="univalent-combinatorics.orientations-complete-undirected-graph.html" class="Module">univalent-combinatorics.orientations-complete-undirected-graph</a>
<a id="31166" class="Keyword">open</a> <a id="31171" class="Keyword">import</a> <a id="31178" href="univalent-combinatorics.orientations-cubes.html" class="Module">univalent-combinatorics.orientations-cubes</a>
<a id="31221" class="Keyword">open</a> <a id="31226" class="Keyword">import</a> <a id="31233" href="univalent-combinatorics.petri-nets.html" class="Module">univalent-combinatorics.petri-nets</a>
<a id="31268" class="Keyword">open</a> <a id="31273" class="Keyword">import</a> <a id="31280" href="univalent-combinatorics.pi-finite-types.html" class="Module">univalent-combinatorics.pi-finite-types</a>
<a id="31320" class="Keyword">open</a> <a id="31325" class="Keyword">import</a> <a id="31332" href="univalent-combinatorics.pigeonhole-principle.html" class="Module">univalent-combinatorics.pigeonhole-principle</a>
<a id="31377" class="Keyword">open</a> <a id="31382" class="Keyword">import</a> <a id="31389" href="univalent-combinatorics.presented-pi-finite-types.html" class="Module">univalent-combinatorics.presented-pi-finite-types</a>
<a id="31439" class="Keyword">open</a> <a id="31444" class="Keyword">import</a> <a id="31451" href="univalent-combinatorics.ramsey-theory.html" class="Module">univalent-combinatorics.ramsey-theory</a>
<a id="31489" class="Keyword">open</a> <a id="31494" class="Keyword">import</a> <a id="31501" href="univalent-combinatorics.retracts-of-finite-types.html" class="Module">univalent-combinatorics.retracts-of-finite-types</a>
<a id="31550" class="Keyword">open</a> <a id="31555" class="Keyword">import</a> <a id="31562" href="univalent-combinatorics.skipping-element-standard-finite-types.html" class="Module">univalent-combinatorics.skipping-element-standard-finite-types</a>
<a id="31625" class="Keyword">open</a> <a id="31630" class="Keyword">import</a> <a id="31637" href="univalent-combinatorics.species.html" class="Module">univalent-combinatorics.species</a>
<a id="31669" class="Keyword">open</a> <a id="31674" class="Keyword">import</a> <a id="31681" href="univalent-combinatorics.standard-finite-pruned-trees.html" class="Module">univalent-combinatorics.standard-finite-pruned-trees</a>
<a id="31734" class="Keyword">open</a> <a id="31739" class="Keyword">import</a> <a id="31746" href="univalent-combinatorics.standard-finite-trees.html" class="Module">univalent-combinatorics.standard-finite-trees</a>
<a id="31792" class="Keyword">open</a> <a id="31797" class="Keyword">import</a> <a id="31804" href="univalent-combinatorics.standard-finite-types.html" class="Module">univalent-combinatorics.standard-finite-types</a>
<a id="31850" class="Keyword">open</a> <a id="31855" class="Keyword">import</a> <a id="31862" href="univalent-combinatorics.sums-of-natural-numbers.html" class="Module">univalent-combinatorics.sums-of-natural-numbers</a>
<a id="31910" class="Keyword">open</a> <a id="31915" class="Keyword">import</a> <a id="31922" href="univalent-combinatorics.surjective-maps.html" class="Module">univalent-combinatorics.surjective-maps</a>
<a id="31962" class="Keyword">open</a> <a id="31967" class="Keyword">import</a> <a id="31974" href="univalent-combinatorics.symmetric-difference.html" class="Module">univalent-combinatorics.symmetric-difference</a>
</pre>
## Wild algebra

<pre class="Agda"><a id="32049" class="Keyword">open</a> <a id="32054" class="Keyword">import</a> <a id="32061" href="wild-algebra.html" class="Module">wild-algebra</a>
<a id="32074" class="Keyword">open</a> <a id="32079" class="Keyword">import</a> <a id="32086" href="wild-algebra.magmas.html" class="Module">wild-algebra.magmas</a>
<a id="32106" class="Keyword">open</a> <a id="32111" class="Keyword">import</a> <a id="32118" href="wild-algebra.morphisms-magmas.html" class="Module">wild-algebra.morphisms-magmas</a>
<a id="32148" class="Keyword">open</a> <a id="32153" class="Keyword">import</a> <a id="32160" href="wild-algebra.morphisms-wild-unital-magmas.html" class="Module">wild-algebra.morphisms-wild-unital-magmas</a>
<a id="32202" class="Keyword">open</a> <a id="32207" class="Keyword">import</a> <a id="32214" href="wild-algebra.universal-property-lists-wild-monoids.html" class="Module">wild-algebra.universal-property-lists-wild-monoids</a>
<a id="32265" class="Keyword">open</a> <a id="32270" class="Keyword">import</a> <a id="32277" href="wild-algebra.wild-groups.html" class="Module">wild-algebra.wild-groups</a>
<a id="32302" class="Keyword">open</a> <a id="32307" class="Keyword">import</a> <a id="32314" href="wild-algebra.wild-loops.html" class="Module">wild-algebra.wild-loops</a>
<a id="32338" class="Keyword">open</a> <a id="32343" class="Keyword">import</a> <a id="32350" href="wild-algebra.wild-monoids.html" class="Module">wild-algebra.wild-monoids</a>
<a id="32376" class="Keyword">open</a> <a id="32381" class="Keyword">import</a> <a id="32388" href="wild-algebra.wild-quasigroups.html" class="Module">wild-algebra.wild-quasigroups</a>
<a id="32418" class="Keyword">open</a> <a id="32423" class="Keyword">import</a> <a id="32430" href="wild-algebra.wild-semigroups.html" class="Module">wild-algebra.wild-semigroups</a>
<a id="32459" class="Keyword">open</a> <a id="32464" class="Keyword">import</a> <a id="32471" href="wild-algebra.wild-unital-magmas.html" class="Module">wild-algebra.wild-unital-magmas</a>
</pre>
## Everything

See the list of all Agda modules [here](everything.html).

