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
<a id="3223" class="Keyword">open</a> <a id="3228" class="Keyword">import</a> <a id="3235" href="category-theory.equivalences-categories.html" class="Module">category-theory.equivalences-categories</a>
<a id="3275" class="Keyword">open</a> <a id="3280" class="Keyword">import</a> <a id="3287" href="category-theory.equivalences-large-precategories.html" class="Module">category-theory.equivalences-large-precategories</a>
<a id="3336" class="Keyword">open</a> <a id="3341" class="Keyword">import</a> <a id="3348" href="category-theory.equivalences-precategories.html" class="Module">category-theory.equivalences-precategories</a>
<a id="3391" class="Keyword">open</a> <a id="3396" class="Keyword">import</a> <a id="3403" href="category-theory.functors-categories.html" class="Module">category-theory.functors-categories</a>
<a id="3439" class="Keyword">open</a> <a id="3444" class="Keyword">import</a> <a id="3451" href="category-theory.functors-large-precategories.html" class="Module">category-theory.functors-large-precategories</a>
<a id="3496" class="Keyword">open</a> <a id="3501" class="Keyword">import</a> <a id="3508" href="category-theory.functors-precategories.html" class="Module">category-theory.functors-precategories</a>
<a id="3547" class="Keyword">open</a> <a id="3552" class="Keyword">import</a> <a id="3559" href="category-theory.homotopies-natural-transformations-large-precategories.html" class="Module">category-theory.homotopies-natural-transformations-large-precategories</a>
<a id="3630" class="Keyword">open</a> <a id="3635" class="Keyword">import</a> <a id="3642" href="category-theory.initial-objects-precategories.html" class="Module">category-theory.initial-objects-precategories</a>
<a id="3688" class="Keyword">open</a> <a id="3693" class="Keyword">import</a> <a id="3700" href="category-theory.isomorphisms-categories.html" class="Module">category-theory.isomorphisms-categories</a>
<a id="3740" class="Keyword">open</a> <a id="3745" class="Keyword">import</a> <a id="3752" href="category-theory.isomorphisms-large-precategories.html" class="Module">category-theory.isomorphisms-large-precategories</a>
<a id="3801" class="Keyword">open</a> <a id="3806" class="Keyword">import</a> <a id="3813" href="category-theory.isomorphisms-precategories.html" class="Module">category-theory.isomorphisms-precategories</a>
<a id="3856" class="Keyword">open</a> <a id="3861" class="Keyword">import</a> <a id="3868" href="category-theory.large-categories.html" class="Module">category-theory.large-categories</a>
<a id="3901" class="Keyword">open</a> <a id="3906" class="Keyword">import</a> <a id="3913" href="category-theory.large-precategories.html" class="Module">category-theory.large-precategories</a>
<a id="3949" class="Keyword">open</a> <a id="3954" class="Keyword">import</a> <a id="3961" href="category-theory.monomorphisms-large-precategories.html" class="Module">category-theory.monomorphisms-large-precategories</a>
<a id="4011" class="Keyword">open</a> <a id="4016" class="Keyword">import</a> <a id="4023" href="category-theory.natural-isomorphisms-categories.html" class="Module">category-theory.natural-isomorphisms-categories</a>
<a id="4071" class="Keyword">open</a> <a id="4076" class="Keyword">import</a> <a id="4083" href="category-theory.natural-isomorphisms-large-precategories.html" class="Module">category-theory.natural-isomorphisms-large-precategories</a>
<a id="4140" class="Keyword">open</a> <a id="4145" class="Keyword">import</a> <a id="4152" href="category-theory.natural-isomorphisms-precategories.html" class="Module">category-theory.natural-isomorphisms-precategories</a>
<a id="4203" class="Keyword">open</a> <a id="4208" class="Keyword">import</a> <a id="4215" href="category-theory.natural-transformations-categories.html" class="Module">category-theory.natural-transformations-categories</a>
<a id="4266" class="Keyword">open</a> <a id="4271" class="Keyword">import</a> <a id="4278" href="category-theory.natural-transformations-large-precategories.html" class="Module">category-theory.natural-transformations-large-precategories</a>
<a id="4338" class="Keyword">open</a> <a id="4343" class="Keyword">import</a> <a id="4350" href="category-theory.natural-transformations-precategories.html" class="Module">category-theory.natural-transformations-precategories</a>
<a id="4404" class="Keyword">open</a> <a id="4409" class="Keyword">import</a> <a id="4416" href="category-theory.precategories.html" class="Module">category-theory.precategories</a>
<a id="4446" class="Keyword">open</a> <a id="4451" class="Keyword">import</a> <a id="4458" href="category-theory.slice-precategories.html" class="Module">category-theory.slice-precategories</a>
<a id="4494" class="Keyword">open</a> <a id="4499" class="Keyword">import</a> <a id="4506" href="category-theory.terminal-objects-precategories.html" class="Module">category-theory.terminal-objects-precategories</a>
</pre>
## Elementary number theory

<pre class="Agda"><a id="4595" class="Keyword">open</a> <a id="4600" class="Keyword">import</a> <a id="4607" href="elementary-number-theory.html" class="Module">elementary-number-theory</a>
<a id="4632" class="Keyword">open</a> <a id="4637" class="Keyword">import</a> <a id="4644" href="elementary-number-theory.absolute-value-integers.html" class="Module">elementary-number-theory.absolute-value-integers</a>
<a id="4693" class="Keyword">open</a> <a id="4698" class="Keyword">import</a> <a id="4705" href="elementary-number-theory.addition-integers.html" class="Module">elementary-number-theory.addition-integers</a>
<a id="4748" class="Keyword">open</a> <a id="4753" class="Keyword">import</a> <a id="4760" href="elementary-number-theory.addition-natural-numbers.html" class="Module">elementary-number-theory.addition-natural-numbers</a>
<a id="4810" class="Keyword">open</a> <a id="4815" class="Keyword">import</a> <a id="4822" href="elementary-number-theory.arithmetic-functions.html" class="Module">elementary-number-theory.arithmetic-functions</a>
<a id="4868" class="Keyword">open</a> <a id="4873" class="Keyword">import</a> <a id="4880" href="elementary-number-theory.binomial-coefficients.html" class="Module">elementary-number-theory.binomial-coefficients</a>
<a id="4927" class="Keyword">open</a> <a id="4932" class="Keyword">import</a> <a id="4939" href="elementary-number-theory.bounded-sums-arithmetic-functions.html" class="Module">elementary-number-theory.bounded-sums-arithmetic-functions</a>
<a id="4998" class="Keyword">open</a> <a id="5003" class="Keyword">import</a> <a id="5010" href="elementary-number-theory.catalan-numbers.html" class="Module">elementary-number-theory.catalan-numbers</a>
<a id="5051" class="Keyword">open</a> <a id="5056" class="Keyword">import</a> <a id="5063" href="elementary-number-theory.collatz-bijection.html" class="Module">elementary-number-theory.collatz-bijection</a>
<a id="5106" class="Keyword">open</a> <a id="5111" class="Keyword">import</a> <a id="5118" href="elementary-number-theory.collatz-conjecture.html" class="Module">elementary-number-theory.collatz-conjecture</a>
<a id="5162" class="Keyword">open</a> <a id="5167" class="Keyword">import</a> <a id="5174" href="elementary-number-theory.congruence-integers.html" class="Module">elementary-number-theory.congruence-integers</a>
<a id="5219" class="Keyword">open</a> <a id="5224" class="Keyword">import</a> <a id="5231" href="elementary-number-theory.congruence-natural-numbers.html" class="Module">elementary-number-theory.congruence-natural-numbers</a>
<a id="5283" class="Keyword">open</a> <a id="5288" class="Keyword">import</a> <a id="5295" href="elementary-number-theory.decidable-dependent-function-types.html" class="Module">elementary-number-theory.decidable-dependent-function-types</a>
<a id="5355" class="Keyword">open</a> <a id="5360" class="Keyword">import</a> <a id="5367" href="elementary-number-theory.decidable-types.html" class="Module">elementary-number-theory.decidable-types</a>
<a id="5408" class="Keyword">open</a> <a id="5413" class="Keyword">import</a> <a id="5420" href="elementary-number-theory.difference-integers.html" class="Module">elementary-number-theory.difference-integers</a>
<a id="5465" class="Keyword">open</a> <a id="5470" class="Keyword">import</a> <a id="5477" href="elementary-number-theory.dirichlet-convolution.html" class="Module">elementary-number-theory.dirichlet-convolution</a>
<a id="5524" class="Keyword">open</a> <a id="5529" class="Keyword">import</a> <a id="5536" href="elementary-number-theory.distance-integers.html" class="Module">elementary-number-theory.distance-integers</a>
<a id="5579" class="Keyword">open</a> <a id="5584" class="Keyword">import</a> <a id="5591" href="elementary-number-theory.distance-natural-numbers.html" class="Module">elementary-number-theory.distance-natural-numbers</a>
<a id="5641" class="Keyword">open</a> <a id="5646" class="Keyword">import</a> <a id="5653" href="elementary-number-theory.divisibility-integers.html" class="Module">elementary-number-theory.divisibility-integers</a>
<a id="5700" class="Keyword">open</a> <a id="5705" class="Keyword">import</a> <a id="5712" href="elementary-number-theory.divisibility-modular-arithmetic.html" class="Module">elementary-number-theory.divisibility-modular-arithmetic</a>
<a id="5769" class="Keyword">open</a> <a id="5774" class="Keyword">import</a> <a id="5781" href="elementary-number-theory.divisibility-natural-numbers.html" class="Module">elementary-number-theory.divisibility-natural-numbers</a>
<a id="5835" class="Keyword">open</a> <a id="5840" class="Keyword">import</a> <a id="5847" href="elementary-number-theory.divisibility-standard-finite-types.html" class="Module">elementary-number-theory.divisibility-standard-finite-types</a>
<a id="5907" class="Keyword">open</a> <a id="5912" class="Keyword">import</a> <a id="5919" href="elementary-number-theory.equality-integers.html" class="Module">elementary-number-theory.equality-integers</a>
<a id="5962" class="Keyword">open</a> <a id="5967" class="Keyword">import</a> <a id="5974" href="elementary-number-theory.equality-natural-numbers.html" class="Module">elementary-number-theory.equality-natural-numbers</a>
<a id="6024" class="Keyword">open</a> <a id="6029" class="Keyword">import</a> <a id="6036" href="elementary-number-theory.euclidean-division-natural-numbers.html" class="Module">elementary-number-theory.euclidean-division-natural-numbers</a>
<a id="6096" class="Keyword">open</a> <a id="6101" class="Keyword">import</a> <a id="6108" href="elementary-number-theory.eulers-totient-function.html" class="Module">elementary-number-theory.eulers-totient-function</a>
<a id="6157" class="Keyword">open</a> <a id="6162" class="Keyword">import</a> <a id="6169" href="elementary-number-theory.exponentiation-natural-numbers.html" class="Module">elementary-number-theory.exponentiation-natural-numbers</a>
<a id="6225" class="Keyword">open</a> <a id="6230" class="Keyword">import</a> <a id="6237" href="elementary-number-theory.factorials.html" class="Module">elementary-number-theory.factorials</a>
<a id="6273" class="Keyword">open</a> <a id="6278" class="Keyword">import</a> <a id="6285" href="elementary-number-theory.falling-factorials.html" class="Module">elementary-number-theory.falling-factorials</a>
<a id="6329" class="Keyword">open</a> <a id="6334" class="Keyword">import</a> <a id="6341" href="elementary-number-theory.fibonacci-sequence.html" class="Module">elementary-number-theory.fibonacci-sequence</a>
<a id="6385" class="Keyword">open</a> <a id="6390" class="Keyword">import</a> <a id="6397" href="elementary-number-theory.finitary-natural-numbers.html" class="Module">elementary-number-theory.finitary-natural-numbers</a>
<a id="6447" class="Keyword">open</a> <a id="6452" class="Keyword">import</a> <a id="6459" href="elementary-number-theory.finitely-cyclic-maps.html" class="Module">elementary-number-theory.finitely-cyclic-maps</a>
<a id="6505" class="Keyword">open</a> <a id="6510" class="Keyword">import</a> <a id="6517" href="elementary-number-theory.fractions.html" class="Module">elementary-number-theory.fractions</a>
<a id="6552" class="Keyword">open</a> <a id="6557" class="Keyword">import</a> <a id="6564" href="elementary-number-theory.goldbach-conjecture.html" class="Module">elementary-number-theory.goldbach-conjecture</a>
<a id="6609" class="Keyword">open</a> <a id="6614" class="Keyword">import</a> <a id="6621" href="elementary-number-theory.greatest-common-divisor-integers.html" class="Module">elementary-number-theory.greatest-common-divisor-integers</a>
<a id="6679" class="Keyword">open</a> <a id="6684" class="Keyword">import</a> <a id="6691" href="elementary-number-theory.greatest-common-divisor-natural-numbers.html" class="Module">elementary-number-theory.greatest-common-divisor-natural-numbers</a>
<a id="6756" class="Keyword">open</a> <a id="6761" class="Keyword">import</a> <a id="6768" href="elementary-number-theory.group-of-integers.html" class="Module">elementary-number-theory.group-of-integers</a>
<a id="6811" class="Keyword">open</a> <a id="6816" class="Keyword">import</a> <a id="6823" href="elementary-number-theory.groups-of-modular-arithmetic.html" class="Module">elementary-number-theory.groups-of-modular-arithmetic</a>
<a id="6877" class="Keyword">open</a> <a id="6882" class="Keyword">import</a> <a id="6889" href="elementary-number-theory.inequality-integers.html" class="Module">elementary-number-theory.inequality-integers</a>
<a id="6934" class="Keyword">open</a> <a id="6939" class="Keyword">import</a> <a id="6946" href="elementary-number-theory.inequality-natural-numbers.html" class="Module">elementary-number-theory.inequality-natural-numbers</a>
<a id="6998" class="Keyword">open</a> <a id="7003" class="Keyword">import</a> <a id="7010" href="elementary-number-theory.inequality-standard-finite-types.html" class="Module">elementary-number-theory.inequality-standard-finite-types</a>
<a id="7068" class="Keyword">open</a> <a id="7073" class="Keyword">import</a> <a id="7080" href="elementary-number-theory.infinitude-of-primes.html" class="Module">elementary-number-theory.infinitude-of-primes</a>
<a id="7126" class="Keyword">open</a> <a id="7131" class="Keyword">import</a> <a id="7138" href="elementary-number-theory.integers.html" class="Module">elementary-number-theory.integers</a>
<a id="7172" class="Keyword">open</a> <a id="7177" class="Keyword">import</a> <a id="7184" href="elementary-number-theory.iterating-functions.html" class="Module">elementary-number-theory.iterating-functions</a>
<a id="7229" class="Keyword">open</a> <a id="7234" class="Keyword">import</a> <a id="7241" href="elementary-number-theory.lower-bounds-natural-numbers.html" class="Module">elementary-number-theory.lower-bounds-natural-numbers</a>
<a id="7295" class="Keyword">open</a> <a id="7300" class="Keyword">import</a> <a id="7307" href="elementary-number-theory.maximum-natural-numbers.html" class="Module">elementary-number-theory.maximum-natural-numbers</a>
<a id="7356" class="Keyword">open</a> <a id="7361" class="Keyword">import</a> <a id="7368" href="elementary-number-theory.mersenne-primes.html" class="Module">elementary-number-theory.mersenne-primes</a>
<a id="7409" class="Keyword">open</a> <a id="7414" class="Keyword">import</a> <a id="7421" href="elementary-number-theory.minimum-natural-numbers.html" class="Module">elementary-number-theory.minimum-natural-numbers</a>
<a id="7470" class="Keyword">open</a> <a id="7475" class="Keyword">import</a> <a id="7482" href="elementary-number-theory.modular-arithmetic-standard-finite-types.html" class="Module">elementary-number-theory.modular-arithmetic-standard-finite-types</a>
<a id="7548" class="Keyword">open</a> <a id="7553" class="Keyword">import</a> <a id="7560" href="elementary-number-theory.modular-arithmetic.html" class="Module">elementary-number-theory.modular-arithmetic</a>
<a id="7604" class="Keyword">open</a> <a id="7609" class="Keyword">import</a> <a id="7616" href="elementary-number-theory.multiplication-integers.html" class="Module">elementary-number-theory.multiplication-integers</a>
<a id="7665" class="Keyword">open</a> <a id="7670" class="Keyword">import</a> <a id="7677" href="elementary-number-theory.multiplication-natural-numbers.html" class="Module">elementary-number-theory.multiplication-natural-numbers</a>
<a id="7733" class="Keyword">open</a> <a id="7738" class="Keyword">import</a> <a id="7745" href="elementary-number-theory.natural-numbers.html" class="Module">elementary-number-theory.natural-numbers</a>
<a id="7786" class="Keyword">open</a> <a id="7791" class="Keyword">import</a> <a id="7798" href="elementary-number-theory.nonzero-natural-numbers.html" class="Module">elementary-number-theory.nonzero-natural-numbers</a>
<a id="7847" class="Keyword">open</a> <a id="7852" class="Keyword">import</a> <a id="7859" href="elementary-number-theory.ordinal-induction-natural-numbers.html" class="Module">elementary-number-theory.ordinal-induction-natural-numbers</a>
<a id="7918" class="Keyword">open</a> <a id="7923" class="Keyword">import</a> <a id="7930" href="elementary-number-theory.prime-numbers.html" class="Module">elementary-number-theory.prime-numbers</a>
<a id="7969" class="Keyword">open</a> <a id="7974" class="Keyword">import</a> <a id="7981" href="elementary-number-theory.products-of-natural-numbers.html" class="Module">elementary-number-theory.products-of-natural-numbers</a>
<a id="8034" class="Keyword">open</a> <a id="8039" class="Keyword">import</a> <a id="8046" href="elementary-number-theory.proper-divisors-natural-numbers.html" class="Module">elementary-number-theory.proper-divisors-natural-numbers</a>
<a id="8103" class="Keyword">open</a> <a id="8108" class="Keyword">import</a> <a id="8115" href="elementary-number-theory.rational-numbers.html" class="Module">elementary-number-theory.rational-numbers</a>
<a id="8157" class="Keyword">open</a> <a id="8162" class="Keyword">import</a> <a id="8169" href="elementary-number-theory.relatively-prime-integers.html" class="Module">elementary-number-theory.relatively-prime-integers</a>
<a id="8220" class="Keyword">open</a> <a id="8225" class="Keyword">import</a> <a id="8232" href="elementary-number-theory.relatively-prime-natural-numbers.html" class="Module">elementary-number-theory.relatively-prime-natural-numbers</a>
<a id="8290" class="Keyword">open</a> <a id="8295" class="Keyword">import</a> <a id="8302" href="elementary-number-theory.repeating-element-standard-finite-type.html" class="Module">elementary-number-theory.repeating-element-standard-finite-type</a>
<a id="8366" class="Keyword">open</a> <a id="8371" class="Keyword">import</a> <a id="8378" href="elementary-number-theory.retracts-of-natural-numbers.html" class="Module">elementary-number-theory.retracts-of-natural-numbers</a>
<a id="8431" class="Keyword">open</a> <a id="8436" class="Keyword">import</a> <a id="8443" href="elementary-number-theory.square-free-natural-numbers.html" class="Module">elementary-number-theory.square-free-natural-numbers</a>
<a id="8496" class="Keyword">open</a> <a id="8501" class="Keyword">import</a> <a id="8508" href="elementary-number-theory.stirling-numbers-of-the-second-kind.html" class="Module">elementary-number-theory.stirling-numbers-of-the-second-kind</a>
<a id="8569" class="Keyword">open</a> <a id="8574" class="Keyword">import</a> <a id="8581" href="elementary-number-theory.strong-induction-natural-numbers.html" class="Module">elementary-number-theory.strong-induction-natural-numbers</a>
<a id="8639" class="Keyword">open</a> <a id="8644" class="Keyword">import</a> <a id="8651" href="elementary-number-theory.sums-of-natural-numbers.html" class="Module">elementary-number-theory.sums-of-natural-numbers</a>
<a id="8700" class="Keyword">open</a> <a id="8705" class="Keyword">import</a> <a id="8712" href="elementary-number-theory.triangular-numbers.html" class="Module">elementary-number-theory.triangular-numbers</a>
<a id="8756" class="Keyword">open</a> <a id="8761" class="Keyword">import</a> <a id="8768" href="elementary-number-theory.telephone-numbers.html" class="Module">elementary-number-theory.telephone-numbers</a>
<a id="8811" class="Keyword">open</a> <a id="8816" class="Keyword">import</a> <a id="8823" href="elementary-number-theory.twin-prime-conjecture.html" class="Module">elementary-number-theory.twin-prime-conjecture</a>
<a id="8870" class="Keyword">open</a> <a id="8875" class="Keyword">import</a> <a id="8882" href="elementary-number-theory.unit-elements-standard-finite-types.html" class="Module">elementary-number-theory.unit-elements-standard-finite-types</a>
<a id="8943" class="Keyword">open</a> <a id="8948" class="Keyword">import</a> <a id="8955" href="elementary-number-theory.unit-similarity-standard-finite-types.html" class="Module">elementary-number-theory.unit-similarity-standard-finite-types</a>
<a id="9018" class="Keyword">open</a> <a id="9023" class="Keyword">import</a> <a id="9030" href="elementary-number-theory.universal-property-natural-numbers.html" class="Module">elementary-number-theory.universal-property-natural-numbers</a>
<a id="9090" class="Keyword">open</a> <a id="9095" class="Keyword">import</a> <a id="9102" href="elementary-number-theory.upper-bounds-natural-numbers.html" class="Module">elementary-number-theory.upper-bounds-natural-numbers</a>
<a id="9156" class="Keyword">open</a> <a id="9161" class="Keyword">import</a> <a id="9168" href="elementary-number-theory.well-ordering-principle-natural-numbers.html" class="Module">elementary-number-theory.well-ordering-principle-natural-numbers</a>
<a id="9233" class="Keyword">open</a> <a id="9238" class="Keyword">import</a> <a id="9245" href="elementary-number-theory.well-ordering-principle-standard-finite-types.html" class="Module">elementary-number-theory.well-ordering-principle-standard-finite-types</a>
</pre>
## Finite group theory

<pre class="Agda"><a id="9353" class="Keyword">open</a> <a id="9358" class="Keyword">import</a> <a id="9365" href="finite-group-theory.html" class="Module">finite-group-theory</a>
<a id="9385" class="Keyword">open</a> <a id="9390" class="Keyword">import</a> <a id="9397" href="finite-group-theory.abstract-quaternion-group.html" class="Module">finite-group-theory.abstract-quaternion-group</a>
<a id="9443" class="Keyword">open</a> <a id="9448" class="Keyword">import</a> <a id="9455" href="finite-group-theory.concrete-quaternion-group.html" class="Module">finite-group-theory.concrete-quaternion-group</a>
<a id="9501" class="Keyword">open</a> <a id="9506" class="Keyword">import</a> <a id="9513" href="finite-group-theory.finite-groups.html" class="Module">finite-group-theory.finite-groups</a>
<a id="9547" class="Keyword">open</a> <a id="9552" class="Keyword">import</a> <a id="9559" href="finite-group-theory.finite-monoids.html" class="Module">finite-group-theory.finite-monoids</a>
<a id="9594" class="Keyword">open</a> <a id="9599" class="Keyword">import</a> <a id="9606" href="finite-group-theory.finite-semigroups.html" class="Module">finite-group-theory.finite-semigroups</a>
<a id="9644" class="Keyword">open</a> <a id="9649" class="Keyword">import</a> <a id="9656" href="finite-group-theory.groups-of-order-2.html" class="Module">finite-group-theory.groups-of-order-2</a>
<a id="9694" class="Keyword">open</a> <a id="9699" class="Keyword">import</a> <a id="9706" href="finite-group-theory.orbits-permutations.html" class="Module">finite-group-theory.orbits-permutations</a>
<a id="9746" class="Keyword">open</a> <a id="9751" class="Keyword">import</a> <a id="9758" href="finite-group-theory.permutations.html" class="Module">finite-group-theory.permutations</a>
<a id="9791" class="Keyword">open</a> <a id="9796" class="Keyword">import</a> <a id="9803" href="finite-group-theory.sign-homomorphism.html" class="Module">finite-group-theory.sign-homomorphism</a>
<a id="9841" class="Keyword">open</a> <a id="9846" class="Keyword">import</a> <a id="9853" href="finite-group-theory.transpositions.html" class="Module">finite-group-theory.transpositions</a>
</pre>
## Foundation

<pre class="Agda"><a id="9916" class="Keyword">open</a> <a id="9921" class="Keyword">import</a> <a id="9928" href="foundation.html" class="Module">foundation</a>
<a id="9939" class="Keyword">open</a> <a id="9944" class="Keyword">import</a> <a id="9951" href="foundation.0-maps.html" class="Module">foundation.0-maps</a>
<a id="9969" class="Keyword">open</a> <a id="9974" class="Keyword">import</a> <a id="9981" href="foundation.1-types.html" class="Module">foundation.1-types</a>
<a id="10000" class="Keyword">open</a> <a id="10005" class="Keyword">import</a> <a id="10012" href="foundation.2-types.html" class="Module">foundation.2-types</a>
<a id="10031" class="Keyword">open</a> <a id="10036" class="Keyword">import</a> <a id="10043" href="foundation.algebras-polynomial-endofunctors.html" class="Module">foundation.algebras-polynomial-endofunctors</a>
<a id="10087" class="Keyword">open</a> <a id="10092" class="Keyword">import</a> <a id="10099" href="foundation.automorphisms.html" class="Module">foundation.automorphisms</a>
<a id="10124" class="Keyword">open</a> <a id="10129" class="Keyword">import</a> <a id="10136" href="foundation.axiom-of-choice.html" class="Module">foundation.axiom-of-choice</a>
<a id="10163" class="Keyword">open</a> <a id="10168" class="Keyword">import</a> <a id="10175" href="foundation.binary-embeddings.html" class="Module">foundation.binary-embeddings</a>
<a id="10204" class="Keyword">open</a> <a id="10209" class="Keyword">import</a> <a id="10216" href="foundation.binary-equivalences.html" class="Module">foundation.binary-equivalences</a>
<a id="10247" class="Keyword">open</a> <a id="10252" class="Keyword">import</a> <a id="10259" href="foundation.binary-relations.html" class="Module">foundation.binary-relations</a>
<a id="10287" class="Keyword">open</a> <a id="10292" class="Keyword">import</a> <a id="10299" href="foundation.boolean-reflection.html" class="Module">foundation.boolean-reflection</a>
<a id="10329" class="Keyword">open</a> <a id="10334" class="Keyword">import</a> <a id="10341" href="foundation.booleans.html" class="Module">foundation.booleans</a>
<a id="10361" class="Keyword">open</a> <a id="10366" class="Keyword">import</a> <a id="10373" href="foundation.cantors-diagonal-argument.html" class="Module">foundation.cantors-diagonal-argument</a>
<a id="10410" class="Keyword">open</a> <a id="10415" class="Keyword">import</a> <a id="10422" href="foundation.cartesian-product-types.html" class="Module">foundation.cartesian-product-types</a>
<a id="10457" class="Keyword">open</a> <a id="10462" class="Keyword">import</a> <a id="10469" href="foundation.choice-of-representatives-equivalence-relation.html" class="Module">foundation.choice-of-representatives-equivalence-relation</a>
<a id="10527" class="Keyword">open</a> <a id="10532" class="Keyword">import</a> <a id="10539" href="foundation.coherently-invertible-maps.html" class="Module">foundation.coherently-invertible-maps</a>
<a id="10577" class="Keyword">open</a> <a id="10582" class="Keyword">import</a> <a id="10589" href="foundation.commuting-squares.html" class="Module">foundation.commuting-squares</a>
<a id="10618" class="Keyword">open</a> <a id="10623" class="Keyword">import</a> <a id="10630" href="foundation.complements.html" class="Module">foundation.complements</a>
<a id="10653" class="Keyword">open</a> <a id="10658" class="Keyword">import</a> <a id="10665" href="foundation.conjunction.html" class="Module">foundation.conjunction</a>
<a id="10688" class="Keyword">open</a> <a id="10693" class="Keyword">import</a> <a id="10700" href="foundation.connected-components-universes.html" class="Module">foundation.connected-components-universes</a>
<a id="10742" class="Keyword">open</a> <a id="10747" class="Keyword">import</a> <a id="10754" href="foundation.connected-components.html" class="Module">foundation.connected-components</a>
<a id="10786" class="Keyword">open</a> <a id="10791" class="Keyword">import</a> <a id="10798" href="foundation.connected-types.html" class="Module">foundation.connected-types</a>
<a id="10825" class="Keyword">open</a> <a id="10830" class="Keyword">import</a> <a id="10837" href="foundation.constant-maps.html" class="Module">foundation.constant-maps</a>
<a id="10862" class="Keyword">open</a> <a id="10867" class="Keyword">import</a> <a id="10874" href="foundation.contractible-maps.html" class="Module">foundation.contractible-maps</a>
<a id="10903" class="Keyword">open</a> <a id="10908" class="Keyword">import</a> <a id="10915" href="foundation.contractible-types.html" class="Module">foundation.contractible-types</a>
<a id="10945" class="Keyword">open</a> <a id="10950" class="Keyword">import</a> <a id="10957" href="foundation.coproduct-types.html" class="Module">foundation.coproduct-types</a>
<a id="10984" class="Keyword">open</a> <a id="10989" class="Keyword">import</a> <a id="10996" href="foundation.coslice.html" class="Module">foundation.coslice</a>
<a id="11015" class="Keyword">open</a> <a id="11020" class="Keyword">import</a> <a id="11027" href="foundation.decidable-dependent-function-types.html" class="Module">foundation.decidable-dependent-function-types</a>
<a id="11073" class="Keyword">open</a> <a id="11078" class="Keyword">import</a> <a id="11085" href="foundation.decidable-dependent-pair-types.html" class="Module">foundation.decidable-dependent-pair-types</a>
<a id="11127" class="Keyword">open</a> <a id="11132" class="Keyword">import</a> <a id="11139" href="foundation.decidable-embeddings.html" class="Module">foundation.decidable-embeddings</a>
<a id="11171" class="Keyword">open</a> <a id="11176" class="Keyword">import</a> <a id="11183" href="foundation.decidable-equality.html" class="Module">foundation.decidable-equality</a>
<a id="11213" class="Keyword">open</a> <a id="11218" class="Keyword">import</a> <a id="11225" href="foundation.decidable-maps.html" class="Module">foundation.decidable-maps</a>
<a id="11251" class="Keyword">open</a> <a id="11256" class="Keyword">import</a> <a id="11263" href="foundation.decidable-propositions.html" class="Module">foundation.decidable-propositions</a>
<a id="11297" class="Keyword">open</a> <a id="11302" class="Keyword">import</a> <a id="11309" href="foundation.decidable-subtypes.html" class="Module">foundation.decidable-subtypes</a>
<a id="11339" class="Keyword">open</a> <a id="11344" class="Keyword">import</a> <a id="11351" href="foundation.decidable-types.html" class="Module">foundation.decidable-types</a>
<a id="11378" class="Keyword">open</a> <a id="11383" class="Keyword">import</a> <a id="11390" href="foundation.dependent-pair-types.html" class="Module">foundation.dependent-pair-types</a>
<a id="11422" class="Keyword">open</a> <a id="11427" class="Keyword">import</a> <a id="11434" href="foundation.diagonal-maps-of-types.html" class="Module">foundation.diagonal-maps-of-types</a>
<a id="11468" class="Keyword">open</a> <a id="11473" class="Keyword">import</a> <a id="11480" href="foundation.disjunction.html" class="Module">foundation.disjunction</a>
<a id="11503" class="Keyword">open</a> <a id="11508" class="Keyword">import</a> <a id="11515" href="foundation.distributivity-of-dependent-functions-over-coproduct-types.html" class="Module">foundation.distributivity-of-dependent-functions-over-coproduct-types</a>
<a id="11585" class="Keyword">open</a> <a id="11590" class="Keyword">import</a> <a id="11597" href="foundation.distributivity-of-dependent-functions-over-dependent-pairs.html" class="Module">foundation.distributivity-of-dependent-functions-over-dependent-pairs</a>
<a id="11667" class="Keyword">open</a> <a id="11672" class="Keyword">import</a> <a id="11679" href="foundation.double-negation.html" class="Module">foundation.double-negation</a>
<a id="11706" class="Keyword">open</a> <a id="11711" class="Keyword">import</a> <a id="11718" href="foundation.double-powersets.html" class="Module">foundation.double-powersets</a>
<a id="11746" class="Keyword">open</a> <a id="11751" class="Keyword">import</a> <a id="11758" href="foundation.dubuc-penon-compact-types.html" class="Module">foundation.dubuc-penon-compact-types</a>
<a id="11795" class="Keyword">open</a> <a id="11800" class="Keyword">import</a> <a id="11807" href="foundation.effective-maps-equivalence-relations.html" class="Module">foundation.effective-maps-equivalence-relations</a>
<a id="11855" class="Keyword">open</a> <a id="11860" class="Keyword">import</a> <a id="11867" href="foundation.elementhood-relation-w-types.html" class="Module">foundation.elementhood-relation-w-types</a>
<a id="11907" class="Keyword">open</a> <a id="11912" class="Keyword">import</a> <a id="11919" href="foundation.embeddings.html" class="Module">foundation.embeddings</a>
<a id="11941" class="Keyword">open</a> <a id="11946" class="Keyword">import</a> <a id="11953" href="foundation.empty-types.html" class="Module">foundation.empty-types</a>
<a id="11976" class="Keyword">open</a> <a id="11981" class="Keyword">import</a> <a id="11988" href="foundation.epimorphisms-with-respect-to-sets.html" class="Module">foundation.epimorphisms-with-respect-to-sets</a>
<a id="12033" class="Keyword">open</a> <a id="12038" class="Keyword">import</a> <a id="12045" href="foundation.equality-cartesian-product-types.html" class="Module">foundation.equality-cartesian-product-types</a>
<a id="12089" class="Keyword">open</a> <a id="12094" class="Keyword">import</a> <a id="12101" href="foundation.equality-coproduct-types.html" class="Module">foundation.equality-coproduct-types</a>
<a id="12137" class="Keyword">open</a> <a id="12142" class="Keyword">import</a> <a id="12149" href="foundation.equality-dependent-function-types.html" class="Module">foundation.equality-dependent-function-types</a>
<a id="12194" class="Keyword">open</a> <a id="12199" class="Keyword">import</a> <a id="12206" href="foundation.equality-dependent-pair-types.html" class="Module">foundation.equality-dependent-pair-types</a>
<a id="12247" class="Keyword">open</a> <a id="12252" class="Keyword">import</a> <a id="12259" href="foundation.equality-fibers-of-maps.html" class="Module">foundation.equality-fibers-of-maps</a>
<a id="12294" class="Keyword">open</a> <a id="12299" class="Keyword">import</a> <a id="12306" href="foundation.equivalence-classes.html" class="Module">foundation.equivalence-classes</a>
<a id="12337" class="Keyword">open</a> <a id="12342" class="Keyword">import</a> <a id="12349" href="foundation.equivalence-induction.html" class="Module">foundation.equivalence-induction</a>
<a id="12382" class="Keyword">open</a> <a id="12387" class="Keyword">import</a> <a id="12394" href="foundation.equivalence-relations.html" class="Module">foundation.equivalence-relations</a>
<a id="12427" class="Keyword">open</a> <a id="12432" class="Keyword">import</a> <a id="12439" href="foundation.equivalences-maybe.html" class="Module">foundation.equivalences-maybe</a>
<a id="12469" class="Keyword">open</a> <a id="12474" class="Keyword">import</a> <a id="12481" href="foundation.equivalences.html" class="Module">foundation.equivalences</a>
<a id="12505" class="Keyword">open</a> <a id="12510" class="Keyword">import</a> <a id="12517" href="foundation.existential-quantification.html" class="Module">foundation.existential-quantification</a>
<a id="12555" class="Keyword">open</a> <a id="12560" class="Keyword">import</a> <a id="12567" href="foundation.extensional-w-types.html" class="Module">foundation.extensional-w-types</a>
<a id="12598" class="Keyword">open</a> <a id="12603" class="Keyword">import</a> <a id="12610" href="foundation.faithful-maps.html" class="Module">foundation.faithful-maps</a>
<a id="12635" class="Keyword">open</a> <a id="12640" class="Keyword">import</a> <a id="12647" href="foundation.fiber-inclusions.html" class="Module">foundation.fiber-inclusions</a>
<a id="12675" class="Keyword">open</a> <a id="12680" class="Keyword">import</a> <a id="12687" href="foundation.fibered-maps.html" class="Module">foundation.fibered-maps</a>
<a id="12711" class="Keyword">open</a> <a id="12716" class="Keyword">import</a> <a id="12723" href="foundation.fibers-of-maps.html" class="Module">foundation.fibers-of-maps</a>
<a id="12749" class="Keyword">open</a> <a id="12754" class="Keyword">import</a> <a id="12761" href="foundation.function-extensionality.html" class="Module">foundation.function-extensionality</a>
<a id="12796" class="Keyword">open</a> <a id="12801" class="Keyword">import</a> <a id="12808" href="foundation.functions.html" class="Module">foundation.functions</a>
<a id="12829" class="Keyword">open</a> <a id="12834" class="Keyword">import</a> <a id="12841" href="foundation.functoriality-cartesian-product-types.html" class="Module">foundation.functoriality-cartesian-product-types</a>
<a id="12890" class="Keyword">open</a> <a id="12895" class="Keyword">import</a> <a id="12902" href="foundation.functoriality-coproduct-types.html" class="Module">foundation.functoriality-coproduct-types</a>
<a id="12943" class="Keyword">open</a> <a id="12948" class="Keyword">import</a> <a id="12955" href="foundation.functoriality-dependent-function-types.html" class="Module">foundation.functoriality-dependent-function-types</a>
<a id="13005" class="Keyword">open</a> <a id="13010" class="Keyword">import</a> <a id="13017" href="foundation.functoriality-dependent-pair-types.html" class="Module">foundation.functoriality-dependent-pair-types</a>
<a id="13063" class="Keyword">open</a> <a id="13068" class="Keyword">import</a> <a id="13075" href="foundation.functoriality-function-types.html" class="Module">foundation.functoriality-function-types</a>
<a id="13115" class="Keyword">open</a> <a id="13120" class="Keyword">import</a> <a id="13127" href="foundation.functoriality-propositional-truncation.html" class="Module">foundation.functoriality-propositional-truncation</a>
<a id="13177" class="Keyword">open</a> <a id="13182" class="Keyword">import</a> <a id="13189" href="foundation.functoriality-set-quotients.html" class="Module">foundation.functoriality-set-quotients</a>
<a id="13228" class="Keyword">open</a> <a id="13233" class="Keyword">import</a> <a id="13240" href="foundation.functoriality-set-truncation.html" class="Module">foundation.functoriality-set-truncation</a>
<a id="13280" class="Keyword">open</a> <a id="13285" class="Keyword">import</a> <a id="13292" href="foundation.functoriality-w-types.html" class="Module">foundation.functoriality-w-types</a>
<a id="13325" class="Keyword">open</a> <a id="13330" class="Keyword">import</a> <a id="13337" href="foundation.fundamental-theorem-of-identity-types.html" class="Module">foundation.fundamental-theorem-of-identity-types</a>
<a id="13386" class="Keyword">open</a> <a id="13391" class="Keyword">import</a> <a id="13398" href="foundation.global-choice.html" class="Module">foundation.global-choice</a>
<a id="13423" class="Keyword">open</a> <a id="13428" class="Keyword">import</a> <a id="13435" href="foundation.hilberts-epsilon-operators.html" class="Module">foundation.hilberts-epsilon-operators</a>
<a id="13473" class="Keyword">open</a> <a id="13478" class="Keyword">import</a> <a id="13485" href="foundation.homotopies.html" class="Module">foundation.homotopies</a>
<a id="13507" class="Keyword">open</a> <a id="13512" class="Keyword">import</a> <a id="13519" href="foundation.identity-systems.html" class="Module">foundation.identity-systems</a>
<a id="13547" class="Keyword">open</a> <a id="13552" class="Keyword">import</a> <a id="13559" href="foundation.identity-types.html" class="Module">foundation.identity-types</a>
<a id="13585" class="Keyword">open</a> <a id="13590" class="Keyword">import</a> <a id="13597" href="foundation.images.html" class="Module">foundation.images</a>
<a id="13615" class="Keyword">open</a> <a id="13620" class="Keyword">import</a> <a id="13627" href="foundation.impredicative-encodings.html" class="Module">foundation.impredicative-encodings</a>
<a id="13662" class="Keyword">open</a> <a id="13667" class="Keyword">import</a> <a id="13674" href="foundation.indexed-w-types.html" class="Module">foundation.indexed-w-types</a>
<a id="13701" class="Keyword">open</a> <a id="13706" class="Keyword">import</a> <a id="13713" href="foundation.induction-principle-propositional-truncation.html" class="Module">foundation.induction-principle-propositional-truncation</a>
<a id="13769" class="Keyword">open</a> <a id="13774" class="Keyword">import</a> <a id="13781" href="foundation.induction-w-types.html" class="Module">foundation.induction-w-types</a>
<a id="13810" class="Keyword">open</a> <a id="13815" class="Keyword">import</a> <a id="13822" href="foundation.inequality-w-types.html" class="Module">foundation.inequality-w-types</a>
<a id="13852" class="Keyword">open</a> <a id="13857" class="Keyword">import</a> <a id="13864" href="foundation.injective-maps.html" class="Module">foundation.injective-maps</a>
<a id="13890" class="Keyword">open</a> <a id="13895" class="Keyword">import</a> <a id="13902" href="foundation.interchange-law.html" class="Module">foundation.interchange-law</a>
<a id="13929" class="Keyword">open</a> <a id="13934" class="Keyword">import</a> <a id="13941" href="foundation.intersection.html" class="Module">foundation.intersection</a>
<a id="13965" class="Keyword">open</a> <a id="13970" class="Keyword">import</a> <a id="13977" href="foundation.involutions.html" class="Module">foundation.involutions</a>
<a id="14000" class="Keyword">open</a> <a id="14005" class="Keyword">import</a> <a id="14012" href="foundation.isolated-points.html" class="Module">foundation.isolated-points</a>
<a id="14039" class="Keyword">open</a> <a id="14044" class="Keyword">import</a> <a id="14051" href="foundation.isomorphisms-of-sets.html" class="Module">foundation.isomorphisms-of-sets</a>
<a id="14083" class="Keyword">open</a> <a id="14088" class="Keyword">import</a> <a id="14095" href="foundation.law-of-excluded-middle.html" class="Module">foundation.law-of-excluded-middle</a>
<a id="14129" class="Keyword">open</a> <a id="14134" class="Keyword">import</a> <a id="14141" href="foundation.lawveres-fixed-point-theorem.html" class="Module">foundation.lawveres-fixed-point-theorem</a>
<a id="14181" class="Keyword">open</a> <a id="14186" class="Keyword">import</a> <a id="14193" href="foundation.locally-small-types.html" class="Module">foundation.locally-small-types</a>
<a id="14224" class="Keyword">open</a> <a id="14229" class="Keyword">import</a> <a id="14236" href="foundation.logical-equivalences.html" class="Module">foundation.logical-equivalences</a>
<a id="14268" class="Keyword">open</a> <a id="14273" class="Keyword">import</a> <a id="14280" href="foundation.lower-types-w-types.html" class="Module">foundation.lower-types-w-types</a>
<a id="14311" class="Keyword">open</a> <a id="14316" class="Keyword">import</a> <a id="14323" href="foundation.maybe.html" class="Module">foundation.maybe</a>
<a id="14340" class="Keyword">open</a> <a id="14345" class="Keyword">import</a> <a id="14352" href="foundation.mere-equality.html" class="Module">foundation.mere-equality</a>
<a id="14377" class="Keyword">open</a> <a id="14382" class="Keyword">import</a> <a id="14389" href="foundation.mere-equivalences.html" class="Module">foundation.mere-equivalences</a>
<a id="14418" class="Keyword">open</a> <a id="14423" class="Keyword">import</a> <a id="14430" href="foundation.monomorphisms.html" class="Module">foundation.monomorphisms</a>
<a id="14455" class="Keyword">open</a> <a id="14460" class="Keyword">import</a> <a id="14467" href="foundation.multisets.html" class="Module">foundation.multisets</a>
<a id="14488" class="Keyword">open</a> <a id="14493" class="Keyword">import</a> <a id="14500" href="foundation.negation.html" class="Module">foundation.negation</a>
<a id="14520" class="Keyword">open</a> <a id="14525" class="Keyword">import</a> <a id="14532" href="foundation.non-contractible-types.html" class="Module">foundation.non-contractible-types</a>
<a id="14566" class="Keyword">open</a> <a id="14571" class="Keyword">import</a> <a id="14578" href="foundation.pairs-of-distinct-elements.html" class="Module">foundation.pairs-of-distinct-elements</a>
<a id="14616" class="Keyword">open</a> <a id="14621" class="Keyword">import</a> <a id="14628" href="foundation.path-algebra.html" class="Module">foundation.path-algebra</a>
<a id="14652" class="Keyword">open</a> <a id="14657" class="Keyword">import</a> <a id="14664" href="foundation.path-split-maps.html" class="Module">foundation.path-split-maps</a>
<a id="14691" class="Keyword">open</a> <a id="14696" class="Keyword">import</a> <a id="14703" href="foundation.polynomial-endofunctors.html" class="Module">foundation.polynomial-endofunctors</a>
<a id="14738" class="Keyword">open</a> <a id="14743" class="Keyword">import</a> <a id="14750" href="foundation.powersets.html" class="Module">foundation.powersets</a>
<a id="14771" class="Keyword">open</a> <a id="14776" class="Keyword">import</a> <a id="14783" href="foundation.principle-of-omniscience.html" class="Module">foundation.principle-of-omniscience</a>
<a id="14819" class="Keyword">open</a> <a id="14824" class="Keyword">import</a> <a id="14831" href="foundation.propositional-extensionality.html" class="Module">foundation.propositional-extensionality</a>
<a id="14871" class="Keyword">open</a> <a id="14876" class="Keyword">import</a> <a id="14883" href="foundation.propositional-maps.html" class="Module">foundation.propositional-maps</a>
<a id="14913" class="Keyword">open</a> <a id="14918" class="Keyword">import</a> <a id="14925" href="foundation.propositional-truncations.html" class="Module">foundation.propositional-truncations</a>
<a id="14962" class="Keyword">open</a> <a id="14967" class="Keyword">import</a> <a id="14974" href="foundation.propositions.html" class="Module">foundation.propositions</a>
<a id="14998" class="Keyword">open</a> <a id="15003" class="Keyword">import</a> <a id="15010" href="foundation.pullbacks.html" class="Module">foundation.pullbacks</a>
<a id="15031" class="Keyword">open</a> <a id="15036" class="Keyword">import</a> <a id="15043" href="foundation.raising-universe-levels.html" class="Module">foundation.raising-universe-levels</a>
<a id="15078" class="Keyword">open</a> <a id="15083" class="Keyword">import</a> <a id="15090" href="foundation.ranks-of-elements-w-types.html" class="Module">foundation.ranks-of-elements-w-types</a>
<a id="15127" class="Keyword">open</a> <a id="15132" class="Keyword">import</a> <a id="15139" href="foundation.reflecting-maps-equivalence-relations.html" class="Module">foundation.reflecting-maps-equivalence-relations</a>
<a id="15188" class="Keyword">open</a> <a id="15193" class="Keyword">import</a> <a id="15200" href="foundation.replacement.html" class="Module">foundation.replacement</a>
<a id="15223" class="Keyword">open</a> <a id="15228" class="Keyword">import</a> <a id="15235" href="foundation.retractions.html" class="Module">foundation.retractions</a>
<a id="15258" class="Keyword">open</a> <a id="15263" class="Keyword">import</a> <a id="15270" href="foundation.russells-paradox.html" class="Module">foundation.russells-paradox</a>
<a id="15298" class="Keyword">open</a> <a id="15303" class="Keyword">import</a> <a id="15310" href="foundation.sections.html" class="Module">foundation.sections</a>
<a id="15330" class="Keyword">open</a> <a id="15335" class="Keyword">import</a> <a id="15342" href="foundation.set-presented-types.html" class="Module">foundation.set-presented-types</a>
<a id="15373" class="Keyword">open</a> <a id="15378" class="Keyword">import</a> <a id="15385" href="foundation.set-truncations.html" class="Module">foundation.set-truncations</a>
<a id="15412" class="Keyword">open</a> <a id="15417" class="Keyword">import</a> <a id="15424" href="foundation.sets.html" class="Module">foundation.sets</a>
<a id="15440" class="Keyword">open</a> <a id="15445" class="Keyword">import</a> <a id="15452" href="foundation.singleton-induction.html" class="Module">foundation.singleton-induction</a>
<a id="15483" class="Keyword">open</a> <a id="15488" class="Keyword">import</a> <a id="15495" href="foundation.slice.html" class="Module">foundation.slice</a>
<a id="15512" class="Keyword">open</a> <a id="15517" class="Keyword">import</a> <a id="15524" href="foundation.small-maps.html" class="Module">foundation.small-maps</a>
<a id="15546" class="Keyword">open</a> <a id="15551" class="Keyword">import</a> <a id="15558" href="foundation.small-multisets.html" class="Module">foundation.small-multisets</a>
<a id="15585" class="Keyword">open</a> <a id="15590" class="Keyword">import</a> <a id="15597" href="foundation.small-types.html" class="Module">foundation.small-types</a>
<a id="15620" class="Keyword">open</a> <a id="15625" class="Keyword">import</a> <a id="15632" href="foundation.small-universes.html" class="Module">foundation.small-universes</a>
<a id="15659" class="Keyword">open</a> <a id="15664" class="Keyword">import</a> <a id="15671" href="foundation.split-surjective-maps.html" class="Module">foundation.split-surjective-maps</a>
<a id="15704" class="Keyword">open</a> <a id="15709" class="Keyword">import</a> <a id="15716" href="foundation.structure-identity-principle.html" class="Module">foundation.structure-identity-principle</a>
<a id="15756" class="Keyword">open</a> <a id="15761" class="Keyword">import</a> <a id="15768" href="foundation.structure.html" class="Module">foundation.structure</a>
<a id="15789" class="Keyword">open</a> <a id="15794" class="Keyword">import</a> <a id="15801" href="foundation.subterminal-types.html" class="Module">foundation.subterminal-types</a>
<a id="15830" class="Keyword">open</a> <a id="15835" class="Keyword">import</a> <a id="15842" href="foundation.subtype-identity-principle.html" class="Module">foundation.subtype-identity-principle</a>
<a id="15880" class="Keyword">open</a> <a id="15885" class="Keyword">import</a> <a id="15892" href="foundation.subtypes.html" class="Module">foundation.subtypes</a>
<a id="15912" class="Keyword">open</a> <a id="15917" class="Keyword">import</a> <a id="15924" href="foundation.subuniverses.html" class="Module">foundation.subuniverses</a>
<a id="15948" class="Keyword">open</a> <a id="15953" class="Keyword">import</a> <a id="15960" href="foundation.surjective-maps.html" class="Module">foundation.surjective-maps</a>
<a id="15987" class="Keyword">open</a> <a id="15992" class="Keyword">import</a> <a id="15999" href="foundation.symmetric-difference.html" class="Module">foundation.symmetric-difference</a>
<a id="16031" class="Keyword">open</a> <a id="16036" class="Keyword">import</a> <a id="16043" href="foundation.truncated-equality.html" class="Module">foundation.truncated-equality</a>
<a id="16073" class="Keyword">open</a> <a id="16078" class="Keyword">import</a> <a id="16085" href="foundation.truncated-maps.html" class="Module">foundation.truncated-maps</a>
<a id="16111" class="Keyword">open</a> <a id="16116" class="Keyword">import</a> <a id="16123" href="foundation.truncated-types.html" class="Module">foundation.truncated-types</a>
<a id="16150" class="Keyword">open</a> <a id="16155" class="Keyword">import</a> <a id="16162" href="foundation.truncation-levels.html" class="Module">foundation.truncation-levels</a>
<a id="16191" class="Keyword">open</a> <a id="16196" class="Keyword">import</a> <a id="16203" href="foundation.truncations.html" class="Module">foundation.truncations</a>
<a id="16226" class="Keyword">open</a> <a id="16231" class="Keyword">import</a> <a id="16238" href="foundation.type-arithmetic-cartesian-product-types.html" class="Module">foundation.type-arithmetic-cartesian-product-types</a>
<a id="16289" class="Keyword">open</a> <a id="16294" class="Keyword">import</a> <a id="16301" href="foundation.type-arithmetic-coproduct-types.html" class="Module">foundation.type-arithmetic-coproduct-types</a>
<a id="16344" class="Keyword">open</a> <a id="16349" class="Keyword">import</a> <a id="16356" href="foundation.type-arithmetic-dependent-pair-types.html" class="Module">foundation.type-arithmetic-dependent-pair-types</a>
<a id="16404" class="Keyword">open</a> <a id="16409" class="Keyword">import</a> <a id="16416" href="foundation.type-arithmetic-empty-type.html" class="Module">foundation.type-arithmetic-empty-type</a>
<a id="16454" class="Keyword">open</a> <a id="16459" class="Keyword">import</a> <a id="16466" href="foundation.type-arithmetic-unit-type.html" class="Module">foundation.type-arithmetic-unit-type</a>
<a id="16503" class="Keyword">open</a> <a id="16508" class="Keyword">import</a> <a id="16515" href="foundation.uniqueness-image.html" class="Module">foundation.uniqueness-image</a>
<a id="16543" class="Keyword">open</a> <a id="16548" class="Keyword">import</a> <a id="16555" href="foundation.uniqueness-set-quotients.html" class="Module">foundation.uniqueness-set-quotients</a>
<a id="16591" class="Keyword">open</a> <a id="16596" class="Keyword">import</a> <a id="16603" href="foundation.uniqueness-set-truncations.html" class="Module">foundation.uniqueness-set-truncations</a>
<a id="16641" class="Keyword">open</a> <a id="16646" class="Keyword">import</a> <a id="16653" href="foundation.uniqueness-truncation.html" class="Module">foundation.uniqueness-truncation</a>
<a id="16686" class="Keyword">open</a> <a id="16691" class="Keyword">import</a> <a id="16698" href="foundation.unit-type.html" class="Module">foundation.unit-type</a>
<a id="16719" class="Keyword">open</a> <a id="16724" class="Keyword">import</a> <a id="16731" href="foundation.univalence-implies-function-extensionality.html" class="Module">foundation.univalence-implies-function-extensionality</a>
<a id="16785" class="Keyword">open</a> <a id="16790" class="Keyword">import</a> <a id="16797" href="foundation.univalence.html" class="Module">foundation.univalence</a>
<a id="16819" class="Keyword">open</a> <a id="16824" class="Keyword">import</a> <a id="16831" href="foundation.univalent-type-families.html" class="Module">foundation.univalent-type-families</a>
<a id="16866" class="Keyword">open</a> <a id="16871" class="Keyword">import</a> <a id="16878" href="foundation.universal-multiset.html" class="Module">foundation.universal-multiset</a>
<a id="16908" class="Keyword">open</a> <a id="16913" class="Keyword">import</a> <a id="16920" href="foundation.universal-property-booleans.html" class="Module">foundation.universal-property-booleans</a>
<a id="16959" class="Keyword">open</a> <a id="16964" class="Keyword">import</a> <a id="16971" href="foundation.universal-property-cartesian-product-types.html" class="Module">foundation.universal-property-cartesian-product-types</a>
<a id="17025" class="Keyword">open</a> <a id="17030" class="Keyword">import</a> <a id="17037" href="foundation.universal-property-coproduct-types.html" class="Module">foundation.universal-property-coproduct-types</a>
<a id="17083" class="Keyword">open</a> <a id="17088" class="Keyword">import</a> <a id="17095" href="foundation.universal-property-dependent-pair-types.html" class="Module">foundation.universal-property-dependent-pair-types</a>
<a id="17146" class="Keyword">open</a> <a id="17151" class="Keyword">import</a> <a id="17158" href="foundation.universal-property-empty-type.html" class="Module">foundation.universal-property-empty-type</a>
<a id="17199" class="Keyword">open</a> <a id="17204" class="Keyword">import</a> <a id="17211" href="foundation.universal-property-fiber-products.html" class="Module">foundation.universal-property-fiber-products</a>
<a id="17256" class="Keyword">open</a> <a id="17261" class="Keyword">import</a> <a id="17268" href="foundation.universal-property-identity-types.html" class="Module">foundation.universal-property-identity-types</a>
<a id="17313" class="Keyword">open</a> <a id="17318" class="Keyword">import</a> <a id="17325" href="foundation.universal-property-image.html" class="Module">foundation.universal-property-image</a>
<a id="17361" class="Keyword">open</a> <a id="17366" class="Keyword">import</a> <a id="17373" href="foundation.universal-property-maybe.html" class="Module">foundation.universal-property-maybe</a>
<a id="17409" class="Keyword">open</a> <a id="17414" class="Keyword">import</a> <a id="17421" href="foundation.universal-property-propositional-truncation-into-sets.html" class="Module">foundation.universal-property-propositional-truncation-into-sets</a>
<a id="17486" class="Keyword">open</a> <a id="17491" class="Keyword">import</a> <a id="17498" href="foundation.universal-property-propositional-truncation.html" class="Module">foundation.universal-property-propositional-truncation</a>
<a id="17553" class="Keyword">open</a> <a id="17558" class="Keyword">import</a> <a id="17565" href="foundation.universal-property-pullbacks.html" class="Module">foundation.universal-property-pullbacks</a>
<a id="17605" class="Keyword">open</a> <a id="17610" class="Keyword">import</a> <a id="17617" href="foundation.universal-property-set-quotients.html" class="Module">foundation.universal-property-set-quotients</a>
<a id="17661" class="Keyword">open</a> <a id="17666" class="Keyword">import</a> <a id="17673" href="foundation.universal-property-set-truncation.html" class="Module">foundation.universal-property-set-truncation</a>
<a id="17718" class="Keyword">open</a> <a id="17723" class="Keyword">import</a> <a id="17730" href="foundation.universal-property-truncation.html" class="Module">foundation.universal-property-truncation</a>
<a id="17771" class="Keyword">open</a> <a id="17776" class="Keyword">import</a> <a id="17783" href="foundation.universal-property-unit-type.html" class="Module">foundation.universal-property-unit-type</a>
<a id="17823" class="Keyword">open</a> <a id="17828" class="Keyword">import</a> <a id="17835" href="foundation.universe-levels.html" class="Module">foundation.universe-levels</a>
<a id="17862" class="Keyword">open</a> <a id="17867" class="Keyword">import</a> <a id="17874" href="foundation.unordered-pairs.html" class="Module">foundation.unordered-pairs</a>
<a id="17901" class="Keyword">open</a> <a id="17906" class="Keyword">import</a> <a id="17913" href="foundation.w-types.html" class="Module">foundation.w-types</a>
<a id="17932" class="Keyword">open</a> <a id="17937" class="Keyword">import</a> <a id="17944" href="foundation.weak-function-extensionality.html" class="Module">foundation.weak-function-extensionality</a>
<a id="17984" class="Keyword">open</a> <a id="17989" class="Keyword">import</a> <a id="17996" href="foundation.weakly-constant-maps.html" class="Module">foundation.weakly-constant-maps</a>
<a id="18028" class="Keyword">open</a> <a id="18033" class="Keyword">import</a> <a id="18040" href="foundation.xor.html" class="Module">foundation.xor</a>
</pre>
## Foundation Core

<pre class="Agda"><a id="18088" class="Keyword">open</a> <a id="18093" class="Keyword">import</a> <a id="18100" href="foundation-core.0-maps.html" class="Module">foundation-core.0-maps</a>
<a id="18123" class="Keyword">open</a> <a id="18128" class="Keyword">import</a> <a id="18135" href="foundation-core.1-types.html" class="Module">foundation-core.1-types</a>
<a id="18159" class="Keyword">open</a> <a id="18164" class="Keyword">import</a> <a id="18171" href="foundation-core.cartesian-product-types.html" class="Module">foundation-core.cartesian-product-types</a>
<a id="18211" class="Keyword">open</a> <a id="18216" class="Keyword">import</a> <a id="18223" href="foundation-core.coherently-invertible-maps.html" class="Module">foundation-core.coherently-invertible-maps</a>
<a id="18266" class="Keyword">open</a> <a id="18271" class="Keyword">import</a> <a id="18278" href="foundation-core.commuting-squares.html" class="Module">foundation-core.commuting-squares</a>
<a id="18312" class="Keyword">open</a> <a id="18317" class="Keyword">import</a> <a id="18324" href="foundation-core.constant-maps.html" class="Module">foundation-core.constant-maps</a>
<a id="18354" class="Keyword">open</a> <a id="18359" class="Keyword">import</a> <a id="18366" href="foundation-core.contractible-maps.html" class="Module">foundation-core.contractible-maps</a>
<a id="18400" class="Keyword">open</a> <a id="18405" class="Keyword">import</a> <a id="18412" href="foundation-core.contractible-types.html" class="Module">foundation-core.contractible-types</a>
<a id="18447" class="Keyword">open</a> <a id="18452" class="Keyword">import</a> <a id="18459" href="foundation-core.dependent-pair-types.html" class="Module">foundation-core.dependent-pair-types</a>
<a id="18496" class="Keyword">open</a> <a id="18501" class="Keyword">import</a> <a id="18508" href="foundation-core.embeddings.html" class="Module">foundation-core.embeddings</a>
<a id="18535" class="Keyword">open</a> <a id="18540" class="Keyword">import</a> <a id="18547" href="foundation-core.empty-types.html" class="Module">foundation-core.empty-types</a>
<a id="18575" class="Keyword">open</a> <a id="18580" class="Keyword">import</a> <a id="18587" href="foundation-core.equality-cartesian-product-types.html" class="Module">foundation-core.equality-cartesian-product-types</a>
<a id="18636" class="Keyword">open</a> <a id="18641" class="Keyword">import</a> <a id="18648" href="foundation-core.equality-dependent-pair-types.html" class="Module">foundation-core.equality-dependent-pair-types</a>
<a id="18694" class="Keyword">open</a> <a id="18699" class="Keyword">import</a> <a id="18706" href="foundation-core.equality-fibers-of-maps.html" class="Module">foundation-core.equality-fibers-of-maps</a>
<a id="18746" class="Keyword">open</a> <a id="18751" class="Keyword">import</a> <a id="18758" href="foundation-core.equivalence-induction.html" class="Module">foundation-core.equivalence-induction</a>
<a id="18796" class="Keyword">open</a> <a id="18801" class="Keyword">import</a> <a id="18808" href="foundation-core.equivalences.html" class="Module">foundation-core.equivalences</a>
<a id="18837" class="Keyword">open</a> <a id="18842" class="Keyword">import</a> <a id="18849" href="foundation-core.faithful-maps.html" class="Module">foundation-core.faithful-maps</a>
<a id="18879" class="Keyword">open</a> <a id="18884" class="Keyword">import</a> <a id="18891" href="foundation-core.fibers-of-maps.html" class="Module">foundation-core.fibers-of-maps</a>
<a id="18922" class="Keyword">open</a> <a id="18927" class="Keyword">import</a> <a id="18934" href="foundation-core.functions.html" class="Module">foundation-core.functions</a>
<a id="18960" class="Keyword">open</a> <a id="18965" class="Keyword">import</a> <a id="18972" href="foundation-core.functoriality-dependent-pair-types.html" class="Module">foundation-core.functoriality-dependent-pair-types</a>
<a id="19023" class="Keyword">open</a> <a id="19028" class="Keyword">import</a> <a id="19035" href="foundation-core.fundamental-theorem-of-identity-types.html" class="Module">foundation-core.fundamental-theorem-of-identity-types</a>
<a id="19089" class="Keyword">open</a> <a id="19094" class="Keyword">import</a> <a id="19101" href="foundation-core.homotopies.html" class="Module">foundation-core.homotopies</a>
<a id="19128" class="Keyword">open</a> <a id="19133" class="Keyword">import</a> <a id="19140" href="foundation-core.identity-systems.html" class="Module">foundation-core.identity-systems</a>
<a id="19173" class="Keyword">open</a> <a id="19178" class="Keyword">import</a> <a id="19185" href="foundation-core.identity-types.html" class="Module">foundation-core.identity-types</a>
<a id="19216" class="Keyword">open</a> <a id="19221" class="Keyword">import</a> <a id="19228" href="foundation-core.logical-equivalences.html" class="Module">foundation-core.logical-equivalences</a>
<a id="19265" class="Keyword">open</a> <a id="19270" class="Keyword">import</a> <a id="19277" href="foundation-core.negation.html" class="Module">foundation-core.negation</a>
<a id="19302" class="Keyword">open</a> <a id="19307" class="Keyword">import</a> <a id="19314" href="foundation-core.path-split-maps.html" class="Module">foundation-core.path-split-maps</a>
<a id="19346" class="Keyword">open</a> <a id="19351" class="Keyword">import</a> <a id="19358" href="foundation-core.propositional-maps.html" class="Module">foundation-core.propositional-maps</a>
<a id="19393" class="Keyword">open</a> <a id="19398" class="Keyword">import</a> <a id="19405" href="foundation-core.propositions.html" class="Module">foundation-core.propositions</a>
<a id="19434" class="Keyword">open</a> <a id="19439" class="Keyword">import</a> <a id="19446" href="foundation-core.retractions.html" class="Module">foundation-core.retractions</a>
<a id="19474" class="Keyword">open</a> <a id="19479" class="Keyword">import</a> <a id="19486" href="foundation-core.sections.html" class="Module">foundation-core.sections</a>
<a id="19511" class="Keyword">open</a> <a id="19516" class="Keyword">import</a> <a id="19523" href="foundation-core.sets.html" class="Module">foundation-core.sets</a>
<a id="19544" class="Keyword">open</a> <a id="19549" class="Keyword">import</a> <a id="19556" href="foundation-core.singleton-induction.html" class="Module">foundation-core.singleton-induction</a>
<a id="19592" class="Keyword">open</a> <a id="19597" class="Keyword">import</a> <a id="19604" href="foundation-core.subtype-identity-principle.html" class="Module">foundation-core.subtype-identity-principle</a>
<a id="19647" class="Keyword">open</a> <a id="19652" class="Keyword">import</a> <a id="19659" href="foundation-core.subtypes.html" class="Module">foundation-core.subtypes</a>
<a id="19684" class="Keyword">open</a> <a id="19689" class="Keyword">import</a> <a id="19696" href="foundation-core.truncated-maps.html" class="Module">foundation-core.truncated-maps</a>
<a id="19727" class="Keyword">open</a> <a id="19732" class="Keyword">import</a> <a id="19739" href="foundation-core.truncated-types.html" class="Module">foundation-core.truncated-types</a>
<a id="19771" class="Keyword">open</a> <a id="19776" class="Keyword">import</a> <a id="19783" href="foundation-core.truncation-levels.html" class="Module">foundation-core.truncation-levels</a>
<a id="19817" class="Keyword">open</a> <a id="19822" class="Keyword">import</a> <a id="19829" href="foundation-core.type-arithmetic-cartesian-product-types.html" class="Module">foundation-core.type-arithmetic-cartesian-product-types</a>
<a id="19885" class="Keyword">open</a> <a id="19890" class="Keyword">import</a> <a id="19897" href="foundation-core.type-arithmetic-dependent-pair-types.html" class="Module">foundation-core.type-arithmetic-dependent-pair-types</a>
<a id="19950" class="Keyword">open</a> <a id="19955" class="Keyword">import</a> <a id="19962" href="foundation-core.univalence.html" class="Module">foundation-core.univalence</a>
<a id="19989" class="Keyword">open</a> <a id="19994" class="Keyword">import</a> <a id="20001" href="foundation-core.universe-levels.html" class="Module">foundation-core.universe-levels</a>
</pre>
## Graph theory

<pre class="Agda"><a id="20063" class="Keyword">open</a> <a id="20068" class="Keyword">import</a> <a id="20075" href="graph-theory.html" class="Module">graph-theory</a>
<a id="20088" class="Keyword">open</a> <a id="20093" class="Keyword">import</a> <a id="20100" href="graph-theory.connected-undirected-graphs.html" class="Module">graph-theory.connected-undirected-graphs</a>
<a id="20141" class="Keyword">open</a> <a id="20146" class="Keyword">import</a> <a id="20153" href="graph-theory.directed-graphs.html" class="Module">graph-theory.directed-graphs</a>
<a id="20182" class="Keyword">open</a> <a id="20187" class="Keyword">import</a> <a id="20194" href="graph-theory.edge-coloured-undirected-graphs.html" class="Module">graph-theory.edge-coloured-undirected-graphs</a>
<a id="20239" class="Keyword">open</a> <a id="20244" class="Keyword">import</a> <a id="20251" href="graph-theory.equivalences-undirected-graphs.html" class="Module">graph-theory.equivalences-undirected-graphs</a>
<a id="20295" class="Keyword">open</a> <a id="20300" class="Keyword">import</a> <a id="20307" href="graph-theory.finite-graphs.html" class="Module">graph-theory.finite-graphs</a>
<a id="20334" class="Keyword">open</a> <a id="20339" class="Keyword">import</a> <a id="20346" href="graph-theory.incidence-undirected-graphs.html" class="Module">graph-theory.incidence-undirected-graphs</a>
<a id="20387" class="Keyword">open</a> <a id="20392" class="Keyword">import</a> <a id="20399" href="graph-theory.matchings.html" class="Module">graph-theory.matchings</a>
<a id="20422" class="Keyword">open</a> <a id="20427" class="Keyword">import</a> <a id="20434" href="graph-theory.mere-equivalences-undirected-graphs.html" class="Module">graph-theory.mere-equivalences-undirected-graphs</a>
<a id="20483" class="Keyword">open</a> <a id="20488" class="Keyword">import</a> <a id="20495" href="graph-theory.morphisms-directed-graphs.html" class="Module">graph-theory.morphisms-directed-graphs</a>
<a id="20534" class="Keyword">open</a> <a id="20539" class="Keyword">import</a> <a id="20546" href="graph-theory.morphisms-undirected-graphs.html" class="Module">graph-theory.morphisms-undirected-graphs</a>
<a id="20587" class="Keyword">open</a> <a id="20592" class="Keyword">import</a> <a id="20599" href="graph-theory.orientations-undirected-graphs.html" class="Module">graph-theory.orientations-undirected-graphs</a>
<a id="20643" class="Keyword">open</a> <a id="20648" class="Keyword">import</a> <a id="20655" href="graph-theory.paths-undirected-graphs.html" class="Module">graph-theory.paths-undirected-graphs</a>
<a id="20692" class="Keyword">open</a> <a id="20697" class="Keyword">import</a> <a id="20704" href="graph-theory.polygons.html" class="Module">graph-theory.polygons</a>
<a id="20726" class="Keyword">open</a> <a id="20731" class="Keyword">import</a> <a id="20738" href="graph-theory.reflexive-graphs.html" class="Module">graph-theory.reflexive-graphs</a>
<a id="20768" class="Keyword">open</a> <a id="20773" class="Keyword">import</a> <a id="20780" href="graph-theory.regular-undirected-graphs.html" class="Module">graph-theory.regular-undirected-graphs</a>
<a id="20819" class="Keyword">open</a> <a id="20824" class="Keyword">import</a> <a id="20831" href="graph-theory.simple-undirected-graphs.html" class="Module">graph-theory.simple-undirected-graphs</a>
<a id="20869" class="Keyword">open</a> <a id="20874" class="Keyword">import</a> <a id="20881" href="graph-theory.undirected-graphs.html" class="Module">graph-theory.undirected-graphs</a>
<a id="20912" class="Keyword">open</a> <a id="20917" class="Keyword">import</a> <a id="20924" href="graph-theory.voltage-graphs.html" class="Module">graph-theory.voltage-graphs</a>
</pre>
## Group theory

<pre class="Agda"><a id="20982" class="Keyword">open</a> <a id="20987" class="Keyword">import</a> <a id="20994" href="group-theory.html" class="Module">group-theory</a>
<a id="21007" class="Keyword">open</a> <a id="21012" class="Keyword">import</a> <a id="21019" href="group-theory.abelian-groups.html" class="Module">group-theory.abelian-groups</a>
<a id="21047" class="Keyword">open</a> <a id="21052" class="Keyword">import</a> <a id="21059" href="group-theory.abelian-subgroups.html" class="Module">group-theory.abelian-subgroups</a>
<a id="21090" class="Keyword">open</a> <a id="21095" class="Keyword">import</a> <a id="21102" href="group-theory.abstract-group-torsors.html" class="Module">group-theory.abstract-group-torsors</a>
<a id="21138" class="Keyword">open</a> <a id="21143" class="Keyword">import</a> <a id="21150" href="group-theory.addition-homomorphisms-abelian-groups.html" class="Module">group-theory.addition-homomorphisms-abelian-groups</a>
<a id="21201" class="Keyword">open</a> <a id="21206" class="Keyword">import</a> <a id="21213" href="group-theory.automorphism-groups.html" class="Module">group-theory.automorphism-groups</a>
<a id="21246" class="Keyword">open</a> <a id="21251" class="Keyword">import</a> <a id="21258" href="group-theory.category-of-groups.html" class="Module">group-theory.category-of-groups</a>
<a id="21290" class="Keyword">open</a> <a id="21295" class="Keyword">import</a> <a id="21302" href="group-theory.category-of-semigroups.html" class="Module">group-theory.category-of-semigroups</a>
<a id="21338" class="Keyword">open</a> <a id="21343" class="Keyword">import</a> <a id="21350" href="group-theory.cayleys-theorem.html" class="Module">group-theory.cayleys-theorem</a>
<a id="21379" class="Keyword">open</a> <a id="21384" class="Keyword">import</a> <a id="21391" href="group-theory.concrete-group-actions.html" class="Module">group-theory.concrete-group-actions</a>
<a id="21427" class="Keyword">open</a> <a id="21432" class="Keyword">import</a> <a id="21439" href="group-theory.concrete-groups.html" class="Module">group-theory.concrete-groups</a>
<a id="21468" class="Keyword">open</a> <a id="21473" class="Keyword">import</a> <a id="21480" href="group-theory.concrete-subgroups.html" class="Module">group-theory.concrete-subgroups</a>
<a id="21512" class="Keyword">open</a> <a id="21517" class="Keyword">import</a> <a id="21524" href="group-theory.conjugation.html" class="Module">group-theory.conjugation</a>
<a id="21549" class="Keyword">open</a> <a id="21554" class="Keyword">import</a> <a id="21561" href="group-theory.embeddings-groups.html" class="Module">group-theory.embeddings-groups</a>
<a id="21592" class="Keyword">open</a> <a id="21597" class="Keyword">import</a> <a id="21604" href="group-theory.endomorphism-rings-abelian-groups.html" class="Module">group-theory.endomorphism-rings-abelian-groups</a>
<a id="21651" class="Keyword">open</a> <a id="21656" class="Keyword">import</a> <a id="21663" href="group-theory.equivalences-group-actions.html" class="Module">group-theory.equivalences-group-actions</a>
<a id="21703" class="Keyword">open</a> <a id="21708" class="Keyword">import</a> <a id="21715" href="group-theory.equivalences-semigroups.html" class="Module">group-theory.equivalences-semigroups</a>
<a id="21752" class="Keyword">open</a> <a id="21757" class="Keyword">import</a> <a id="21764" href="group-theory.examples-higher-groups.html" class="Module">group-theory.examples-higher-groups</a>
<a id="21800" class="Keyword">open</a> <a id="21805" class="Keyword">import</a> <a id="21812" href="group-theory.furstenberg-groups.html" class="Module">group-theory.furstenberg-groups</a>
<a id="21844" class="Keyword">open</a> <a id="21849" class="Keyword">import</a> <a id="21856" href="group-theory.group-actions.html" class="Module">group-theory.group-actions</a>
<a id="21883" class="Keyword">open</a> <a id="21888" class="Keyword">import</a> <a id="21895" href="group-theory.groups.html" class="Module">group-theory.groups</a>
<a id="21915" class="Keyword">open</a> <a id="21920" class="Keyword">import</a> <a id="21927" href="group-theory.higher-groups.html" class="Module">group-theory.higher-groups</a>
<a id="21954" class="Keyword">open</a> <a id="21959" class="Keyword">import</a> <a id="21966" href="group-theory.homomorphisms-abelian-groups.html" class="Module">group-theory.homomorphisms-abelian-groups</a>
<a id="22008" class="Keyword">open</a> <a id="22013" class="Keyword">import</a> <a id="22020" href="group-theory.homomorphisms-group-actions.html" class="Module">group-theory.homomorphisms-group-actions</a>
<a id="22061" class="Keyword">open</a> <a id="22066" class="Keyword">import</a> <a id="22073" href="group-theory.homomorphisms-groups.html" class="Module">group-theory.homomorphisms-groups</a>
<a id="22107" class="Keyword">open</a> <a id="22112" class="Keyword">import</a> <a id="22119" href="group-theory.homomorphisms-monoids.html" class="Module">group-theory.homomorphisms-monoids</a>
<a id="22154" class="Keyword">open</a> <a id="22159" class="Keyword">import</a> <a id="22166" href="group-theory.homomorphisms-semigroups.html" class="Module">group-theory.homomorphisms-semigroups</a>
<a id="22204" class="Keyword">open</a> <a id="22209" class="Keyword">import</a> <a id="22216" href="group-theory.inverse-semigroups.html" class="Module">group-theory.inverse-semigroups</a>
<a id="22248" class="Keyword">open</a> <a id="22253" class="Keyword">import</a> <a id="22260" href="group-theory.invertible-elements-monoids.html" class="Module">group-theory.invertible-elements-monoids</a>
<a id="22301" class="Keyword">open</a> <a id="22306" class="Keyword">import</a> <a id="22313" href="group-theory.isomorphisms-abelian-groups.html" class="Module">group-theory.isomorphisms-abelian-groups</a>
<a id="22354" class="Keyword">open</a> <a id="22359" class="Keyword">import</a> <a id="22366" href="group-theory.isomorphisms-group-actions.html" class="Module">group-theory.isomorphisms-group-actions</a>
<a id="22406" class="Keyword">open</a> <a id="22411" class="Keyword">import</a> <a id="22418" href="group-theory.isomorphisms-groups.html" class="Module">group-theory.isomorphisms-groups</a>
<a id="22451" class="Keyword">open</a> <a id="22456" class="Keyword">import</a> <a id="22463" href="group-theory.isomorphisms-semigroups.html" class="Module">group-theory.isomorphisms-semigroups</a>
<a id="22500" class="Keyword">open</a> <a id="22505" class="Keyword">import</a> <a id="22512" href="group-theory.mere-equivalences-group-actions.html" class="Module">group-theory.mere-equivalences-group-actions</a>
<a id="22557" class="Keyword">open</a> <a id="22562" class="Keyword">import</a> <a id="22569" href="group-theory.monoids.html" class="Module">group-theory.monoids</a>
<a id="22590" class="Keyword">open</a> <a id="22595" class="Keyword">import</a> <a id="22602" href="group-theory.orbits-group-actions.html" class="Module">group-theory.orbits-group-actions</a>
<a id="22636" class="Keyword">open</a> <a id="22641" class="Keyword">import</a> <a id="22648" href="group-theory.precategory-of-group-actions.html" class="Module">group-theory.precategory-of-group-actions</a>
<a id="22690" class="Keyword">open</a> <a id="22695" class="Keyword">import</a> <a id="22702" href="group-theory.precategory-of-groups.html" class="Module">group-theory.precategory-of-groups</a>
<a id="22737" class="Keyword">open</a> <a id="22742" class="Keyword">import</a> <a id="22749" href="group-theory.precategory-of-semigroups.html" class="Module">group-theory.precategory-of-semigroups</a>
<a id="22788" class="Keyword">open</a> <a id="22793" class="Keyword">import</a> <a id="22800" href="group-theory.principal-group-actions.html" class="Module">group-theory.principal-group-actions</a>
<a id="22837" class="Keyword">open</a> <a id="22842" class="Keyword">import</a> <a id="22849" href="group-theory.semigroups.html" class="Module">group-theory.semigroups</a>
<a id="22873" class="Keyword">open</a> <a id="22878" class="Keyword">import</a> <a id="22885" href="group-theory.sheargroups.html" class="Module">group-theory.sheargroups</a>
<a id="22910" class="Keyword">open</a> <a id="22915" class="Keyword">import</a> <a id="22922" href="group-theory.stabilizer-groups.html" class="Module">group-theory.stabilizer-groups</a>
<a id="22953" class="Keyword">open</a> <a id="22958" class="Keyword">import</a> <a id="22965" href="group-theory.subgroups.html" class="Module">group-theory.subgroups</a>
<a id="22988" class="Keyword">open</a> <a id="22993" class="Keyword">import</a> <a id="23000" href="group-theory.substitution-functor-group-actions.html" class="Module">group-theory.substitution-functor-group-actions</a>
<a id="23048" class="Keyword">open</a> <a id="23053" class="Keyword">import</a> <a id="23060" href="group-theory.symmetric-groups.html" class="Module">group-theory.symmetric-groups</a>
<a id="23090" class="Keyword">open</a> <a id="23095" class="Keyword">import</a> <a id="23102" href="group-theory.transitive-group-actions.html" class="Module">group-theory.transitive-group-actions</a>
</pre>
## Linear algebra

<pre class="Agda"><a id="23172" class="Keyword">open</a> <a id="23177" class="Keyword">import</a> <a id="23184" href="linear-algebra.html" class="Module">linear-algebra</a>
<a id="23199" class="Keyword">open</a> <a id="23204" class="Keyword">import</a> <a id="23211" href="linear-algebra.constant-matrices.html" class="Module">linear-algebra.constant-matrices</a>
<a id="23244" class="Keyword">open</a> <a id="23249" class="Keyword">import</a> <a id="23256" href="linear-algebra.constant-vectors.html" class="Module">linear-algebra.constant-vectors</a>
<a id="23288" class="Keyword">open</a> <a id="23293" class="Keyword">import</a> <a id="23300" href="linear-algebra.diagonal-matrices-on-rings.html" class="Module">linear-algebra.diagonal-matrices-on-rings</a>
<a id="23342" class="Keyword">open</a> <a id="23347" class="Keyword">import</a> <a id="23354" href="linear-algebra.functoriality-matrices.html" class="Module">linear-algebra.functoriality-matrices</a>
<a id="23392" class="Keyword">open</a> <a id="23397" class="Keyword">import</a> <a id="23404" href="linear-algebra.functoriality-vectors.html" class="Module">linear-algebra.functoriality-vectors</a>
<a id="23441" class="Keyword">open</a> <a id="23446" class="Keyword">import</a> <a id="23453" href="linear-algebra.matrices-on-rings.html" class="Module">linear-algebra.matrices-on-rings</a>
<a id="23486" class="Keyword">open</a> <a id="23491" class="Keyword">import</a> <a id="23498" href="linear-algebra.matrices.html" class="Module">linear-algebra.matrices</a>
<a id="23522" class="Keyword">open</a> <a id="23527" class="Keyword">import</a> <a id="23534" href="linear-algebra.multiplication-matrices.html" class="Module">linear-algebra.multiplication-matrices</a>
<a id="23573" class="Keyword">open</a> <a id="23578" class="Keyword">import</a> <a id="23585" href="linear-algebra.scalar-multiplication-matrices.html" class="Module">linear-algebra.scalar-multiplication-matrices</a>
<a id="23631" class="Keyword">open</a> <a id="23636" class="Keyword">import</a> <a id="23643" href="linear-algebra.scalar-multiplication-vectors.html" class="Module">linear-algebra.scalar-multiplication-vectors</a>
<a id="23688" class="Keyword">open</a> <a id="23693" class="Keyword">import</a> <a id="23700" href="linear-algebra.transposition-matrices.html" class="Module">linear-algebra.transposition-matrices</a>
<a id="23738" class="Keyword">open</a> <a id="23743" class="Keyword">import</a> <a id="23750" href="linear-algebra.vectors-on-rings.html" class="Module">linear-algebra.vectors-on-rings</a>
<a id="23782" class="Keyword">open</a> <a id="23787" class="Keyword">import</a> <a id="23794" href="linear-algebra.vectors.html" class="Module">linear-algebra.vectors</a>
</pre>
## Order theory

<pre class="Agda"><a id="23847" class="Keyword">open</a> <a id="23852" class="Keyword">import</a> <a id="23859" href="order-theory.html" class="Module">order-theory</a>
<a id="23872" class="Keyword">open</a> <a id="23877" class="Keyword">import</a> <a id="23884" href="order-theory.chains-posets.html" class="Module">order-theory.chains-posets</a>
<a id="23911" class="Keyword">open</a> <a id="23916" class="Keyword">import</a> <a id="23923" href="order-theory.chains-preorders.html" class="Module">order-theory.chains-preorders</a>
<a id="23953" class="Keyword">open</a> <a id="23958" class="Keyword">import</a> <a id="23965" href="order-theory.decidable-subposets.html" class="Module">order-theory.decidable-subposets</a>
<a id="23998" class="Keyword">open</a> <a id="24003" class="Keyword">import</a> <a id="24010" href="order-theory.decidable-subpreorders.html" class="Module">order-theory.decidable-subpreorders</a>
<a id="24046" class="Keyword">open</a> <a id="24051" class="Keyword">import</a> <a id="24058" href="order-theory.finite-posets.html" class="Module">order-theory.finite-posets</a>
<a id="24085" class="Keyword">open</a> <a id="24090" class="Keyword">import</a> <a id="24097" href="order-theory.finite-preorders.html" class="Module">order-theory.finite-preorders</a>
<a id="24127" class="Keyword">open</a> <a id="24132" class="Keyword">import</a> <a id="24139" href="order-theory.finitely-graded-posets.html" class="Module">order-theory.finitely-graded-posets</a>
<a id="24175" class="Keyword">open</a> <a id="24180" class="Keyword">import</a> <a id="24187" href="order-theory.greatest-lower-bounds-posets.html" class="Module">order-theory.greatest-lower-bounds-posets</a>
<a id="24229" class="Keyword">open</a> <a id="24234" class="Keyword">import</a> <a id="24241" href="order-theory.interval-subposets.html" class="Module">order-theory.interval-subposets</a>
<a id="24273" class="Keyword">open</a> <a id="24278" class="Keyword">import</a> <a id="24285" href="order-theory.large-posets.html" class="Module">order-theory.large-posets</a>
<a id="24311" class="Keyword">open</a> <a id="24316" class="Keyword">import</a> <a id="24323" href="order-theory.large-preorders.html" class="Module">order-theory.large-preorders</a>
<a id="24352" class="Keyword">open</a> <a id="24357" class="Keyword">import</a> <a id="24364" href="order-theory.largest-elements-posets.html" class="Module">order-theory.largest-elements-posets</a>
<a id="24401" class="Keyword">open</a> <a id="24406" class="Keyword">import</a> <a id="24413" href="order-theory.largest-elements-preorders.html" class="Module">order-theory.largest-elements-preorders</a>
<a id="24453" class="Keyword">open</a> <a id="24458" class="Keyword">import</a> <a id="24465" href="order-theory.least-elements-posets.html" class="Module">order-theory.least-elements-posets</a>
<a id="24500" class="Keyword">open</a> <a id="24505" class="Keyword">import</a> <a id="24512" href="order-theory.least-elements-preorders.html" class="Module">order-theory.least-elements-preorders</a>
<a id="24550" class="Keyword">open</a> <a id="24555" class="Keyword">import</a> <a id="24562" href="order-theory.locally-finite-posets.html" class="Module">order-theory.locally-finite-posets</a>
<a id="24597" class="Keyword">open</a> <a id="24602" class="Keyword">import</a> <a id="24609" href="order-theory.maximal-chains-posets.html" class="Module">order-theory.maximal-chains-posets</a>
<a id="24644" class="Keyword">open</a> <a id="24649" class="Keyword">import</a> <a id="24656" href="order-theory.maximal-chains-preorders.html" class="Module">order-theory.maximal-chains-preorders</a>
<a id="24694" class="Keyword">open</a> <a id="24699" class="Keyword">import</a> <a id="24706" href="order-theory.meet-semilattices.html" class="Module">order-theory.meet-semilattices</a>
<a id="24737" class="Keyword">open</a> <a id="24742" class="Keyword">import</a> <a id="24749" href="order-theory.planar-binary-trees.html" class="Module">order-theory.planar-binary-trees</a>
<a id="24782" class="Keyword">open</a> <a id="24787" class="Keyword">import</a> <a id="24794" href="order-theory.posets.html" class="Module">order-theory.posets</a>
<a id="24814" class="Keyword">open</a> <a id="24819" class="Keyword">import</a> <a id="24826" href="order-theory.preorders.html" class="Module">order-theory.preorders</a>
<a id="24849" class="Keyword">open</a> <a id="24854" class="Keyword">import</a> <a id="24861" href="order-theory.subposets.html" class="Module">order-theory.subposets</a>
<a id="24884" class="Keyword">open</a> <a id="24889" class="Keyword">import</a> <a id="24896" href="order-theory.subpreorders.html" class="Module">order-theory.subpreorders</a>
<a id="24922" class="Keyword">open</a> <a id="24927" class="Keyword">import</a> <a id="24934" href="order-theory.total-posets.html" class="Module">order-theory.total-posets</a>
<a id="24960" class="Keyword">open</a> <a id="24965" class="Keyword">import</a> <a id="24972" href="order-theory.total-preorders.html" class="Module">order-theory.total-preorders</a>
</pre>
## Polytopes

<pre class="Agda"><a id="25028" class="Keyword">open</a> <a id="25033" class="Keyword">import</a> <a id="25040" href="polytopes.html" class="Module">polytopes</a>
<a id="25050" class="Keyword">open</a> <a id="25055" class="Keyword">import</a> <a id="25062" href="polytopes.abstract-polytopes.html" class="Module">polytopes.abstract-polytopes</a>
</pre>
## Ring theory

<pre class="Agda"><a id="25120" class="Keyword">open</a> <a id="25125" class="Keyword">import</a> <a id="25132" href="ring-theory.html" class="Module">ring-theory</a>
<a id="25144" class="Keyword">open</a> <a id="25149" class="Keyword">import</a> <a id="25156" href="ring-theory.commutative-rings.html" class="Module">ring-theory.commutative-rings</a>
<a id="25186" class="Keyword">open</a> <a id="25191" class="Keyword">import</a> <a id="25198" href="ring-theory.discrete-fields.html" class="Module">ring-theory.discrete-fields</a>
<a id="25226" class="Keyword">open</a> <a id="25231" class="Keyword">import</a> <a id="25238" href="ring-theory.division-rings.html" class="Module">ring-theory.division-rings</a>
<a id="25265" class="Keyword">open</a> <a id="25270" class="Keyword">import</a> <a id="25277" href="ring-theory.eisenstein-integers.html" class="Module">ring-theory.eisenstein-integers</a>
<a id="25309" class="Keyword">open</a> <a id="25314" class="Keyword">import</a> <a id="25321" href="ring-theory.gaussian-integers.html" class="Module">ring-theory.gaussian-integers</a>
<a id="25351" class="Keyword">open</a> <a id="25356" class="Keyword">import</a> <a id="25363" href="ring-theory.homomorphisms-commutative-rings.html" class="Module">ring-theory.homomorphisms-commutative-rings</a>
<a id="25407" class="Keyword">open</a> <a id="25412" class="Keyword">import</a> <a id="25419" href="ring-theory.homomorphisms-rings.html" class="Module">ring-theory.homomorphisms-rings</a>
<a id="25451" class="Keyword">open</a> <a id="25456" class="Keyword">import</a> <a id="25463" href="ring-theory.ideals-generated-by-subsets-rings.html" class="Module">ring-theory.ideals-generated-by-subsets-rings</a>
<a id="25509" class="Keyword">open</a> <a id="25514" class="Keyword">import</a> <a id="25521" href="ring-theory.ideals-rings.html" class="Module">ring-theory.ideals-rings</a>
<a id="25546" class="Keyword">open</a> <a id="25551" class="Keyword">import</a> <a id="25558" href="ring-theory.invertible-elements-rings.html" class="Module">ring-theory.invertible-elements-rings</a>
<a id="25596" class="Keyword">open</a> <a id="25601" class="Keyword">import</a> <a id="25608" href="ring-theory.isomorphisms-commutative-rings.html" class="Module">ring-theory.isomorphisms-commutative-rings</a>
<a id="25651" class="Keyword">open</a> <a id="25656" class="Keyword">import</a> <a id="25663" href="ring-theory.isomorphisms-rings.html" class="Module">ring-theory.isomorphisms-rings</a>
<a id="25694" class="Keyword">open</a> <a id="25699" class="Keyword">import</a> <a id="25706" href="ring-theory.localizations-rings.html" class="Module">ring-theory.localizations-rings</a>
<a id="25738" class="Keyword">open</a> <a id="25743" class="Keyword">import</a> <a id="25750" href="ring-theory.nontrivial-rings.html" class="Module">ring-theory.nontrivial-rings</a>
<a id="25779" class="Keyword">open</a> <a id="25784" class="Keyword">import</a> <a id="25791" href="ring-theory.rings.html" class="Module">ring-theory.rings</a>
</pre>
## Synthetic homotopy theory

<pre class="Agda"><a id="25852" class="Keyword">open</a> <a id="25857" class="Keyword">import</a> <a id="25864" href="synthetic-homotopy-theory.html" class="Module">synthetic-homotopy-theory</a>
<a id="25890" class="Keyword">open</a> <a id="25895" class="Keyword">import</a> <a id="25902" href="synthetic-homotopy-theory.23-pullbacks.html" class="Module">synthetic-homotopy-theory.23-pullbacks</a>
<a id="25941" class="Keyword">open</a> <a id="25946" class="Keyword">import</a> <a id="25953" href="synthetic-homotopy-theory.24-pushouts.html" class="Module">synthetic-homotopy-theory.24-pushouts</a>
<a id="25991" class="Keyword">open</a> <a id="25996" class="Keyword">import</a> <a id="26003" href="synthetic-homotopy-theory.25-cubical-diagrams.html" class="Module">synthetic-homotopy-theory.25-cubical-diagrams</a>
<a id="26049" class="Keyword">open</a> <a id="26054" class="Keyword">import</a> <a id="26061" href="synthetic-homotopy-theory.26-descent.html" class="Module">synthetic-homotopy-theory.26-descent</a>
<a id="26098" class="Keyword">open</a> <a id="26103" class="Keyword">import</a> <a id="26110" href="synthetic-homotopy-theory.26-id-pushout.html" class="Module">synthetic-homotopy-theory.26-id-pushout</a>
<a id="26150" class="Keyword">open</a> <a id="26155" class="Keyword">import</a> <a id="26162" href="synthetic-homotopy-theory.27-sequences.html" class="Module">synthetic-homotopy-theory.27-sequences</a>
<a id="26201" class="Keyword">open</a> <a id="26206" class="Keyword">import</a> <a id="26213" href="synthetic-homotopy-theory.circle.html" class="Module">synthetic-homotopy-theory.circle</a>
<a id="26246" class="Keyword">open</a> <a id="26251" class="Keyword">import</a> <a id="26258" href="synthetic-homotopy-theory.commutative-operations.html" class="Module">synthetic-homotopy-theory.commutative-operations</a>
<a id="26307" class="Keyword">open</a> <a id="26312" class="Keyword">import</a> <a id="26319" href="synthetic-homotopy-theory.cyclic-types.html" class="Module">synthetic-homotopy-theory.cyclic-types</a>
<a id="26358" class="Keyword">open</a> <a id="26363" class="Keyword">import</a> <a id="26370" href="synthetic-homotopy-theory.double-loop-spaces.html" class="Module">synthetic-homotopy-theory.double-loop-spaces</a>
<a id="26415" class="Keyword">open</a> <a id="26420" class="Keyword">import</a> <a id="26427" href="synthetic-homotopy-theory.functoriality-loop-spaces.html" class="Module">synthetic-homotopy-theory.functoriality-loop-spaces</a>
<a id="26479" class="Keyword">open</a> <a id="26484" class="Keyword">import</a> <a id="26491" href="synthetic-homotopy-theory.groups-of-loops-in-1-types.html" class="Module">synthetic-homotopy-theory.groups-of-loops-in-1-types</a>
<a id="26544" class="Keyword">open</a> <a id="26549" class="Keyword">import</a> <a id="26556" href="synthetic-homotopy-theory.infinite-cyclic-types.html" class="Module">synthetic-homotopy-theory.infinite-cyclic-types</a>
<a id="26604" class="Keyword">open</a> <a id="26609" class="Keyword">import</a> <a id="26616" href="synthetic-homotopy-theory.interval-type.html" class="Module">synthetic-homotopy-theory.interval-type</a>
<a id="26656" class="Keyword">open</a> <a id="26661" class="Keyword">import</a> <a id="26668" href="synthetic-homotopy-theory.iterated-loop-spaces.html" class="Module">synthetic-homotopy-theory.iterated-loop-spaces</a>
<a id="26715" class="Keyword">open</a> <a id="26720" class="Keyword">import</a> <a id="26727" href="synthetic-homotopy-theory.loop-spaces.html" class="Module">synthetic-homotopy-theory.loop-spaces</a>
<a id="26765" class="Keyword">open</a> <a id="26770" class="Keyword">import</a> <a id="26777" href="synthetic-homotopy-theory.pointed-dependent-functions.html" class="Module">synthetic-homotopy-theory.pointed-dependent-functions</a>
<a id="26831" class="Keyword">open</a> <a id="26836" class="Keyword">import</a> <a id="26843" href="synthetic-homotopy-theory.pointed-equivalences.html" class="Module">synthetic-homotopy-theory.pointed-equivalences</a>
<a id="26890" class="Keyword">open</a> <a id="26895" class="Keyword">import</a> <a id="26902" href="synthetic-homotopy-theory.pointed-families-of-types.html" class="Module">synthetic-homotopy-theory.pointed-families-of-types</a>
<a id="26954" class="Keyword">open</a> <a id="26959" class="Keyword">import</a> <a id="26966" href="synthetic-homotopy-theory.pointed-homotopies.html" class="Module">synthetic-homotopy-theory.pointed-homotopies</a>
<a id="27011" class="Keyword">open</a> <a id="27016" class="Keyword">import</a> <a id="27023" href="synthetic-homotopy-theory.pointed-maps.html" class="Module">synthetic-homotopy-theory.pointed-maps</a>
<a id="27062" class="Keyword">open</a> <a id="27067" class="Keyword">import</a> <a id="27074" href="synthetic-homotopy-theory.pointed-types.html" class="Module">synthetic-homotopy-theory.pointed-types</a>
<a id="27114" class="Keyword">open</a> <a id="27119" class="Keyword">import</a> <a id="27126" href="synthetic-homotopy-theory.spaces.html" class="Module">synthetic-homotopy-theory.spaces</a>
<a id="27159" class="Keyword">open</a> <a id="27164" class="Keyword">import</a> <a id="27171" href="synthetic-homotopy-theory.triple-loop-spaces.html" class="Module">synthetic-homotopy-theory.triple-loop-spaces</a>
<a id="27216" class="Keyword">open</a> <a id="27221" class="Keyword">import</a> <a id="27228" href="synthetic-homotopy-theory.universal-cover-circle.html" class="Module">synthetic-homotopy-theory.universal-cover-circle</a>
</pre>
## Tutorials

<pre class="Agda"><a id="27304" class="Keyword">open</a> <a id="27309" class="Keyword">import</a> <a id="27316" href="tutorials.basic-agda.html" class="Module">tutorials.basic-agda</a>
</pre>
## Type theories

<pre class="Agda"><a id="27368" class="Keyword">open</a> <a id="27373" class="Keyword">import</a> <a id="27380" href="type-theories.html" class="Module">type-theories</a>
<a id="27394" class="Keyword">open</a> <a id="27399" class="Keyword">import</a> <a id="27406" href="type-theories.comprehension-type-theories.html" class="Module">type-theories.comprehension-type-theories</a>
<a id="27448" class="Keyword">open</a> <a id="27453" class="Keyword">import</a> <a id="27460" href="type-theories.dependent-type-theories.html" class="Module">type-theories.dependent-type-theories</a>
<a id="27498" class="Keyword">open</a> <a id="27503" class="Keyword">import</a> <a id="27510" href="type-theories.fibered-dependent-type-theories.html" class="Module">type-theories.fibered-dependent-type-theories</a>
<a id="27556" class="Keyword">open</a> <a id="27561" class="Keyword">import</a> <a id="27568" href="type-theories.sections-dependent-type-theories.html" class="Module">type-theories.sections-dependent-type-theories</a>
<a id="27615" class="Keyword">open</a> <a id="27620" class="Keyword">import</a> <a id="27627" href="type-theories.simple-type-theories.html" class="Module">type-theories.simple-type-theories</a>
<a id="27662" class="Keyword">open</a> <a id="27667" class="Keyword">import</a> <a id="27674" href="type-theories.unityped-type-theories.html" class="Module">type-theories.unityped-type-theories</a>
</pre>
## Univalent combinatorics

<pre class="Agda"><a id="27752" class="Keyword">open</a> <a id="27757" class="Keyword">import</a> <a id="27764" href="univalent-combinatorics.html" class="Module">univalent-combinatorics</a>
<a id="27788" class="Keyword">open</a> <a id="27793" class="Keyword">import</a> <a id="27800" href="univalent-combinatorics.2-element-decidable-subtypes.html" class="Module">univalent-combinatorics.2-element-decidable-subtypes</a>
<a id="27853" class="Keyword">open</a> <a id="27858" class="Keyword">import</a> <a id="27865" href="univalent-combinatorics.2-element-subtypes.html" class="Module">univalent-combinatorics.2-element-subtypes</a>
<a id="27908" class="Keyword">open</a> <a id="27913" class="Keyword">import</a> <a id="27920" href="univalent-combinatorics.2-element-types.html" class="Module">univalent-combinatorics.2-element-types</a>
<a id="27960" class="Keyword">open</a> <a id="27965" class="Keyword">import</a> <a id="27972" href="univalent-combinatorics.binomial-types.html" class="Module">univalent-combinatorics.binomial-types</a>
<a id="28011" class="Keyword">open</a> <a id="28016" class="Keyword">import</a> <a id="28023" href="univalent-combinatorics.cartesian-product-types.html" class="Module">univalent-combinatorics.cartesian-product-types</a>
<a id="28071" class="Keyword">open</a> <a id="28076" class="Keyword">import</a> <a id="28083" href="univalent-combinatorics.classical-finite-types.html" class="Module">univalent-combinatorics.classical-finite-types</a>
<a id="28130" class="Keyword">open</a> <a id="28135" class="Keyword">import</a> <a id="28142" href="univalent-combinatorics.complements-isolated-points.html" class="Module">univalent-combinatorics.complements-isolated-points</a>
<a id="28194" class="Keyword">open</a> <a id="28199" class="Keyword">import</a> <a id="28206" href="univalent-combinatorics.coproduct-types.html" class="Module">univalent-combinatorics.coproduct-types</a>
<a id="28246" class="Keyword">open</a> <a id="28251" class="Keyword">import</a> <a id="28258" href="univalent-combinatorics.counting-decidable-subtypes.html" class="Module">univalent-combinatorics.counting-decidable-subtypes</a>
<a id="28310" class="Keyword">open</a> <a id="28315" class="Keyword">import</a> <a id="28322" href="univalent-combinatorics.counting-dependent-pair-types.html" class="Module">univalent-combinatorics.counting-dependent-pair-types</a>
<a id="28376" class="Keyword">open</a> <a id="28381" class="Keyword">import</a> <a id="28388" href="univalent-combinatorics.counting-maybe.html" class="Module">univalent-combinatorics.counting-maybe</a>
<a id="28427" class="Keyword">open</a> <a id="28432" class="Keyword">import</a> <a id="28439" href="univalent-combinatorics.counting.html" class="Module">univalent-combinatorics.counting</a>
<a id="28472" class="Keyword">open</a> <a id="28477" class="Keyword">import</a> <a id="28484" href="univalent-combinatorics.cubes.html" class="Module">univalent-combinatorics.cubes</a>
<a id="28514" class="Keyword">open</a> <a id="28519" class="Keyword">import</a> <a id="28526" href="univalent-combinatorics.decidable-dependent-function-types.html" class="Module">univalent-combinatorics.decidable-dependent-function-types</a>
<a id="28585" class="Keyword">open</a> <a id="28590" class="Keyword">import</a> <a id="28597" href="univalent-combinatorics.decidable-dependent-pair-types.html" class="Module">univalent-combinatorics.decidable-dependent-pair-types</a>
<a id="28652" class="Keyword">open</a> <a id="28657" class="Keyword">import</a> <a id="28664" href="univalent-combinatorics.decidable-subtypes.html" class="Module">univalent-combinatorics.decidable-subtypes</a>
<a id="28707" class="Keyword">open</a> <a id="28712" class="Keyword">import</a> <a id="28719" href="univalent-combinatorics.dependent-function-types.html" class="Module">univalent-combinatorics.dependent-function-types</a>
<a id="28768" class="Keyword">open</a> <a id="28773" class="Keyword">import</a> <a id="28780" href="univalent-combinatorics.dedekind-finite-sets.html" class="Module">univalent-combinatorics.dedekind-finite-sets</a>
<a id="28825" class="Keyword">open</a> <a id="28830" class="Keyword">import</a> <a id="28837" href="univalent-combinatorics.dependent-sum-finite-types.html" class="Module">univalent-combinatorics.dependent-sum-finite-types</a>
<a id="28888" class="Keyword">open</a> <a id="28893" class="Keyword">import</a> <a id="28900" href="univalent-combinatorics.distributivity-of-set-truncation-over-finite-products.html" class="Module">univalent-combinatorics.distributivity-of-set-truncation-over-finite-products</a>
<a id="28978" class="Keyword">open</a> <a id="28983" class="Keyword">import</a> <a id="28990" href="univalent-combinatorics.double-counting.html" class="Module">univalent-combinatorics.double-counting</a>
<a id="29030" class="Keyword">open</a> <a id="29035" class="Keyword">import</a> <a id="29042" href="univalent-combinatorics.embeddings-standard-finite-types.html" class="Module">univalent-combinatorics.embeddings-standard-finite-types</a>
<a id="29099" class="Keyword">open</a> <a id="29104" class="Keyword">import</a> <a id="29111" href="univalent-combinatorics.embeddings.html" class="Module">univalent-combinatorics.embeddings</a>
<a id="29146" class="Keyword">open</a> <a id="29151" class="Keyword">import</a> <a id="29158" href="univalent-combinatorics.equality-finite-types.html" class="Module">univalent-combinatorics.equality-finite-types</a>
<a id="29204" class="Keyword">open</a> <a id="29209" class="Keyword">import</a> <a id="29216" href="univalent-combinatorics.equality-standard-finite-types.html" class="Module">univalent-combinatorics.equality-standard-finite-types</a>
<a id="29271" class="Keyword">open</a> <a id="29276" class="Keyword">import</a> <a id="29283" href="univalent-combinatorics.equivalences-cubes.html" class="Module">univalent-combinatorics.equivalences-cubes</a>
<a id="29326" class="Keyword">open</a> <a id="29331" class="Keyword">import</a> <a id="29338" href="univalent-combinatorics.equivalences-standard-finite-types.html" class="Module">univalent-combinatorics.equivalences-standard-finite-types</a>
<a id="29397" class="Keyword">open</a> <a id="29402" class="Keyword">import</a> <a id="29409" href="univalent-combinatorics.equivalences.html" class="Module">univalent-combinatorics.equivalences</a>
<a id="29446" class="Keyword">open</a> <a id="29451" class="Keyword">import</a> <a id="29458" href="univalent-combinatorics.fibers-of-maps.html" class="Module">univalent-combinatorics.fibers-of-maps</a>
<a id="29497" class="Keyword">open</a> <a id="29502" class="Keyword">import</a> <a id="29509" href="univalent-combinatorics.finite-choice.html" class="Module">univalent-combinatorics.finite-choice</a>
<a id="29547" class="Keyword">open</a> <a id="29552" class="Keyword">import</a> <a id="29559" href="univalent-combinatorics.finite-connected-components.html" class="Module">univalent-combinatorics.finite-connected-components</a>
<a id="29611" class="Keyword">open</a> <a id="29616" class="Keyword">import</a> <a id="29623" href="univalent-combinatorics.finite-presentations.html" class="Module">univalent-combinatorics.finite-presentations</a>
<a id="29668" class="Keyword">open</a> <a id="29673" class="Keyword">import</a> <a id="29680" href="univalent-combinatorics.finite-types.html" class="Module">univalent-combinatorics.finite-types</a>
<a id="29717" class="Keyword">open</a> <a id="29722" class="Keyword">import</a> <a id="29729" href="univalent-combinatorics.finitely-presented-types.html" class="Module">univalent-combinatorics.finitely-presented-types</a>
<a id="29778" class="Keyword">open</a> <a id="29783" class="Keyword">import</a> <a id="29790" href="univalent-combinatorics.function-types.html" class="Module">univalent-combinatorics.function-types</a>
<a id="29829" class="Keyword">open</a> <a id="29834" class="Keyword">import</a> <a id="29841" href="univalent-combinatorics.image-of-maps.html" class="Module">univalent-combinatorics.image-of-maps</a>
<a id="29879" class="Keyword">open</a> <a id="29884" class="Keyword">import</a> <a id="29891" href="univalent-combinatorics.inequality-types-with-counting.html" class="Module">univalent-combinatorics.inequality-types-with-counting</a>
<a id="29946" class="Keyword">open</a> <a id="29951" class="Keyword">import</a> <a id="29958" href="univalent-combinatorics.injective-maps.html" class="Module">univalent-combinatorics.injective-maps</a>
<a id="29997" class="Keyword">open</a> <a id="30002" class="Keyword">import</a> <a id="30009" href="univalent-combinatorics.kuratowsky-finite-sets.html" class="Module">univalent-combinatorics.kuratowsky-finite-sets</a>
<a id="30056" class="Keyword">open</a> <a id="30061" class="Keyword">import</a> <a id="30068" href="univalent-combinatorics.lists.html" class="Module">univalent-combinatorics.lists</a>
<a id="30098" class="Keyword">open</a> <a id="30103" class="Keyword">import</a> <a id="30110" href="univalent-combinatorics.maybe.html" class="Module">univalent-combinatorics.maybe</a>
<a id="30140" class="Keyword">open</a> <a id="30145" class="Keyword">import</a> <a id="30152" href="univalent-combinatorics.orientations-complete-undirected-graph.html" class="Module">univalent-combinatorics.orientations-complete-undirected-graph</a>
<a id="30215" class="Keyword">open</a> <a id="30220" class="Keyword">import</a> <a id="30227" href="univalent-combinatorics.orientations-cubes.html" class="Module">univalent-combinatorics.orientations-cubes</a>
<a id="30270" class="Keyword">open</a> <a id="30275" class="Keyword">import</a> <a id="30282" href="univalent-combinatorics.petri-nets.html" class="Module">univalent-combinatorics.petri-nets</a>
<a id="30317" class="Keyword">open</a> <a id="30322" class="Keyword">import</a> <a id="30329" href="univalent-combinatorics.pi-finite-types.html" class="Module">univalent-combinatorics.pi-finite-types</a>
<a id="30369" class="Keyword">open</a> <a id="30374" class="Keyword">import</a> <a id="30381" href="univalent-combinatorics.pigeonhole-principle.html" class="Module">univalent-combinatorics.pigeonhole-principle</a>
<a id="30426" class="Keyword">open</a> <a id="30431" class="Keyword">import</a> <a id="30438" href="univalent-combinatorics.presented-pi-finite-types.html" class="Module">univalent-combinatorics.presented-pi-finite-types</a>
<a id="30488" class="Keyword">open</a> <a id="30493" class="Keyword">import</a> <a id="30500" href="univalent-combinatorics.ramsey-theory.html" class="Module">univalent-combinatorics.ramsey-theory</a>
<a id="30538" class="Keyword">open</a> <a id="30543" class="Keyword">import</a> <a id="30550" href="univalent-combinatorics.retracts-of-finite-types.html" class="Module">univalent-combinatorics.retracts-of-finite-types</a>
<a id="30599" class="Keyword">open</a> <a id="30604" class="Keyword">import</a> <a id="30611" href="univalent-combinatorics.skipping-element-standard-finite-types.html" class="Module">univalent-combinatorics.skipping-element-standard-finite-types</a>
<a id="30674" class="Keyword">open</a> <a id="30679" class="Keyword">import</a> <a id="30686" href="univalent-combinatorics.species.html" class="Module">univalent-combinatorics.species</a>
<a id="30718" class="Keyword">open</a> <a id="30723" class="Keyword">import</a> <a id="30730" href="univalent-combinatorics.standard-finite-pruned-trees.html" class="Module">univalent-combinatorics.standard-finite-pruned-trees</a>
<a id="30783" class="Keyword">open</a> <a id="30788" class="Keyword">import</a> <a id="30795" href="univalent-combinatorics.standard-finite-trees.html" class="Module">univalent-combinatorics.standard-finite-trees</a>
<a id="30841" class="Keyword">open</a> <a id="30846" class="Keyword">import</a> <a id="30853" href="univalent-combinatorics.standard-finite-types.html" class="Module">univalent-combinatorics.standard-finite-types</a>
<a id="30899" class="Keyword">open</a> <a id="30904" class="Keyword">import</a> <a id="30911" href="univalent-combinatorics.sums-of-natural-numbers.html" class="Module">univalent-combinatorics.sums-of-natural-numbers</a>
<a id="30959" class="Keyword">open</a> <a id="30964" class="Keyword">import</a> <a id="30971" href="univalent-combinatorics.surjective-maps.html" class="Module">univalent-combinatorics.surjective-maps</a>
<a id="31011" class="Keyword">open</a> <a id="31016" class="Keyword">import</a> <a id="31023" href="univalent-combinatorics.symmetric-difference.html" class="Module">univalent-combinatorics.symmetric-difference</a>
</pre>
## Wild algebra

<pre class="Agda"><a id="31098" class="Keyword">open</a> <a id="31103" class="Keyword">import</a> <a id="31110" href="wild-algebra.html" class="Module">wild-algebra</a>
<a id="31123" class="Keyword">open</a> <a id="31128" class="Keyword">import</a> <a id="31135" href="wild-algebra.magmas.html" class="Module">wild-algebra.magmas</a>
<a id="31155" class="Keyword">open</a> <a id="31160" class="Keyword">import</a> <a id="31167" href="wild-algebra.morphisms-magmas.html" class="Module">wild-algebra.morphisms-magmas</a>
<a id="31197" class="Keyword">open</a> <a id="31202" class="Keyword">import</a> <a id="31209" href="wild-algebra.morphisms-wild-unital-magmas.html" class="Module">wild-algebra.morphisms-wild-unital-magmas</a>
<a id="31251" class="Keyword">open</a> <a id="31256" class="Keyword">import</a> <a id="31263" href="wild-algebra.universal-property-lists-wild-monoids.html" class="Module">wild-algebra.universal-property-lists-wild-monoids</a>
<a id="31314" class="Keyword">open</a> <a id="31319" class="Keyword">import</a> <a id="31326" href="wild-algebra.wild-groups.html" class="Module">wild-algebra.wild-groups</a>
<a id="31351" class="Keyword">open</a> <a id="31356" class="Keyword">import</a> <a id="31363" href="wild-algebra.wild-loops.html" class="Module">wild-algebra.wild-loops</a>
<a id="31387" class="Keyword">open</a> <a id="31392" class="Keyword">import</a> <a id="31399" href="wild-algebra.wild-monoids.html" class="Module">wild-algebra.wild-monoids</a>
<a id="31425" class="Keyword">open</a> <a id="31430" class="Keyword">import</a> <a id="31437" href="wild-algebra.wild-quasigroups.html" class="Module">wild-algebra.wild-quasigroups</a>
<a id="31467" class="Keyword">open</a> <a id="31472" class="Keyword">import</a> <a id="31479" href="wild-algebra.wild-semigroups.html" class="Module">wild-algebra.wild-semigroups</a>
<a id="31508" class="Keyword">open</a> <a id="31513" class="Keyword">import</a> <a id="31520" href="wild-algebra.wild-unital-magmas.html" class="Module">wild-algebra.wild-unital-magmas</a>
</pre>
## Everything

See the list of all Agda modules [here](everything.html).

