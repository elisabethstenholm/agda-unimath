---
title: Retracts of finite types
---

<pre class="Agda"><a id="50" class="Symbol">{-#</a> <a id="54" class="Keyword">OPTIONS</a> <a id="62" class="Pragma">--without-K</a> <a id="74" class="Pragma">--exact-split</a> <a id="88" class="Symbol">#-}</a>

<a id="93" class="Keyword">module</a> <a id="100" href="univalent-combinatorics.retracts-of-finite-types.html" class="Module">univalent-combinatorics.retracts-of-finite-types</a> <a id="149" class="Keyword">where</a>

<a id="156" class="Keyword">open</a> <a id="161" class="Keyword">import</a> <a id="168" href="elementary-number-theory.natural-numbers.html" class="Module">elementary-number-theory.natural-numbers</a> <a id="209" class="Keyword">using</a> <a id="215" class="Symbol">(</a><a id="216" href="elementary-number-theory.natural-numbers.html#1444" class="Datatype">ℕ</a><a id="217" class="Symbol">)</a>

<a id="220" class="Keyword">open</a> <a id="225" class="Keyword">import</a> <a id="232" href="foundation.decidable-maps.html" class="Module">foundation.decidable-maps</a> <a id="258" class="Keyword">using</a>
  <a id="266" class="Symbol">(</a> <a id="268" href="foundation.decidable-maps.html#758" class="Function">is-decidable-map</a><a id="284" class="Symbol">;</a> <a id="286" href="foundation.decidable-maps.html#869" class="Function">is-decidable-map-retr</a><a id="307" class="Symbol">)</a>
<a id="309" class="Keyword">open</a> <a id="314" class="Keyword">import</a> <a id="321" href="foundation.dependent-pair-types.html" class="Module">foundation.dependent-pair-types</a> <a id="353" class="Keyword">using</a> <a id="359" class="Symbol">(</a><a id="360" href="foundation-core.dependent-pair-types.html#502" class="Record">Σ</a><a id="361" class="Symbol">;</a> <a id="363" href="foundation-core.dependent-pair-types.html#575" class="InductiveConstructor">pair</a><a id="367" class="Symbol">;</a> <a id="369" href="foundation-core.dependent-pair-types.html#592" class="Field">pr1</a><a id="372" class="Symbol">;</a> <a id="374" href="foundation-core.dependent-pair-types.html#604" class="Field">pr2</a><a id="377" class="Symbol">)</a>
<a id="379" class="Keyword">open</a> <a id="384" class="Keyword">import</a> <a id="391" href="foundation.embeddings.html" class="Module">foundation.embeddings</a> <a id="413" class="Keyword">using</a> <a id="419" class="Symbol">(</a><a id="420" href="foundation-core.embeddings.html#980" class="Function">is-emb</a><a id="426" class="Symbol">;</a> <a id="428" href="foundation-core.embeddings.html#1062" class="Function Operator">_↪_</a><a id="431" class="Symbol">)</a>
<a id="433" class="Keyword">open</a> <a id="438" class="Keyword">import</a> <a id="445" href="foundation.fibers-of-maps.html" class="Module">foundation.fibers-of-maps</a> <a id="471" class="Keyword">using</a> <a id="477" class="Symbol">(</a><a id="478" href="foundation-core.fibers-of-maps.html#5261" class="Function">equiv-total-fib</a><a id="493" class="Symbol">)</a>
<a id="495" class="Keyword">open</a> <a id="500" class="Keyword">import</a> <a id="507" href="foundation.functoriality-propositional-truncation.html" class="Module">foundation.functoriality-propositional-truncation</a> <a id="557" class="Keyword">using</a>
  <a id="565" class="Symbol">(</a> <a id="567" href="foundation.functoriality-propositional-truncation.html#1451" class="Function">functor-trunc-Prop</a><a id="585" class="Symbol">)</a>
<a id="587" class="Keyword">open</a> <a id="592" class="Keyword">import</a> <a id="599" href="foundation.injective-maps.html" class="Module">foundation.injective-maps</a> <a id="625" class="Keyword">using</a> <a id="631" class="Symbol">(</a><a id="632" href="foundation.injective-maps.html#4595" class="Function">is-emb-is-injective</a><a id="651" class="Symbol">)</a>
<a id="653" class="Keyword">open</a> <a id="658" class="Keyword">import</a> <a id="665" href="foundation.propositional-maps.html" class="Module">foundation.propositional-maps</a> <a id="695" class="Keyword">using</a> <a id="701" class="Symbol">(</a><a id="702" href="foundation-core.propositional-maps.html#2460" class="Function">fib-emb-Prop</a><a id="714" class="Symbol">)</a>
<a id="716" class="Keyword">open</a> <a id="721" class="Keyword">import</a> <a id="728" href="foundation.retractions.html" class="Module">foundation.retractions</a> <a id="751" class="Keyword">using</a>
  <a id="759" class="Symbol">(</a> <a id="761" href="foundation-core.retractions.html#593" class="Function">retr</a><a id="765" class="Symbol">;</a> <a id="767" href="foundation.retractions.html#2840" class="Function">is-injective-retr</a><a id="784" class="Symbol">;</a> <a id="786" href="foundation-core.retractions.html#670" class="Function Operator">_retract-of_</a><a id="798" class="Symbol">)</a>
<a id="800" class="Keyword">open</a> <a id="805" class="Keyword">import</a> <a id="812" href="foundation.universe-levels.html" class="Module">foundation.universe-levels</a> <a id="839" class="Keyword">using</a> <a id="845" class="Symbol">(</a><a id="846" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="851" class="Symbol">;</a> <a id="853" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a><a id="855" class="Symbol">)</a>

<a id="858" class="Keyword">open</a> <a id="863" class="Keyword">import</a> <a id="870" href="univalent-combinatorics.counting.html" class="Module">univalent-combinatorics.counting</a> <a id="903" class="Keyword">using</a>
  <a id="911" class="Symbol">(</a> <a id="913" href="univalent-combinatorics.counting.html#1759" class="Function">count</a><a id="918" class="Symbol">;</a> <a id="920" href="univalent-combinatorics.counting.html#5721" class="Function">has-decidable-equality-count</a><a id="948" class="Symbol">;</a> <a id="950" href="univalent-combinatorics.counting.html#2336" class="Function">is-set-count</a><a id="962" class="Symbol">;</a> <a id="964" href="univalent-combinatorics.counting.html#2974" class="Function">count-equiv</a><a id="975" class="Symbol">)</a>
<a id="977" class="Keyword">open</a> <a id="982" class="Keyword">import</a> <a id="989" href="univalent-combinatorics.counting-decidable-subtypes.html" class="Module">univalent-combinatorics.counting-decidable-subtypes</a> <a id="1041" class="Keyword">using</a>
  <a id="1049" class="Symbol">(</a> <a id="1051" href="univalent-combinatorics.counting-decidable-subtypes.html#6686" class="Function">count-decidable-subtype</a><a id="1074" class="Symbol">)</a>
<a id="1076" class="Keyword">open</a> <a id="1081" class="Keyword">import</a> <a id="1088" href="univalent-combinatorics.equality-finite-types.html" class="Module">univalent-combinatorics.equality-finite-types</a> <a id="1134" class="Keyword">using</a>
  <a id="1142" class="Symbol">(</a> <a id="1144" href="univalent-combinatorics.equality-finite-types.html#1973" class="Function">has-decidable-equality-is-finite</a><a id="1176" class="Symbol">)</a>
<a id="1178" class="Keyword">open</a> <a id="1183" class="Keyword">import</a> <a id="1190" href="univalent-combinatorics.equality-standard-finite-types.html" class="Module">univalent-combinatorics.equality-standard-finite-types</a> <a id="1245" class="Keyword">using</a>
  <a id="1253" class="Symbol">(</a> <a id="1255" href="univalent-combinatorics.equality-standard-finite-types.html#2796" class="Function">has-decidable-equality-Fin</a><a id="1281" class="Symbol">)</a>
<a id="1283" class="Keyword">open</a> <a id="1288" class="Keyword">import</a> <a id="1295" href="univalent-combinatorics.finite-types.html" class="Module">univalent-combinatorics.finite-types</a> <a id="1332" class="Keyword">using</a>
  <a id="1340" class="Symbol">(</a> <a id="1342" href="univalent-combinatorics.finite-types.html#3664" class="Function">is-finite</a><a id="1351" class="Symbol">)</a>
<a id="1353" class="Keyword">open</a> <a id="1358" class="Keyword">import</a> <a id="1365" href="univalent-combinatorics.standard-finite-types.html" class="Module">univalent-combinatorics.standard-finite-types</a> <a id="1411" class="Keyword">using</a> <a id="1417" class="Symbol">(</a><a id="1418" href="univalent-combinatorics.standard-finite-types.html#2085" class="Function">Fin</a><a id="1421" class="Symbol">)</a>
</pre>
## Properties

### If a map `i : A → Fin k` has a retraction, then it is a decidable map

<pre class="Agda"><a id="is-decidable-map-retr-Fin"></a><a id="1526" href="univalent-combinatorics.retracts-of-finite-types.html#1526" class="Function">is-decidable-map-retr-Fin</a> <a id="1552" class="Symbol">:</a>
  <a id="1556" class="Symbol">{</a><a id="1557" href="univalent-combinatorics.retracts-of-finite-types.html#1557" class="Bound">l1</a> <a id="1560" class="Symbol">:</a> <a id="1562" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="1567" class="Symbol">}</a> <a id="1569" class="Symbol">{</a><a id="1570" href="univalent-combinatorics.retracts-of-finite-types.html#1570" class="Bound">k</a> <a id="1572" class="Symbol">:</a> <a id="1574" href="elementary-number-theory.natural-numbers.html#1444" class="Datatype">ℕ</a><a id="1575" class="Symbol">}</a> <a id="1577" class="Symbol">{</a><a id="1578" href="univalent-combinatorics.retracts-of-finite-types.html#1578" class="Bound">A</a> <a id="1580" class="Symbol">:</a> <a id="1582" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="1585" href="univalent-combinatorics.retracts-of-finite-types.html#1557" class="Bound">l1</a><a id="1587" class="Symbol">}</a> <a id="1589" class="Symbol">(</a><a id="1590" href="univalent-combinatorics.retracts-of-finite-types.html#1590" class="Bound">i</a> <a id="1592" class="Symbol">:</a> <a id="1594" href="univalent-combinatorics.retracts-of-finite-types.html#1578" class="Bound">A</a> <a id="1596" class="Symbol">→</a> <a id="1598" href="univalent-combinatorics.standard-finite-types.html#2085" class="Function">Fin</a> <a id="1602" href="univalent-combinatorics.retracts-of-finite-types.html#1570" class="Bound">k</a><a id="1603" class="Symbol">)</a> <a id="1605" class="Symbol">→</a> <a id="1607" href="foundation-core.retractions.html#593" class="Function">retr</a> <a id="1612" href="univalent-combinatorics.retracts-of-finite-types.html#1590" class="Bound">i</a> <a id="1614" class="Symbol">→</a> <a id="1616" href="foundation.decidable-maps.html#758" class="Function">is-decidable-map</a> <a id="1633" href="univalent-combinatorics.retracts-of-finite-types.html#1590" class="Bound">i</a>
<a id="1635" href="univalent-combinatorics.retracts-of-finite-types.html#1526" class="Function">is-decidable-map-retr-Fin</a> <a id="1661" class="Symbol">=</a>
  <a id="1665" href="foundation.decidable-maps.html#869" class="Function">is-decidable-map-retr</a> <a id="1687" href="univalent-combinatorics.equality-standard-finite-types.html#2796" class="Function">has-decidable-equality-Fin</a>
</pre>
### If a map `i : A → B` into a finite type `B` has a retraction, then `i` is decidable and `A` is finite.

<pre class="Agda"><a id="is-decidable-map-retr-count"></a><a id="1835" href="univalent-combinatorics.retracts-of-finite-types.html#1835" class="Function">is-decidable-map-retr-count</a> <a id="1863" class="Symbol">:</a>
  <a id="1867" class="Symbol">{</a><a id="1868" href="univalent-combinatorics.retracts-of-finite-types.html#1868" class="Bound">l1</a> <a id="1871" href="univalent-combinatorics.retracts-of-finite-types.html#1871" class="Bound">l2</a> <a id="1874" class="Symbol">:</a> <a id="1876" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="1881" class="Symbol">}</a> <a id="1883" class="Symbol">{</a><a id="1884" href="univalent-combinatorics.retracts-of-finite-types.html#1884" class="Bound">A</a> <a id="1886" class="Symbol">:</a> <a id="1888" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="1891" href="univalent-combinatorics.retracts-of-finite-types.html#1868" class="Bound">l1</a><a id="1893" class="Symbol">}</a> <a id="1895" class="Symbol">{</a><a id="1896" href="univalent-combinatorics.retracts-of-finite-types.html#1896" class="Bound">B</a> <a id="1898" class="Symbol">:</a> <a id="1900" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="1903" href="univalent-combinatorics.retracts-of-finite-types.html#1871" class="Bound">l2</a><a id="1905" class="Symbol">}</a> <a id="1907" class="Symbol">(</a><a id="1908" href="univalent-combinatorics.retracts-of-finite-types.html#1908" class="Bound">e</a> <a id="1910" class="Symbol">:</a> <a id="1912" href="univalent-combinatorics.counting.html#1759" class="Function">count</a> <a id="1918" href="univalent-combinatorics.retracts-of-finite-types.html#1896" class="Bound">B</a><a id="1919" class="Symbol">)</a> <a id="1921" class="Symbol">(</a><a id="1922" href="univalent-combinatorics.retracts-of-finite-types.html#1922" class="Bound">i</a> <a id="1924" class="Symbol">:</a> <a id="1926" href="univalent-combinatorics.retracts-of-finite-types.html#1884" class="Bound">A</a> <a id="1928" class="Symbol">→</a> <a id="1930" href="univalent-combinatorics.retracts-of-finite-types.html#1896" class="Bound">B</a><a id="1931" class="Symbol">)</a> <a id="1933" class="Symbol">→</a> <a id="1935" href="foundation-core.retractions.html#593" class="Function">retr</a> <a id="1940" href="univalent-combinatorics.retracts-of-finite-types.html#1922" class="Bound">i</a> <a id="1942" class="Symbol">→</a>
  <a id="1946" href="foundation.decidable-maps.html#758" class="Function">is-decidable-map</a> <a id="1963" href="univalent-combinatorics.retracts-of-finite-types.html#1922" class="Bound">i</a>
<a id="1965" href="univalent-combinatorics.retracts-of-finite-types.html#1835" class="Function">is-decidable-map-retr-count</a> <a id="1993" href="univalent-combinatorics.retracts-of-finite-types.html#1993" class="Bound">e</a> <a id="1995" class="Symbol">=</a>
  <a id="1999" href="foundation.decidable-maps.html#869" class="Function">is-decidable-map-retr</a> <a id="2021" class="Symbol">(</a><a id="2022" href="univalent-combinatorics.counting.html#5721" class="Function">has-decidable-equality-count</a> <a id="2051" href="univalent-combinatorics.retracts-of-finite-types.html#1993" class="Bound">e</a><a id="2052" class="Symbol">)</a>

<a id="is-decidable-map-retr-is-finite"></a><a id="2055" href="univalent-combinatorics.retracts-of-finite-types.html#2055" class="Function">is-decidable-map-retr-is-finite</a> <a id="2087" class="Symbol">:</a>
  <a id="2091" class="Symbol">{</a><a id="2092" href="univalent-combinatorics.retracts-of-finite-types.html#2092" class="Bound">l1</a> <a id="2095" href="univalent-combinatorics.retracts-of-finite-types.html#2095" class="Bound">l2</a> <a id="2098" class="Symbol">:</a> <a id="2100" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="2105" class="Symbol">}</a> <a id="2107" class="Symbol">{</a><a id="2108" href="univalent-combinatorics.retracts-of-finite-types.html#2108" class="Bound">A</a> <a id="2110" class="Symbol">:</a> <a id="2112" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="2115" href="univalent-combinatorics.retracts-of-finite-types.html#2092" class="Bound">l1</a><a id="2117" class="Symbol">}</a> <a id="2119" class="Symbol">{</a><a id="2120" href="univalent-combinatorics.retracts-of-finite-types.html#2120" class="Bound">B</a> <a id="2122" class="Symbol">:</a> <a id="2124" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="2127" href="univalent-combinatorics.retracts-of-finite-types.html#2095" class="Bound">l2</a><a id="2129" class="Symbol">}</a> <a id="2131" class="Symbol">(</a><a id="2132" href="univalent-combinatorics.retracts-of-finite-types.html#2132" class="Bound">H</a> <a id="2134" class="Symbol">:</a> <a id="2136" href="univalent-combinatorics.finite-types.html#3664" class="Function">is-finite</a> <a id="2146" href="univalent-combinatorics.retracts-of-finite-types.html#2120" class="Bound">B</a><a id="2147" class="Symbol">)</a> <a id="2149" class="Symbol">(</a><a id="2150" href="univalent-combinatorics.retracts-of-finite-types.html#2150" class="Bound">i</a> <a id="2152" class="Symbol">:</a> <a id="2154" href="univalent-combinatorics.retracts-of-finite-types.html#2108" class="Bound">A</a> <a id="2156" class="Symbol">→</a> <a id="2158" href="univalent-combinatorics.retracts-of-finite-types.html#2120" class="Bound">B</a><a id="2159" class="Symbol">)</a> <a id="2161" class="Symbol">→</a>
  <a id="2165" href="foundation-core.retractions.html#593" class="Function">retr</a> <a id="2170" href="univalent-combinatorics.retracts-of-finite-types.html#2150" class="Bound">i</a> <a id="2172" class="Symbol">→</a> <a id="2174" href="foundation.decidable-maps.html#758" class="Function">is-decidable-map</a> <a id="2191" href="univalent-combinatorics.retracts-of-finite-types.html#2150" class="Bound">i</a>
<a id="2193" href="univalent-combinatorics.retracts-of-finite-types.html#2055" class="Function">is-decidable-map-retr-is-finite</a> <a id="2225" href="univalent-combinatorics.retracts-of-finite-types.html#2225" class="Bound">H</a> <a id="2227" class="Symbol">=</a>
  <a id="2231" href="foundation.decidable-maps.html#869" class="Function">is-decidable-map-retr</a> <a id="2253" class="Symbol">(</a><a id="2254" href="univalent-combinatorics.equality-finite-types.html#1973" class="Function">has-decidable-equality-is-finite</a> <a id="2287" href="univalent-combinatorics.retracts-of-finite-types.html#2225" class="Bound">H</a><a id="2288" class="Symbol">)</a>
</pre>
<pre class="Agda"><a id="2303" class="Keyword">abstract</a>
  <a id="is-emb-retract-count"></a><a id="2314" href="univalent-combinatorics.retracts-of-finite-types.html#2314" class="Function">is-emb-retract-count</a> <a id="2335" class="Symbol">:</a>
    <a id="2341" class="Symbol">{</a><a id="2342" href="univalent-combinatorics.retracts-of-finite-types.html#2342" class="Bound">l1</a> <a id="2345" href="univalent-combinatorics.retracts-of-finite-types.html#2345" class="Bound">l2</a> <a id="2348" class="Symbol">:</a> <a id="2350" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="2355" class="Symbol">}</a> <a id="2357" class="Symbol">{</a><a id="2358" href="univalent-combinatorics.retracts-of-finite-types.html#2358" class="Bound">A</a> <a id="2360" class="Symbol">:</a> <a id="2362" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="2365" href="univalent-combinatorics.retracts-of-finite-types.html#2342" class="Bound">l1</a><a id="2367" class="Symbol">}</a> <a id="2369" class="Symbol">{</a><a id="2370" href="univalent-combinatorics.retracts-of-finite-types.html#2370" class="Bound">B</a> <a id="2372" class="Symbol">:</a> <a id="2374" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="2377" href="univalent-combinatorics.retracts-of-finite-types.html#2345" class="Bound">l2</a><a id="2379" class="Symbol">}</a> <a id="2381" class="Symbol">(</a><a id="2382" href="univalent-combinatorics.retracts-of-finite-types.html#2382" class="Bound">e</a> <a id="2384" class="Symbol">:</a> <a id="2386" href="univalent-combinatorics.counting.html#1759" class="Function">count</a> <a id="2392" href="univalent-combinatorics.retracts-of-finite-types.html#2370" class="Bound">B</a><a id="2393" class="Symbol">)</a> <a id="2395" class="Symbol">(</a><a id="2396" href="univalent-combinatorics.retracts-of-finite-types.html#2396" class="Bound">i</a> <a id="2398" class="Symbol">:</a> <a id="2400" href="univalent-combinatorics.retracts-of-finite-types.html#2358" class="Bound">A</a> <a id="2402" class="Symbol">→</a> <a id="2404" href="univalent-combinatorics.retracts-of-finite-types.html#2370" class="Bound">B</a><a id="2405" class="Symbol">)</a> <a id="2407" class="Symbol">→</a>
    <a id="2413" href="foundation-core.retractions.html#593" class="Function">retr</a> <a id="2418" href="univalent-combinatorics.retracts-of-finite-types.html#2396" class="Bound">i</a> <a id="2420" class="Symbol">→</a> <a id="2422" href="foundation-core.embeddings.html#980" class="Function">is-emb</a> <a id="2429" href="univalent-combinatorics.retracts-of-finite-types.html#2396" class="Bound">i</a>
  <a id="2433" href="univalent-combinatorics.retracts-of-finite-types.html#2314" class="Function">is-emb-retract-count</a> <a id="2454" href="univalent-combinatorics.retracts-of-finite-types.html#2454" class="Bound">e</a> <a id="2456" href="univalent-combinatorics.retracts-of-finite-types.html#2456" class="Bound">i</a> <a id="2458" href="univalent-combinatorics.retracts-of-finite-types.html#2458" class="Bound">R</a> <a id="2460" class="Symbol">=</a>
    <a id="2466" href="foundation.injective-maps.html#4595" class="Function">is-emb-is-injective</a> <a id="2486" class="Symbol">(</a><a id="2487" href="univalent-combinatorics.counting.html#2336" class="Function">is-set-count</a> <a id="2500" href="univalent-combinatorics.retracts-of-finite-types.html#2454" class="Bound">e</a><a id="2501" class="Symbol">)</a> <a id="2503" class="Symbol">(</a><a id="2504" href="foundation.retractions.html#2840" class="Function">is-injective-retr</a> <a id="2522" href="univalent-combinatorics.retracts-of-finite-types.html#2456" class="Bound">i</a> <a id="2524" href="univalent-combinatorics.retracts-of-finite-types.html#2458" class="Bound">R</a><a id="2525" class="Symbol">)</a>

<a id="emb-retract-count"></a><a id="2528" href="univalent-combinatorics.retracts-of-finite-types.html#2528" class="Function">emb-retract-count</a> <a id="2546" class="Symbol">:</a>
  <a id="2550" class="Symbol">{</a><a id="2551" href="univalent-combinatorics.retracts-of-finite-types.html#2551" class="Bound">l1</a> <a id="2554" href="univalent-combinatorics.retracts-of-finite-types.html#2554" class="Bound">l2</a> <a id="2557" class="Symbol">:</a> <a id="2559" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="2564" class="Symbol">}</a> <a id="2566" class="Symbol">{</a><a id="2567" href="univalent-combinatorics.retracts-of-finite-types.html#2567" class="Bound">A</a> <a id="2569" class="Symbol">:</a> <a id="2571" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="2574" href="univalent-combinatorics.retracts-of-finite-types.html#2551" class="Bound">l1</a><a id="2576" class="Symbol">}</a> <a id="2578" class="Symbol">{</a><a id="2579" href="univalent-combinatorics.retracts-of-finite-types.html#2579" class="Bound">B</a> <a id="2581" class="Symbol">:</a> <a id="2583" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="2586" href="univalent-combinatorics.retracts-of-finite-types.html#2554" class="Bound">l2</a><a id="2588" class="Symbol">}</a> <a id="2590" class="Symbol">(</a><a id="2591" href="univalent-combinatorics.retracts-of-finite-types.html#2591" class="Bound">e</a> <a id="2593" class="Symbol">:</a> <a id="2595" href="univalent-combinatorics.counting.html#1759" class="Function">count</a> <a id="2601" href="univalent-combinatorics.retracts-of-finite-types.html#2579" class="Bound">B</a><a id="2602" class="Symbol">)</a> <a id="2604" class="Symbol">(</a><a id="2605" href="univalent-combinatorics.retracts-of-finite-types.html#2605" class="Bound">i</a> <a id="2607" class="Symbol">:</a> <a id="2609" href="univalent-combinatorics.retracts-of-finite-types.html#2567" class="Bound">A</a> <a id="2611" class="Symbol">→</a> <a id="2613" href="univalent-combinatorics.retracts-of-finite-types.html#2579" class="Bound">B</a><a id="2614" class="Symbol">)</a> <a id="2616" class="Symbol">→</a>
  <a id="2620" href="foundation-core.retractions.html#593" class="Function">retr</a> <a id="2625" href="univalent-combinatorics.retracts-of-finite-types.html#2605" class="Bound">i</a> <a id="2627" class="Symbol">→</a> <a id="2629" href="univalent-combinatorics.retracts-of-finite-types.html#2567" class="Bound">A</a> <a id="2631" href="foundation-core.embeddings.html#1062" class="Function Operator">↪</a> <a id="2633" href="univalent-combinatorics.retracts-of-finite-types.html#2579" class="Bound">B</a>
<a id="2635" href="foundation-core.dependent-pair-types.html#592" class="Field">pr1</a> <a id="2639" class="Symbol">(</a><a id="2640" href="univalent-combinatorics.retracts-of-finite-types.html#2528" class="Function">emb-retract-count</a> <a id="2658" href="univalent-combinatorics.retracts-of-finite-types.html#2658" class="Bound">e</a> <a id="2660" href="univalent-combinatorics.retracts-of-finite-types.html#2660" class="Bound">i</a> <a id="2662" href="univalent-combinatorics.retracts-of-finite-types.html#2662" class="Bound">R</a><a id="2663" class="Symbol">)</a> <a id="2665" class="Symbol">=</a> <a id="2667" href="univalent-combinatorics.retracts-of-finite-types.html#2660" class="Bound">i</a>
<a id="2669" href="foundation-core.dependent-pair-types.html#604" class="Field">pr2</a> <a id="2673" class="Symbol">(</a><a id="2674" href="univalent-combinatorics.retracts-of-finite-types.html#2528" class="Function">emb-retract-count</a> <a id="2692" href="univalent-combinatorics.retracts-of-finite-types.html#2692" class="Bound">e</a> <a id="2694" href="univalent-combinatorics.retracts-of-finite-types.html#2694" class="Bound">i</a> <a id="2696" href="univalent-combinatorics.retracts-of-finite-types.html#2696" class="Bound">R</a><a id="2697" class="Symbol">)</a> <a id="2699" class="Symbol">=</a> <a id="2701" href="univalent-combinatorics.retracts-of-finite-types.html#2314" class="Function">is-emb-retract-count</a> <a id="2722" href="univalent-combinatorics.retracts-of-finite-types.html#2692" class="Bound">e</a> <a id="2724" href="univalent-combinatorics.retracts-of-finite-types.html#2694" class="Bound">i</a> <a id="2726" href="univalent-combinatorics.retracts-of-finite-types.html#2696" class="Bound">R</a>

<a id="count-retract"></a><a id="2729" href="univalent-combinatorics.retracts-of-finite-types.html#2729" class="Function">count-retract</a> <a id="2743" class="Symbol">:</a>
  <a id="2747" class="Symbol">{</a><a id="2748" href="univalent-combinatorics.retracts-of-finite-types.html#2748" class="Bound">l1</a> <a id="2751" href="univalent-combinatorics.retracts-of-finite-types.html#2751" class="Bound">l2</a> <a id="2754" class="Symbol">:</a> <a id="2756" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="2761" class="Symbol">}</a> <a id="2763" class="Symbol">{</a><a id="2764" href="univalent-combinatorics.retracts-of-finite-types.html#2764" class="Bound">A</a> <a id="2766" class="Symbol">:</a> <a id="2768" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="2771" href="univalent-combinatorics.retracts-of-finite-types.html#2748" class="Bound">l1</a><a id="2773" class="Symbol">}</a> <a id="2775" class="Symbol">{</a><a id="2776" href="univalent-combinatorics.retracts-of-finite-types.html#2776" class="Bound">B</a> <a id="2778" class="Symbol">:</a> <a id="2780" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="2783" href="univalent-combinatorics.retracts-of-finite-types.html#2751" class="Bound">l2</a><a id="2785" class="Symbol">}</a> <a id="2787" class="Symbol">→</a>
  <a id="2791" href="univalent-combinatorics.retracts-of-finite-types.html#2764" class="Bound">A</a> <a id="2793" href="foundation-core.retractions.html#670" class="Function Operator">retract-of</a> <a id="2804" href="univalent-combinatorics.retracts-of-finite-types.html#2776" class="Bound">B</a> <a id="2806" class="Symbol">→</a> <a id="2808" href="univalent-combinatorics.counting.html#1759" class="Function">count</a> <a id="2814" href="univalent-combinatorics.retracts-of-finite-types.html#2776" class="Bound">B</a> <a id="2816" class="Symbol">→</a> <a id="2818" href="univalent-combinatorics.counting.html#1759" class="Function">count</a> <a id="2824" href="univalent-combinatorics.retracts-of-finite-types.html#2764" class="Bound">A</a>
<a id="2826" href="univalent-combinatorics.retracts-of-finite-types.html#2729" class="Function">count-retract</a> <a id="2840" class="Symbol">(</a><a id="2841" href="foundation-core.dependent-pair-types.html#575" class="InductiveConstructor">pair</a> <a id="2846" href="univalent-combinatorics.retracts-of-finite-types.html#2846" class="Bound">i</a> <a id="2848" href="univalent-combinatorics.retracts-of-finite-types.html#2848" class="Bound">R</a><a id="2849" class="Symbol">)</a> <a id="2851" href="univalent-combinatorics.retracts-of-finite-types.html#2851" class="Bound">e</a> <a id="2853" class="Symbol">=</a>
  <a id="2857" href="univalent-combinatorics.counting.html#2974" class="Function">count-equiv</a>
    <a id="2873" class="Symbol">(</a> <a id="2875" href="foundation-core.fibers-of-maps.html#5261" class="Function">equiv-total-fib</a> <a id="2891" href="univalent-combinatorics.retracts-of-finite-types.html#2846" class="Bound">i</a><a id="2892" class="Symbol">)</a>
    <a id="2898" class="Symbol">(</a> <a id="2900" href="univalent-combinatorics.counting-decidable-subtypes.html#6686" class="Function">count-decidable-subtype</a>
      <a id="2930" class="Symbol">(</a> <a id="2932" href="foundation-core.propositional-maps.html#2460" class="Function">fib-emb-Prop</a> <a id="2945" class="Symbol">(</a><a id="2946" href="univalent-combinatorics.retracts-of-finite-types.html#2528" class="Function">emb-retract-count</a> <a id="2964" href="univalent-combinatorics.retracts-of-finite-types.html#2851" class="Bound">e</a> <a id="2966" href="univalent-combinatorics.retracts-of-finite-types.html#2846" class="Bound">i</a> <a id="2968" href="univalent-combinatorics.retracts-of-finite-types.html#2848" class="Bound">R</a><a id="2969" class="Symbol">))</a>
      <a id="2978" class="Symbol">(</a> <a id="2980" href="univalent-combinatorics.retracts-of-finite-types.html#1835" class="Function">is-decidable-map-retr-count</a> <a id="3008" href="univalent-combinatorics.retracts-of-finite-types.html#2851" class="Bound">e</a> <a id="3010" href="univalent-combinatorics.retracts-of-finite-types.html#2846" class="Bound">i</a> <a id="3012" href="univalent-combinatorics.retracts-of-finite-types.html#2848" class="Bound">R</a><a id="3013" class="Symbol">)</a>
      <a id="3021" class="Symbol">(</a> <a id="3023" href="univalent-combinatorics.retracts-of-finite-types.html#2851" class="Bound">e</a><a id="3024" class="Symbol">))</a>

<a id="3028" class="Keyword">abstract</a>
  <a id="is-finite-retract"></a><a id="3039" href="univalent-combinatorics.retracts-of-finite-types.html#3039" class="Function">is-finite-retract</a> <a id="3057" class="Symbol">:</a>
    <a id="3063" class="Symbol">{</a><a id="3064" href="univalent-combinatorics.retracts-of-finite-types.html#3064" class="Bound">l1</a> <a id="3067" href="univalent-combinatorics.retracts-of-finite-types.html#3067" class="Bound">l2</a> <a id="3070" class="Symbol">:</a> <a id="3072" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="3077" class="Symbol">}</a> <a id="3079" class="Symbol">{</a><a id="3080" href="univalent-combinatorics.retracts-of-finite-types.html#3080" class="Bound">A</a> <a id="3082" class="Symbol">:</a> <a id="3084" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="3087" href="univalent-combinatorics.retracts-of-finite-types.html#3064" class="Bound">l1</a><a id="3089" class="Symbol">}</a> <a id="3091" class="Symbol">{</a><a id="3092" href="univalent-combinatorics.retracts-of-finite-types.html#3092" class="Bound">B</a> <a id="3094" class="Symbol">:</a> <a id="3096" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="3099" href="univalent-combinatorics.retracts-of-finite-types.html#3067" class="Bound">l2</a><a id="3101" class="Symbol">}</a> <a id="3103" class="Symbol">→</a> <a id="3105" href="univalent-combinatorics.retracts-of-finite-types.html#3080" class="Bound">A</a> <a id="3107" href="foundation-core.retractions.html#670" class="Function Operator">retract-of</a> <a id="3118" href="univalent-combinatorics.retracts-of-finite-types.html#3092" class="Bound">B</a> <a id="3120" class="Symbol">→</a>
    <a id="3126" href="univalent-combinatorics.finite-types.html#3664" class="Function">is-finite</a> <a id="3136" href="univalent-combinatorics.retracts-of-finite-types.html#3092" class="Bound">B</a> <a id="3138" class="Symbol">→</a> <a id="3140" href="univalent-combinatorics.finite-types.html#3664" class="Function">is-finite</a> <a id="3150" href="univalent-combinatorics.retracts-of-finite-types.html#3080" class="Bound">A</a>
  <a id="3154" href="univalent-combinatorics.retracts-of-finite-types.html#3039" class="Function">is-finite-retract</a> <a id="3172" href="univalent-combinatorics.retracts-of-finite-types.html#3172" class="Bound">R</a> <a id="3174" class="Symbol">=</a> <a id="3176" href="foundation.functoriality-propositional-truncation.html#1451" class="Function">functor-trunc-Prop</a> <a id="3195" class="Symbol">(</a><a id="3196" href="univalent-combinatorics.retracts-of-finite-types.html#2729" class="Function">count-retract</a> <a id="3210" href="univalent-combinatorics.retracts-of-finite-types.html#3172" class="Bound">R</a><a id="3211" class="Symbol">)</a>
</pre>