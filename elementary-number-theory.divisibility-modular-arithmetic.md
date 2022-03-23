# Divisibility in modular arithmetic

<pre class="Agda"><a id="47" class="Symbol">{-#</a> <a id="51" class="Keyword">OPTIONS</a> <a id="59" class="Pragma">--without-K</a> <a id="71" class="Pragma">--exact-split</a> <a id="85" class="Symbol">#-}</a>

<a id="90" class="Keyword">module</a> <a id="97" href="elementary-number-theory.divisibility-modular-arithmetic.html" class="Module">elementary-number-theory.divisibility-modular-arithmetic</a> <a id="154" class="Keyword">where</a>

<a id="161" class="Keyword">open</a> <a id="166" class="Keyword">import</a> <a id="173" href="elementary-number-theory.divisibility-integers.html" class="Module">elementary-number-theory.divisibility-integers</a> <a id="220" class="Keyword">using</a>
  <a id="228" class="Symbol">(</a> <a id="230" href="elementary-number-theory.divisibility-integers.html#2319" class="Function">refl-div-ℤ</a><a id="240" class="Symbol">;</a> <a id="242" href="elementary-number-theory.divisibility-integers.html#2423" class="Function">trans-div-ℤ</a><a id="253" class="Symbol">)</a>
<a id="255" class="Keyword">open</a> <a id="260" class="Keyword">import</a> <a id="267" href="elementary-number-theory.divisibility-standard-finite-types.html" class="Module">elementary-number-theory.divisibility-standard-finite-types</a> <a id="327" class="Keyword">using</a>
  <a id="335" class="Symbol">(</a> <a id="337" href="elementary-number-theory.divisibility-standard-finite-types.html#1376" class="Function">refl-div-Fin</a><a id="349" class="Symbol">;</a> <a id="351" href="elementary-number-theory.divisibility-standard-finite-types.html#1583" class="Function">trans-div-Fin</a><a id="364" class="Symbol">)</a>
<a id="366" class="Keyword">open</a> <a id="371" class="Keyword">import</a> <a id="378" href="elementary-number-theory.modular-arithmetic.html" class="Module">elementary-number-theory.modular-arithmetic</a> <a id="422" class="Keyword">using</a>
  <a id="430" class="Symbol">(</a> <a id="432" href="elementary-number-theory.modular-arithmetic.html#3446" class="Function">ℤ-Mod</a><a id="437" class="Symbol">;</a> <a id="439" href="elementary-number-theory.modular-arithmetic.html#11613" class="Function">mul-ℤ-Mod</a><a id="448" class="Symbol">)</a>
<a id="450" class="Keyword">open</a> <a id="455" class="Keyword">import</a> <a id="462" href="elementary-number-theory.natural-numbers.html" class="Module">elementary-number-theory.natural-numbers</a> <a id="503" class="Keyword">using</a> <a id="509" class="Symbol">(</a><a id="510" href="elementary-number-theory.natural-numbers.html#1444" class="Datatype">ℕ</a><a id="511" class="Symbol">)</a>

<a id="514" class="Keyword">open</a> <a id="519" class="Keyword">import</a> <a id="526" href="foundation.dependent-pair-types.html" class="Module">foundation.dependent-pair-types</a> <a id="558" class="Keyword">using</a> <a id="564" class="Symbol">(</a><a id="565" href="foundation-core.dependent-pair-types.html#502" class="Record">Σ</a><a id="566" class="Symbol">;</a> <a id="568" href="foundation-core.dependent-pair-types.html#575" class="InductiveConstructor">pair</a><a id="572" class="Symbol">;</a> <a id="574" href="foundation-core.dependent-pair-types.html#592" class="Field">pr1</a><a id="577" class="Symbol">;</a> <a id="579" href="foundation-core.dependent-pair-types.html#604" class="Field">pr2</a><a id="582" class="Symbol">)</a>
<a id="584" class="Keyword">open</a> <a id="589" class="Keyword">import</a> <a id="596" href="foundation.identity-types.html" class="Module">foundation.identity-types</a> <a id="622" class="Keyword">using</a> <a id="628" class="Symbol">(</a><a id="629" href="foundation-core.identity-types.html#641" class="Datatype">Id</a><a id="631" class="Symbol">)</a>
<a id="633" class="Keyword">open</a> <a id="638" class="Keyword">import</a> <a id="645" href="foundation.universe-levels.html" class="Module">foundation.universe-levels</a> <a id="672" class="Keyword">using</a> <a id="678" class="Symbol">(</a><a id="679" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a><a id="681" class="Symbol">;</a> <a id="683" href="Agda.Primitive.html#764" class="Primitive">lzero</a><a id="688" class="Symbol">)</a>
</pre>
## Idea

For two numbers `x` and `y` in `ℤ-Mod k`, we say that `x` divides `y` if there is a number `u` in `ℤ-Mod k` such that `mul-ℤ-Mod k u x = y`.

## Definition

<pre class="Agda"><a id="div-ℤ-Mod"></a><a id="869" href="elementary-number-theory.divisibility-modular-arithmetic.html#869" class="Function">div-ℤ-Mod</a> <a id="879" class="Symbol">:</a> <a id="881" class="Symbol">(</a><a id="882" href="elementary-number-theory.divisibility-modular-arithmetic.html#882" class="Bound">k</a> <a id="884" class="Symbol">:</a> <a id="886" href="elementary-number-theory.natural-numbers.html#1444" class="Datatype">ℕ</a><a id="887" class="Symbol">)</a> <a id="889" class="Symbol">→</a> <a id="891" href="elementary-number-theory.modular-arithmetic.html#3446" class="Function">ℤ-Mod</a> <a id="897" href="elementary-number-theory.divisibility-modular-arithmetic.html#882" class="Bound">k</a> <a id="899" class="Symbol">→</a> <a id="901" href="elementary-number-theory.modular-arithmetic.html#3446" class="Function">ℤ-Mod</a> <a id="907" href="elementary-number-theory.divisibility-modular-arithmetic.html#882" class="Bound">k</a> <a id="909" class="Symbol">→</a> <a id="911" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="914" href="Agda.Primitive.html#764" class="Primitive">lzero</a>
<a id="920" href="elementary-number-theory.divisibility-modular-arithmetic.html#869" class="Function">div-ℤ-Mod</a> <a id="930" href="elementary-number-theory.divisibility-modular-arithmetic.html#930" class="Bound">k</a> <a id="932" href="elementary-number-theory.divisibility-modular-arithmetic.html#932" class="Bound">x</a> <a id="934" href="elementary-number-theory.divisibility-modular-arithmetic.html#934" class="Bound">y</a> <a id="936" class="Symbol">=</a> <a id="938" href="foundation-core.dependent-pair-types.html#502" class="Record">Σ</a> <a id="940" class="Symbol">(</a><a id="941" href="elementary-number-theory.modular-arithmetic.html#3446" class="Function">ℤ-Mod</a> <a id="947" href="elementary-number-theory.divisibility-modular-arithmetic.html#930" class="Bound">k</a><a id="948" class="Symbol">)</a> <a id="950" class="Symbol">(λ</a> <a id="953" href="elementary-number-theory.divisibility-modular-arithmetic.html#953" class="Bound">u</a> <a id="955" class="Symbol">→</a> <a id="957" href="foundation-core.identity-types.html#641" class="Datatype">Id</a> <a id="960" class="Symbol">(</a><a id="961" href="elementary-number-theory.modular-arithmetic.html#11613" class="Function">mul-ℤ-Mod</a> <a id="971" href="elementary-number-theory.divisibility-modular-arithmetic.html#930" class="Bound">k</a> <a id="973" href="elementary-number-theory.divisibility-modular-arithmetic.html#953" class="Bound">u</a> <a id="975" href="elementary-number-theory.divisibility-modular-arithmetic.html#932" class="Bound">x</a><a id="976" class="Symbol">)</a> <a id="978" href="elementary-number-theory.divisibility-modular-arithmetic.html#934" class="Bound">y</a><a id="979" class="Symbol">)</a>
</pre>
## Properties

### The divisibility relation is reflexive

<pre class="Agda"><a id="refl-div-ℤ-Mod"></a><a id="1053" href="elementary-number-theory.divisibility-modular-arithmetic.html#1053" class="Function">refl-div-ℤ-Mod</a> <a id="1068" class="Symbol">:</a> <a id="1070" class="Symbol">{</a><a id="1071" href="elementary-number-theory.divisibility-modular-arithmetic.html#1071" class="Bound">k</a> <a id="1073" class="Symbol">:</a> <a id="1075" href="elementary-number-theory.natural-numbers.html#1444" class="Datatype">ℕ</a><a id="1076" class="Symbol">}</a> <a id="1078" class="Symbol">(</a><a id="1079" href="elementary-number-theory.divisibility-modular-arithmetic.html#1079" class="Bound">x</a> <a id="1081" class="Symbol">:</a> <a id="1083" href="elementary-number-theory.modular-arithmetic.html#3446" class="Function">ℤ-Mod</a> <a id="1089" href="elementary-number-theory.divisibility-modular-arithmetic.html#1071" class="Bound">k</a><a id="1090" class="Symbol">)</a> <a id="1092" class="Symbol">→</a> <a id="1094" href="elementary-number-theory.divisibility-modular-arithmetic.html#869" class="Function">div-ℤ-Mod</a> <a id="1104" href="elementary-number-theory.divisibility-modular-arithmetic.html#1071" class="Bound">k</a> <a id="1106" href="elementary-number-theory.divisibility-modular-arithmetic.html#1079" class="Bound">x</a> <a id="1108" href="elementary-number-theory.divisibility-modular-arithmetic.html#1079" class="Bound">x</a>
<a id="1110" href="elementary-number-theory.divisibility-modular-arithmetic.html#1053" class="Function">refl-div-ℤ-Mod</a> <a id="1125" class="Symbol">{</a><a id="1126" href="elementary-number-theory.natural-numbers.html#1465" class="InductiveConstructor">ℕ.zero-ℕ</a><a id="1134" class="Symbol">}</a> <a id="1136" class="Symbol">=</a> <a id="1138" href="elementary-number-theory.divisibility-integers.html#2319" class="Function">refl-div-ℤ</a>
<a id="1149" href="elementary-number-theory.divisibility-modular-arithmetic.html#1053" class="Function">refl-div-ℤ-Mod</a> <a id="1164" class="Symbol">{</a><a id="1165" href="elementary-number-theory.natural-numbers.html#1478" class="InductiveConstructor">ℕ.succ-ℕ</a> <a id="1174" href="elementary-number-theory.divisibility-modular-arithmetic.html#1174" class="Bound">k</a><a id="1175" class="Symbol">}</a> <a id="1177" class="Symbol">=</a> <a id="1179" href="elementary-number-theory.divisibility-standard-finite-types.html#1376" class="Function">refl-div-Fin</a>
</pre>
### The divisibility relation is transitive

<pre class="Agda"><a id="trans-div-ℤ-Mod"></a><a id="1250" href="elementary-number-theory.divisibility-modular-arithmetic.html#1250" class="Function">trans-div-ℤ-Mod</a> <a id="1266" class="Symbol">:</a>
  <a id="1270" class="Symbol">{</a><a id="1271" href="elementary-number-theory.divisibility-modular-arithmetic.html#1271" class="Bound">k</a> <a id="1273" class="Symbol">:</a> <a id="1275" href="elementary-number-theory.natural-numbers.html#1444" class="Datatype">ℕ</a><a id="1276" class="Symbol">}</a> <a id="1278" class="Symbol">(</a><a id="1279" href="elementary-number-theory.divisibility-modular-arithmetic.html#1279" class="Bound">x</a> <a id="1281" href="elementary-number-theory.divisibility-modular-arithmetic.html#1281" class="Bound">y</a> <a id="1283" href="elementary-number-theory.divisibility-modular-arithmetic.html#1283" class="Bound">z</a> <a id="1285" class="Symbol">:</a> <a id="1287" href="elementary-number-theory.modular-arithmetic.html#3446" class="Function">ℤ-Mod</a> <a id="1293" href="elementary-number-theory.divisibility-modular-arithmetic.html#1271" class="Bound">k</a><a id="1294" class="Symbol">)</a> <a id="1296" class="Symbol">→</a>
  <a id="1300" href="elementary-number-theory.divisibility-modular-arithmetic.html#869" class="Function">div-ℤ-Mod</a> <a id="1310" href="elementary-number-theory.divisibility-modular-arithmetic.html#1271" class="Bound">k</a> <a id="1312" href="elementary-number-theory.divisibility-modular-arithmetic.html#1279" class="Bound">x</a> <a id="1314" href="elementary-number-theory.divisibility-modular-arithmetic.html#1281" class="Bound">y</a> <a id="1316" class="Symbol">→</a> <a id="1318" href="elementary-number-theory.divisibility-modular-arithmetic.html#869" class="Function">div-ℤ-Mod</a> <a id="1328" href="elementary-number-theory.divisibility-modular-arithmetic.html#1271" class="Bound">k</a> <a id="1330" href="elementary-number-theory.divisibility-modular-arithmetic.html#1281" class="Bound">y</a> <a id="1332" href="elementary-number-theory.divisibility-modular-arithmetic.html#1283" class="Bound">z</a> <a id="1334" class="Symbol">→</a> <a id="1336" href="elementary-number-theory.divisibility-modular-arithmetic.html#869" class="Function">div-ℤ-Mod</a> <a id="1346" href="elementary-number-theory.divisibility-modular-arithmetic.html#1271" class="Bound">k</a> <a id="1348" href="elementary-number-theory.divisibility-modular-arithmetic.html#1279" class="Bound">x</a> <a id="1350" href="elementary-number-theory.divisibility-modular-arithmetic.html#1283" class="Bound">z</a>
<a id="1352" href="elementary-number-theory.divisibility-modular-arithmetic.html#1250" class="Function">trans-div-ℤ-Mod</a> <a id="1368" class="Symbol">{</a><a id="1369" href="elementary-number-theory.natural-numbers.html#1465" class="InductiveConstructor">ℕ.zero-ℕ</a><a id="1377" class="Symbol">}</a> <a id="1379" class="Symbol">=</a> <a id="1381" href="elementary-number-theory.divisibility-integers.html#2423" class="Function">trans-div-ℤ</a>
<a id="1393" href="elementary-number-theory.divisibility-modular-arithmetic.html#1250" class="Function">trans-div-ℤ-Mod</a> <a id="1409" class="Symbol">{</a><a id="1410" href="elementary-number-theory.natural-numbers.html#1478" class="InductiveConstructor">ℕ.succ-ℕ</a> <a id="1419" href="elementary-number-theory.divisibility-modular-arithmetic.html#1419" class="Bound">k</a><a id="1420" class="Symbol">}</a> <a id="1422" class="Symbol">=</a> <a id="1424" href="elementary-number-theory.divisibility-standard-finite-types.html#1583" class="Function">trans-div-Fin</a>
</pre>