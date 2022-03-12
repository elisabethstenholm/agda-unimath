# The universal property of truncations

<pre class="Agda"><a id="50" class="Symbol">{-#</a> <a id="54" class="Keyword">OPTIONS</a> <a id="62" class="Pragma">--without-K</a> <a id="74" class="Pragma">--exact-split</a> <a id="88" class="Symbol">#-}</a>

<a id="93" class="Keyword">module</a> <a id="100" href="foundation.universal-property-truncation.html" class="Module">foundation.universal-property-truncation</a> <a id="141" class="Keyword">where</a>

<a id="148" class="Keyword">open</a> <a id="153" class="Keyword">import</a> <a id="160" href="foundation.contractible-maps.html" class="Module">foundation.contractible-maps</a> <a id="189" class="Keyword">using</a>
  <a id="197" class="Symbol">(</a> <a id="199" href="foundation-core.contractible-maps.html#2368" class="Function">is-equiv-is-contr-map</a><a id="220" class="Symbol">;</a> <a id="222" href="foundation-core.contractible-maps.html#3850" class="Function">is-contr-map-is-equiv</a><a id="243" class="Symbol">)</a>
<a id="245" class="Keyword">open</a> <a id="250" class="Keyword">import</a> <a id="257" href="foundation.contractible-types.html" class="Module">foundation.contractible-types</a> <a id="287" class="Keyword">using</a>
  <a id="295" class="Symbol">(</a> <a id="297" href="foundation-core.contractible-types.html#925" class="Function">is-contr</a><a id="305" class="Symbol">;</a> <a id="307" href="foundation-core.contractible-types.html#3230" class="Function">is-contr-equiv</a><a id="321" class="Symbol">;</a> <a id="323" href="foundation-core.contractible-types.html#3739" class="Function">is-contr-equiv&#39;</a><a id="338" class="Symbol">;</a> <a id="340" href="foundation-core.contractible-types.html#1018" class="Function">center</a><a id="346" class="Symbol">)</a>
<a id="348" class="Keyword">open</a> <a id="353" class="Keyword">import</a> <a id="360" href="foundation.dependent-pair-types.html" class="Module">foundation.dependent-pair-types</a> <a id="392" class="Keyword">using</a> <a id="398" class="Symbol">(</a><a id="399" href="foundation-core.dependent-pair-types.html#502" class="Record">Σ</a><a id="400" class="Symbol">;</a> <a id="402" href="foundation-core.dependent-pair-types.html#575" class="InductiveConstructor">pair</a><a id="406" class="Symbol">;</a> <a id="408" href="foundation-core.dependent-pair-types.html#592" class="Field">pr1</a><a id="411" class="Symbol">;</a> <a id="413" href="foundation-core.dependent-pair-types.html#604" class="Field">pr2</a><a id="416" class="Symbol">;</a> <a id="418" href="foundation-core.dependent-pair-types.html#687" class="Function">ind-Σ</a><a id="423" class="Symbol">)</a>
<a id="425" class="Keyword">open</a> <a id="430" class="Keyword">import</a>
  <a id="439" href="foundation.distributivity-of-dependent-functions-over-dependent-pairs.html" class="Module">foundation.distributivity-of-dependent-functions-over-dependent-pairs</a> <a id="509" class="Keyword">using</a>
  <a id="517" class="Symbol">(</a> <a id="519" href="foundation.distributivity-of-dependent-functions-over-dependent-pairs.html#5106" class="Function">inv-distributive-Π-Σ</a><a id="539" class="Symbol">;</a> <a id="541" href="foundation.distributivity-of-dependent-functions-over-dependent-pairs.html#2808" class="Function">map-distributive-Π-Σ</a><a id="561" class="Symbol">)</a>
<a id="563" class="Keyword">open</a> <a id="568" class="Keyword">import</a> <a id="575" href="foundation.equivalences.html" class="Module">foundation.equivalences</a> <a id="599" class="Keyword">using</a>
  <a id="607" class="Symbol">(</a> <a id="609" href="foundation-core.equivalences.html#1542" class="Function">is-equiv</a><a id="617" class="Symbol">;</a> <a id="619" href="foundation-core.equivalences.html#12773" class="Function">is-equiv-equiv</a><a id="633" class="Symbol">;</a> <a id="635" href="foundation-core.equivalences.html#4173" class="Function">map-inv-is-equiv</a><a id="651" class="Symbol">;</a> <a id="653" href="foundation.equivalences.html#9061" class="Function">is-equiv-precomp-is-equiv</a><a id="678" class="Symbol">;</a>
    <a id="684" href="foundation-core.equivalences.html#2309" class="Function">is-equiv-id</a><a id="695" class="Symbol">;</a> <a id="697" href="foundation-core.equivalences.html#1607" class="Function Operator">_≃_</a><a id="700" class="Symbol">;</a> <a id="702" href="foundation-core.equivalences.html#1807" class="Function">map-equiv</a><a id="711" class="Symbol">;</a> <a id="713" href="foundation-core.equivalences.html#1862" class="Function">is-equiv-map-equiv</a><a id="731" class="Symbol">)</a>
<a id="733" class="Keyword">open</a> <a id="738" class="Keyword">import</a> <a id="745" href="foundation.function-extensionality.html" class="Module">foundation.function-extensionality</a> <a id="780" class="Keyword">using</a> <a id="786" class="Symbol">(</a><a id="787" href="foundation.function-extensionality.html#1283" class="Function">equiv-funext</a><a id="799" class="Symbol">)</a>
<a id="801" class="Keyword">open</a> <a id="806" class="Keyword">import</a> <a id="813" href="foundation.functions.html" class="Module">foundation.functions</a> <a id="834" class="Keyword">using</a> <a id="840" class="Symbol">(</a><a id="841" href="foundation-core.functions.html#925" class="Function">precomp</a><a id="848" class="Symbol">;</a> <a id="850" href="foundation-core.functions.html#407" class="Function Operator">_∘_</a><a id="853" class="Symbol">;</a> <a id="855" href="foundation-core.functions.html#309" class="Function">id</a><a id="857" class="Symbol">)</a>
<a id="859" class="Keyword">open</a> <a id="864" class="Keyword">import</a> <a id="871" href="foundation.functoriality-dependent-pair-types.html" class="Module">foundation.functoriality-dependent-pair-types</a> <a id="917" class="Keyword">using</a>
  <a id="925" class="Symbol">(</a> <a id="927" href="foundation-core.functoriality-dependent-pair-types.html#6804" class="Function">equiv-tot</a><a id="936" class="Symbol">;</a> <a id="938" href="foundation-core.functoriality-dependent-pair-types.html#10750" class="Function">is-fiberwise-equiv-is-equiv-map-Σ</a><a id="971" class="Symbol">)</a>
<a id="973" class="Keyword">open</a> <a id="978" class="Keyword">import</a> <a id="985" href="foundation.homotopies.html" class="Module">foundation.homotopies</a> <a id="1007" class="Keyword">using</a> <a id="1013" class="Symbol">(</a><a id="1014" href="foundation-core.homotopies.html#467" class="Function Operator">_~_</a><a id="1017" class="Symbol">)</a>
<a id="1019" class="Keyword">open</a> <a id="1024" class="Keyword">import</a> <a id="1031" href="foundation.identity-types.html" class="Module">foundation.identity-types</a> <a id="1057" class="Keyword">using</a> <a id="1063" class="Symbol">(</a><a id="1064" href="foundation-core.identity-types.html#641" class="Datatype">Id</a><a id="1066" class="Symbol">;</a> <a id="1068" href="foundation-core.identity-types.html#694" class="InductiveConstructor">refl</a><a id="1072" class="Symbol">;</a> <a id="1074" href="foundation-core.identity-types.html#1552" class="Function">inv</a><a id="1077" class="Symbol">)</a>
<a id="1079" class="Keyword">open</a> <a id="1084" class="Keyword">import</a> <a id="1091" href="foundation.sections.html" class="Module">foundation.sections</a> <a id="1111" class="Keyword">using</a> <a id="1117" class="Symbol">(</a><a id="1118" href="foundation-core.sections.html#521" class="Function">sec</a><a id="1121" class="Symbol">)</a>
<a id="1123" class="Keyword">open</a> <a id="1128" class="Keyword">import</a> <a id="1135" href="foundation.truncated-types.html" class="Module">foundation.truncated-types</a> <a id="1162" class="Keyword">using</a>
  <a id="1170" class="Symbol">(</a> <a id="1172" href="foundation-core.truncated-types.html#1651" class="Function">Truncated-Type</a><a id="1186" class="Symbol">;</a> <a id="1188" href="foundation-core.truncated-types.html#1786" class="Function">type-Truncated-Type</a><a id="1207" class="Symbol">;</a> <a id="1209" href="foundation.truncated-types.html#3483" class="Function">type-hom-Truncated-Type</a><a id="1232" class="Symbol">;</a>
    <a id="1238" href="foundation-core.truncated-types.html#6022" class="Function">Σ-Truncated-Type</a><a id="1254" class="Symbol">;</a> <a id="1256" href="foundation-core.truncated-types.html#6396" class="Function">fib-Truncated-Type</a><a id="1274" class="Symbol">;</a> <a id="1276" href="foundation-core.truncated-types.html#1466" class="Function">is-trunc</a><a id="1284" class="Symbol">)</a>
<a id="1286" class="Keyword">open</a> <a id="1291" class="Keyword">import</a> <a id="1298" href="foundation.truncation-levels.html" class="Module">foundation.truncation-levels</a> <a id="1327" class="Keyword">using</a> <a id="1333" class="Symbol">(</a><a id="1334" href="foundation-core.truncation-levels.html#382" class="Datatype">𝕋</a><a id="1335" class="Symbol">)</a>
<a id="1337" class="Keyword">open</a> <a id="1342" class="Keyword">import</a> <a id="1349" href="foundation.universe-levels.html" class="Module">foundation.universe-levels</a> <a id="1376" class="Keyword">using</a> <a id="1382" class="Symbol">(</a><a id="1383" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a><a id="1385" class="Symbol">;</a> <a id="1387" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="1392" class="Symbol">;</a> <a id="1394" href="Agda.Primitive.html#810" class="Primitive Operator">_⊔_</a><a id="1397" class="Symbol">;</a> <a id="1399" href="Agda.Primitive.html#780" class="Primitive">lsuc</a><a id="1403" class="Symbol">)</a>
</pre>
## Idea

We say that a map `f : A → B` into a `k`-truncated type `B` is a `k`-truncation of `A` -- or that it satisfies the universal property of the `k`-truncation of `A` -- if any map `g : A → C` into a `k`-truncated type `C` extends uniquely along `f` to a map `B → C`.

## Definition

### The condition on a map to be a truncation

<pre class="Agda"><a id="precomp-Trunc"></a><a id="1754" href="foundation.universal-property-truncation.html#1754" class="Function">precomp-Trunc</a> <a id="1768" class="Symbol">:</a>
  <a id="1772" class="Symbol">{</a><a id="1773" href="foundation.universal-property-truncation.html#1773" class="Bound">l1</a> <a id="1776" href="foundation.universal-property-truncation.html#1776" class="Bound">l2</a> <a id="1779" href="foundation.universal-property-truncation.html#1779" class="Bound">l3</a> <a id="1782" class="Symbol">:</a> <a id="1784" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="1789" class="Symbol">}</a> <a id="1791" class="Symbol">{</a><a id="1792" href="foundation.universal-property-truncation.html#1792" class="Bound">k</a> <a id="1794" class="Symbol">:</a> <a id="1796" href="foundation-core.truncation-levels.html#382" class="Datatype">𝕋</a><a id="1797" class="Symbol">}</a> <a id="1799" class="Symbol">{</a><a id="1800" href="foundation.universal-property-truncation.html#1800" class="Bound">A</a> <a id="1802" class="Symbol">:</a> <a id="1804" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="1807" href="foundation.universal-property-truncation.html#1773" class="Bound">l1</a><a id="1809" class="Symbol">}</a> <a id="1811" class="Symbol">{</a><a id="1812" href="foundation.universal-property-truncation.html#1812" class="Bound">B</a> <a id="1814" class="Symbol">:</a> <a id="1816" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="1819" href="foundation.universal-property-truncation.html#1776" class="Bound">l2</a><a id="1821" class="Symbol">}</a> <a id="1823" class="Symbol">(</a><a id="1824" href="foundation.universal-property-truncation.html#1824" class="Bound">f</a> <a id="1826" class="Symbol">:</a> <a id="1828" href="foundation.universal-property-truncation.html#1800" class="Bound">A</a> <a id="1830" class="Symbol">→</a> <a id="1832" href="foundation.universal-property-truncation.html#1812" class="Bound">B</a><a id="1833" class="Symbol">)</a>
  <a id="1837" class="Symbol">(</a><a id="1838" href="foundation.universal-property-truncation.html#1838" class="Bound">C</a> <a id="1840" class="Symbol">:</a> <a id="1842" href="foundation-core.truncated-types.html#1651" class="Function">Truncated-Type</a> <a id="1857" href="foundation.universal-property-truncation.html#1779" class="Bound">l3</a> <a id="1860" href="foundation.universal-property-truncation.html#1792" class="Bound">k</a><a id="1861" class="Symbol">)</a> <a id="1863" class="Symbol">→</a>
  <a id="1867" class="Symbol">(</a><a id="1868" href="foundation.universal-property-truncation.html#1812" class="Bound">B</a> <a id="1870" class="Symbol">→</a> <a id="1872" href="foundation-core.truncated-types.html#1786" class="Function">type-Truncated-Type</a> <a id="1892" href="foundation.universal-property-truncation.html#1838" class="Bound">C</a><a id="1893" class="Symbol">)</a> <a id="1895" class="Symbol">→</a> <a id="1897" class="Symbol">(</a><a id="1898" href="foundation.universal-property-truncation.html#1800" class="Bound">A</a> <a id="1900" class="Symbol">→</a> <a id="1902" href="foundation-core.truncated-types.html#1786" class="Function">type-Truncated-Type</a> <a id="1922" href="foundation.universal-property-truncation.html#1838" class="Bound">C</a><a id="1923" class="Symbol">)</a>
<a id="1925" href="foundation.universal-property-truncation.html#1754" class="Function">precomp-Trunc</a> <a id="1939" href="foundation.universal-property-truncation.html#1939" class="Bound">f</a> <a id="1941" href="foundation.universal-property-truncation.html#1941" class="Bound">C</a> <a id="1943" class="Symbol">=</a> <a id="1945" href="foundation-core.functions.html#925" class="Function">precomp</a> <a id="1953" href="foundation.universal-property-truncation.html#1939" class="Bound">f</a> <a id="1955" class="Symbol">(</a><a id="1956" href="foundation-core.truncated-types.html#1786" class="Function">type-Truncated-Type</a> <a id="1976" href="foundation.universal-property-truncation.html#1941" class="Bound">C</a><a id="1977" class="Symbol">)</a>

<a id="is-truncation"></a><a id="1980" href="foundation.universal-property-truncation.html#1980" class="Function">is-truncation</a> <a id="1994" class="Symbol">:</a>
  <a id="1998" class="Symbol">{</a><a id="1999" href="foundation.universal-property-truncation.html#1999" class="Bound">l1</a> <a id="2002" href="foundation.universal-property-truncation.html#2002" class="Bound">l2</a> <a id="2005" class="Symbol">:</a> <a id="2007" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="2012" class="Symbol">}</a> <a id="2014" class="Symbol">(</a><a id="2015" href="foundation.universal-property-truncation.html#2015" class="Bound">l</a> <a id="2017" class="Symbol">:</a> <a id="2019" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="2024" class="Symbol">)</a> <a id="2026" class="Symbol">{</a><a id="2027" href="foundation.universal-property-truncation.html#2027" class="Bound">k</a> <a id="2029" class="Symbol">:</a> <a id="2031" href="foundation-core.truncation-levels.html#382" class="Datatype">𝕋</a><a id="2032" class="Symbol">}</a> <a id="2034" class="Symbol">{</a><a id="2035" href="foundation.universal-property-truncation.html#2035" class="Bound">A</a> <a id="2037" class="Symbol">:</a> <a id="2039" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="2042" href="foundation.universal-property-truncation.html#1999" class="Bound">l1</a><a id="2044" class="Symbol">}</a>
  <a id="2048" class="Symbol">(</a><a id="2049" href="foundation.universal-property-truncation.html#2049" class="Bound">B</a> <a id="2051" class="Symbol">:</a> <a id="2053" href="foundation-core.truncated-types.html#1651" class="Function">Truncated-Type</a> <a id="2068" href="foundation.universal-property-truncation.html#2002" class="Bound">l2</a> <a id="2071" href="foundation.universal-property-truncation.html#2027" class="Bound">k</a><a id="2072" class="Symbol">)</a> <a id="2074" class="Symbol">→</a> <a id="2076" class="Symbol">(</a><a id="2077" href="foundation.universal-property-truncation.html#2035" class="Bound">A</a> <a id="2079" class="Symbol">→</a> <a id="2081" href="foundation-core.truncated-types.html#1786" class="Function">type-Truncated-Type</a> <a id="2101" href="foundation.universal-property-truncation.html#2049" class="Bound">B</a><a id="2102" class="Symbol">)</a> <a id="2104" class="Symbol">→</a>
  <a id="2108" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="2111" class="Symbol">(</a><a id="2112" href="foundation.universal-property-truncation.html#1999" class="Bound">l1</a> <a id="2115" href="Agda.Primitive.html#810" class="Primitive Operator">⊔</a> <a id="2117" href="foundation.universal-property-truncation.html#2002" class="Bound">l2</a> <a id="2120" href="Agda.Primitive.html#810" class="Primitive Operator">⊔</a> <a id="2122" href="Agda.Primitive.html#780" class="Primitive">lsuc</a> <a id="2127" href="foundation.universal-property-truncation.html#2015" class="Bound">l</a><a id="2128" class="Symbol">)</a>
<a id="2130" href="foundation.universal-property-truncation.html#1980" class="Function">is-truncation</a> <a id="2144" href="foundation.universal-property-truncation.html#2144" class="Bound">l</a> <a id="2146" class="Symbol">{</a><a id="2147" href="foundation.universal-property-truncation.html#2147" class="Bound">k</a><a id="2148" class="Symbol">}</a> <a id="2150" href="foundation.universal-property-truncation.html#2150" class="Bound">B</a> <a id="2152" href="foundation.universal-property-truncation.html#2152" class="Bound">f</a> <a id="2154" class="Symbol">=</a>
  <a id="2158" class="Symbol">(</a><a id="2159" href="foundation.universal-property-truncation.html#2159" class="Bound">C</a> <a id="2161" class="Symbol">:</a> <a id="2163" href="foundation-core.truncated-types.html#1651" class="Function">Truncated-Type</a> <a id="2178" href="foundation.universal-property-truncation.html#2144" class="Bound">l</a> <a id="2180" href="foundation.universal-property-truncation.html#2147" class="Bound">k</a><a id="2181" class="Symbol">)</a> <a id="2183" class="Symbol">→</a> <a id="2185" href="foundation-core.equivalences.html#1542" class="Function">is-equiv</a> <a id="2194" class="Symbol">(</a><a id="2195" href="foundation.universal-property-truncation.html#1754" class="Function">precomp-Trunc</a> <a id="2209" href="foundation.universal-property-truncation.html#2152" class="Bound">f</a> <a id="2211" href="foundation.universal-property-truncation.html#2159" class="Bound">C</a><a id="2212" class="Symbol">)</a>
</pre>
### The universal property of truncations

<pre class="Agda"><a id="universal-property-truncation"></a><a id="2270" href="foundation.universal-property-truncation.html#2270" class="Function">universal-property-truncation</a> <a id="2300" class="Symbol">:</a>
  <a id="2304" class="Symbol">(</a><a id="2305" href="foundation.universal-property-truncation.html#2305" class="Bound">l</a> <a id="2307" class="Symbol">:</a> <a id="2309" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="2314" class="Symbol">)</a> <a id="2316" class="Symbol">{</a><a id="2317" href="foundation.universal-property-truncation.html#2317" class="Bound">l1</a> <a id="2320" href="foundation.universal-property-truncation.html#2320" class="Bound">l2</a> <a id="2323" class="Symbol">:</a> <a id="2325" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="2330" class="Symbol">}</a> <a id="2332" class="Symbol">{</a><a id="2333" href="foundation.universal-property-truncation.html#2333" class="Bound">k</a> <a id="2335" class="Symbol">:</a> <a id="2337" href="foundation-core.truncation-levels.html#382" class="Datatype">𝕋</a><a id="2338" class="Symbol">}</a> <a id="2340" class="Symbol">{</a><a id="2341" href="foundation.universal-property-truncation.html#2341" class="Bound">A</a> <a id="2343" class="Symbol">:</a> <a id="2345" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="2348" href="foundation.universal-property-truncation.html#2317" class="Bound">l1</a><a id="2350" class="Symbol">}</a>
  <a id="2354" class="Symbol">(</a><a id="2355" href="foundation.universal-property-truncation.html#2355" class="Bound">B</a> <a id="2357" class="Symbol">:</a> <a id="2359" href="foundation-core.truncated-types.html#1651" class="Function">Truncated-Type</a> <a id="2374" href="foundation.universal-property-truncation.html#2320" class="Bound">l2</a> <a id="2377" href="foundation.universal-property-truncation.html#2333" class="Bound">k</a><a id="2378" class="Symbol">)</a> <a id="2380" class="Symbol">(</a><a id="2381" href="foundation.universal-property-truncation.html#2381" class="Bound">f</a> <a id="2383" class="Symbol">:</a> <a id="2385" href="foundation.universal-property-truncation.html#2341" class="Bound">A</a> <a id="2387" class="Symbol">→</a> <a id="2389" href="foundation-core.truncated-types.html#1786" class="Function">type-Truncated-Type</a> <a id="2409" href="foundation.universal-property-truncation.html#2355" class="Bound">B</a><a id="2410" class="Symbol">)</a> <a id="2412" class="Symbol">→</a>
  <a id="2416" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="2419" class="Symbol">(</a><a id="2420" href="Agda.Primitive.html#780" class="Primitive">lsuc</a> <a id="2425" href="foundation.universal-property-truncation.html#2305" class="Bound">l</a> <a id="2427" href="Agda.Primitive.html#810" class="Primitive Operator">⊔</a> <a id="2429" href="foundation.universal-property-truncation.html#2317" class="Bound">l1</a> <a id="2432" href="Agda.Primitive.html#810" class="Primitive Operator">⊔</a> <a id="2434" href="foundation.universal-property-truncation.html#2320" class="Bound">l2</a><a id="2436" class="Symbol">)</a>
<a id="2438" href="foundation.universal-property-truncation.html#2270" class="Function">universal-property-truncation</a> <a id="2468" href="foundation.universal-property-truncation.html#2468" class="Bound">l</a> <a id="2470" class="Symbol">{</a><a id="2471" class="Argument">k</a> <a id="2473" class="Symbol">=</a> <a id="2475" href="foundation.universal-property-truncation.html#2475" class="Bound">k</a><a id="2476" class="Symbol">}</a> <a id="2478" class="Symbol">{</a><a id="2479" href="foundation.universal-property-truncation.html#2479" class="Bound">A</a><a id="2480" class="Symbol">}</a> <a id="2482" href="foundation.universal-property-truncation.html#2482" class="Bound">B</a> <a id="2484" href="foundation.universal-property-truncation.html#2484" class="Bound">f</a> <a id="2486" class="Symbol">=</a>
  <a id="2490" class="Symbol">(</a><a id="2491" href="foundation.universal-property-truncation.html#2491" class="Bound">C</a> <a id="2493" class="Symbol">:</a> <a id="2495" href="foundation-core.truncated-types.html#1651" class="Function">Truncated-Type</a> <a id="2510" href="foundation.universal-property-truncation.html#2468" class="Bound">l</a> <a id="2512" href="foundation.universal-property-truncation.html#2475" class="Bound">k</a><a id="2513" class="Symbol">)</a> <a id="2515" class="Symbol">(</a><a id="2516" href="foundation.universal-property-truncation.html#2516" class="Bound">g</a> <a id="2518" class="Symbol">:</a> <a id="2520" href="foundation.universal-property-truncation.html#2479" class="Bound">A</a> <a id="2522" class="Symbol">→</a> <a id="2524" href="foundation-core.truncated-types.html#1786" class="Function">type-Truncated-Type</a> <a id="2544" href="foundation.universal-property-truncation.html#2491" class="Bound">C</a><a id="2545" class="Symbol">)</a> <a id="2547" class="Symbol">→</a>
  <a id="2551" href="foundation-core.contractible-types.html#925" class="Function">is-contr</a> <a id="2560" class="Symbol">(</a><a id="2561" href="foundation-core.dependent-pair-types.html#502" class="Record">Σ</a> <a id="2563" class="Symbol">(</a><a id="2564" href="foundation.truncated-types.html#3483" class="Function">type-hom-Truncated-Type</a> <a id="2588" href="foundation.universal-property-truncation.html#2475" class="Bound">k</a> <a id="2590" href="foundation.universal-property-truncation.html#2482" class="Bound">B</a> <a id="2592" href="foundation.universal-property-truncation.html#2491" class="Bound">C</a><a id="2593" class="Symbol">)</a> <a id="2595" class="Symbol">(λ</a> <a id="2598" href="foundation.universal-property-truncation.html#2598" class="Bound">h</a> <a id="2600" class="Symbol">→</a> <a id="2602" class="Symbol">(</a><a id="2603" href="foundation.universal-property-truncation.html#2598" class="Bound">h</a> <a id="2605" href="foundation-core.functions.html#407" class="Function Operator">∘</a> <a id="2607" href="foundation.universal-property-truncation.html#2484" class="Bound">f</a><a id="2608" class="Symbol">)</a> <a id="2610" href="foundation-core.homotopies.html#467" class="Function Operator">~</a> <a id="2612" href="foundation.universal-property-truncation.html#2516" class="Bound">g</a><a id="2613" class="Symbol">))</a>
</pre>
### The dependent universal property of truncations

<pre class="Agda"><a id="precomp-Π-Truncated-Type"></a><a id="2678" href="foundation.universal-property-truncation.html#2678" class="Function">precomp-Π-Truncated-Type</a> <a id="2703" class="Symbol">:</a>
  <a id="2707" class="Symbol">{</a><a id="2708" href="foundation.universal-property-truncation.html#2708" class="Bound">l1</a> <a id="2711" href="foundation.universal-property-truncation.html#2711" class="Bound">l2</a> <a id="2714" href="foundation.universal-property-truncation.html#2714" class="Bound">l3</a> <a id="2717" class="Symbol">:</a> <a id="2719" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="2724" class="Symbol">}</a> <a id="2726" class="Symbol">{</a><a id="2727" href="foundation.universal-property-truncation.html#2727" class="Bound">k</a> <a id="2729" class="Symbol">:</a> <a id="2731" href="foundation-core.truncation-levels.html#382" class="Datatype">𝕋</a><a id="2732" class="Symbol">}</a> <a id="2734" class="Symbol">{</a><a id="2735" href="foundation.universal-property-truncation.html#2735" class="Bound">A</a> <a id="2737" class="Symbol">:</a> <a id="2739" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="2742" href="foundation.universal-property-truncation.html#2708" class="Bound">l1</a><a id="2744" class="Symbol">}</a> <a id="2746" class="Symbol">{</a><a id="2747" href="foundation.universal-property-truncation.html#2747" class="Bound">B</a> <a id="2749" class="Symbol">:</a> <a id="2751" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="2754" href="foundation.universal-property-truncation.html#2711" class="Bound">l2</a><a id="2756" class="Symbol">}</a> <a id="2758" class="Symbol">(</a><a id="2759" href="foundation.universal-property-truncation.html#2759" class="Bound">f</a> <a id="2761" class="Symbol">:</a> <a id="2763" href="foundation.universal-property-truncation.html#2735" class="Bound">A</a> <a id="2765" class="Symbol">→</a> <a id="2767" href="foundation.universal-property-truncation.html#2747" class="Bound">B</a><a id="2768" class="Symbol">)</a>
  <a id="2772" class="Symbol">(</a><a id="2773" href="foundation.universal-property-truncation.html#2773" class="Bound">C</a> <a id="2775" class="Symbol">:</a> <a id="2777" href="foundation.universal-property-truncation.html#2747" class="Bound">B</a> <a id="2779" class="Symbol">→</a> <a id="2781" href="foundation-core.truncated-types.html#1651" class="Function">Truncated-Type</a> <a id="2796" href="foundation.universal-property-truncation.html#2714" class="Bound">l3</a> <a id="2799" href="foundation.universal-property-truncation.html#2727" class="Bound">k</a><a id="2800" class="Symbol">)</a> <a id="2802" class="Symbol">→</a>
  <a id="2806" class="Symbol">((</a><a id="2808" href="foundation.universal-property-truncation.html#2808" class="Bound">b</a> <a id="2810" class="Symbol">:</a> <a id="2812" href="foundation.universal-property-truncation.html#2747" class="Bound">B</a><a id="2813" class="Symbol">)</a> <a id="2815" class="Symbol">→</a> <a id="2817" href="foundation-core.truncated-types.html#1786" class="Function">type-Truncated-Type</a> <a id="2837" class="Symbol">(</a><a id="2838" href="foundation.universal-property-truncation.html#2773" class="Bound">C</a> <a id="2840" href="foundation.universal-property-truncation.html#2808" class="Bound">b</a><a id="2841" class="Symbol">))</a> <a id="2844" class="Symbol">→</a>
  <a id="2848" class="Symbol">((</a><a id="2850" href="foundation.universal-property-truncation.html#2850" class="Bound">a</a> <a id="2852" class="Symbol">:</a> <a id="2854" href="foundation.universal-property-truncation.html#2735" class="Bound">A</a><a id="2855" class="Symbol">)</a> <a id="2857" class="Symbol">→</a> <a id="2859" href="foundation-core.truncated-types.html#1786" class="Function">type-Truncated-Type</a> <a id="2879" class="Symbol">(</a><a id="2880" href="foundation.universal-property-truncation.html#2773" class="Bound">C</a> <a id="2882" class="Symbol">(</a><a id="2883" href="foundation.universal-property-truncation.html#2759" class="Bound">f</a> <a id="2885" href="foundation.universal-property-truncation.html#2850" class="Bound">a</a><a id="2886" class="Symbol">)))</a>
<a id="2890" href="foundation.universal-property-truncation.html#2678" class="Function">precomp-Π-Truncated-Type</a> <a id="2915" href="foundation.universal-property-truncation.html#2915" class="Bound">f</a> <a id="2917" href="foundation.universal-property-truncation.html#2917" class="Bound">C</a> <a id="2919" href="foundation.universal-property-truncation.html#2919" class="Bound">h</a> <a id="2921" href="foundation.universal-property-truncation.html#2921" class="Bound">a</a> <a id="2923" class="Symbol">=</a> <a id="2925" href="foundation.universal-property-truncation.html#2919" class="Bound">h</a> <a id="2927" class="Symbol">(</a><a id="2928" href="foundation.universal-property-truncation.html#2915" class="Bound">f</a> <a id="2930" href="foundation.universal-property-truncation.html#2921" class="Bound">a</a><a id="2931" class="Symbol">)</a>

<a id="dependent-universal-property-truncation"></a><a id="2934" href="foundation.universal-property-truncation.html#2934" class="Function">dependent-universal-property-truncation</a> <a id="2974" class="Symbol">:</a>
  <a id="2978" class="Symbol">{</a><a id="2979" href="foundation.universal-property-truncation.html#2979" class="Bound">l1</a> <a id="2982" href="foundation.universal-property-truncation.html#2982" class="Bound">l2</a> <a id="2985" class="Symbol">:</a> <a id="2987" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="2992" class="Symbol">}</a> <a id="2994" class="Symbol">(</a><a id="2995" href="foundation.universal-property-truncation.html#2995" class="Bound">l</a> <a id="2997" class="Symbol">:</a> <a id="2999" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="3004" class="Symbol">)</a> <a id="3006" class="Symbol">{</a><a id="3007" href="foundation.universal-property-truncation.html#3007" class="Bound">k</a> <a id="3009" class="Symbol">:</a> <a id="3011" href="foundation-core.truncation-levels.html#382" class="Datatype">𝕋</a><a id="3012" class="Symbol">}</a> <a id="3014" class="Symbol">{</a><a id="3015" href="foundation.universal-property-truncation.html#3015" class="Bound">A</a> <a id="3017" class="Symbol">:</a> <a id="3019" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="3022" href="foundation.universal-property-truncation.html#2979" class="Bound">l1</a><a id="3024" class="Symbol">}</a> <a id="3026" class="Symbol">(</a><a id="3027" href="foundation.universal-property-truncation.html#3027" class="Bound">B</a> <a id="3029" class="Symbol">:</a> <a id="3031" href="foundation-core.truncated-types.html#1651" class="Function">Truncated-Type</a> <a id="3046" href="foundation.universal-property-truncation.html#2982" class="Bound">l2</a> <a id="3049" href="foundation.universal-property-truncation.html#3007" class="Bound">k</a><a id="3050" class="Symbol">)</a>
  <a id="3054" class="Symbol">(</a><a id="3055" href="foundation.universal-property-truncation.html#3055" class="Bound">f</a> <a id="3057" class="Symbol">:</a> <a id="3059" href="foundation.universal-property-truncation.html#3015" class="Bound">A</a> <a id="3061" class="Symbol">→</a> <a id="3063" href="foundation-core.truncated-types.html#1786" class="Function">type-Truncated-Type</a> <a id="3083" href="foundation.universal-property-truncation.html#3027" class="Bound">B</a><a id="3084" class="Symbol">)</a> <a id="3086" class="Symbol">→</a> <a id="3088" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="3091" class="Symbol">(</a><a id="3092" href="foundation.universal-property-truncation.html#2979" class="Bound">l1</a> <a id="3095" href="Agda.Primitive.html#810" class="Primitive Operator">⊔</a> <a id="3097" href="foundation.universal-property-truncation.html#2982" class="Bound">l2</a> <a id="3100" href="Agda.Primitive.html#810" class="Primitive Operator">⊔</a> <a id="3102" href="Agda.Primitive.html#780" class="Primitive">lsuc</a> <a id="3107" href="foundation.universal-property-truncation.html#2995" class="Bound">l</a><a id="3108" class="Symbol">)</a>
<a id="3110" href="foundation.universal-property-truncation.html#2934" class="Function">dependent-universal-property-truncation</a> <a id="3150" href="foundation.universal-property-truncation.html#3150" class="Bound">l</a> <a id="3152" class="Symbol">{</a><a id="3153" href="foundation.universal-property-truncation.html#3153" class="Bound">k</a><a id="3154" class="Symbol">}</a> <a id="3156" href="foundation.universal-property-truncation.html#3156" class="Bound">B</a> <a id="3158" href="foundation.universal-property-truncation.html#3158" class="Bound">f</a> <a id="3160" class="Symbol">=</a>
  <a id="3164" class="Symbol">(</a><a id="3165" href="foundation.universal-property-truncation.html#3165" class="Bound">X</a> <a id="3167" class="Symbol">:</a> <a id="3169" href="foundation-core.truncated-types.html#1786" class="Function">type-Truncated-Type</a> <a id="3189" href="foundation.universal-property-truncation.html#3156" class="Bound">B</a> <a id="3191" class="Symbol">→</a> <a id="3193" href="foundation-core.truncated-types.html#1651" class="Function">Truncated-Type</a> <a id="3208" href="foundation.universal-property-truncation.html#3150" class="Bound">l</a> <a id="3210" href="foundation.universal-property-truncation.html#3153" class="Bound">k</a><a id="3211" class="Symbol">)</a> <a id="3213" class="Symbol">→</a>
  <a id="3217" href="foundation-core.equivalences.html#1542" class="Function">is-equiv</a> <a id="3226" class="Symbol">(</a><a id="3227" href="foundation.universal-property-truncation.html#2678" class="Function">precomp-Π-Truncated-Type</a> <a id="3252" href="foundation.universal-property-truncation.html#3158" class="Bound">f</a> <a id="3254" href="foundation.universal-property-truncation.html#3165" class="Bound">X</a><a id="3255" class="Symbol">)</a>
</pre>
## Properties

### Equivalences into `k`-truncated types are truncations

<pre class="Agda"><a id="3344" class="Keyword">abstract</a>
  <a id="is-truncation-id"></a><a id="3355" href="foundation.universal-property-truncation.html#3355" class="Function">is-truncation-id</a> <a id="3372" class="Symbol">:</a>
    <a id="3378" class="Symbol">{</a><a id="3379" href="foundation.universal-property-truncation.html#3379" class="Bound">l1</a> <a id="3382" class="Symbol">:</a> <a id="3384" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="3389" class="Symbol">}</a> <a id="3391" class="Symbol">{</a><a id="3392" href="foundation.universal-property-truncation.html#3392" class="Bound">k</a> <a id="3394" class="Symbol">:</a> <a id="3396" href="foundation-core.truncation-levels.html#382" class="Datatype">𝕋</a><a id="3397" class="Symbol">}</a> <a id="3399" class="Symbol">{</a><a id="3400" href="foundation.universal-property-truncation.html#3400" class="Bound">A</a> <a id="3402" class="Symbol">:</a> <a id="3404" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="3407" href="foundation.universal-property-truncation.html#3379" class="Bound">l1</a><a id="3409" class="Symbol">}</a> <a id="3411" class="Symbol">(</a><a id="3412" href="foundation.universal-property-truncation.html#3412" class="Bound">H</a> <a id="3414" class="Symbol">:</a> <a id="3416" href="foundation-core.truncated-types.html#1466" class="Function">is-trunc</a> <a id="3425" href="foundation.universal-property-truncation.html#3392" class="Bound">k</a> <a id="3427" href="foundation.universal-property-truncation.html#3400" class="Bound">A</a><a id="3428" class="Symbol">)</a> <a id="3430" class="Symbol">→</a>
    <a id="3436" class="Symbol">{</a><a id="3437" href="foundation.universal-property-truncation.html#3437" class="Bound">l</a> <a id="3439" class="Symbol">:</a> <a id="3441" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="3446" class="Symbol">}</a> <a id="3448" class="Symbol">→</a> <a id="3450" href="foundation.universal-property-truncation.html#1980" class="Function">is-truncation</a> <a id="3464" href="foundation.universal-property-truncation.html#3437" class="Bound">l</a> <a id="3466" class="Symbol">(</a><a id="3467" href="foundation-core.dependent-pair-types.html#575" class="InductiveConstructor">pair</a> <a id="3472" href="foundation.universal-property-truncation.html#3400" class="Bound">A</a> <a id="3474" href="foundation.universal-property-truncation.html#3412" class="Bound">H</a><a id="3475" class="Symbol">)</a> <a id="3477" href="foundation-core.functions.html#309" class="Function">id</a>
  <a id="3482" href="foundation.universal-property-truncation.html#3355" class="Function">is-truncation-id</a> <a id="3499" href="foundation.universal-property-truncation.html#3499" class="Bound">H</a> <a id="3501" href="foundation.universal-property-truncation.html#3501" class="Bound">B</a> <a id="3503" class="Symbol">=</a>
    <a id="3509" href="foundation.equivalences.html#9061" class="Function">is-equiv-precomp-is-equiv</a> <a id="3535" href="foundation-core.functions.html#309" class="Function">id</a> <a id="3538" href="foundation-core.equivalences.html#2309" class="Function">is-equiv-id</a> <a id="3550" class="Symbol">(</a><a id="3551" href="foundation-core.truncated-types.html#1786" class="Function">type-Truncated-Type</a> <a id="3571" href="foundation.universal-property-truncation.html#3501" class="Bound">B</a><a id="3572" class="Symbol">)</a>

<a id="3575" class="Keyword">abstract</a>
  <a id="is-truncation-equiv"></a><a id="3586" href="foundation.universal-property-truncation.html#3586" class="Function">is-truncation-equiv</a> <a id="3606" class="Symbol">:</a>
    <a id="3612" class="Symbol">{</a><a id="3613" href="foundation.universal-property-truncation.html#3613" class="Bound">l1</a> <a id="3616" href="foundation.universal-property-truncation.html#3616" class="Bound">l2</a> <a id="3619" class="Symbol">:</a> <a id="3621" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="3626" class="Symbol">}</a> <a id="3628" class="Symbol">{</a><a id="3629" href="foundation.universal-property-truncation.html#3629" class="Bound">k</a> <a id="3631" class="Symbol">:</a> <a id="3633" href="foundation-core.truncation-levels.html#382" class="Datatype">𝕋</a><a id="3634" class="Symbol">}</a> <a id="3636" class="Symbol">{</a><a id="3637" href="foundation.universal-property-truncation.html#3637" class="Bound">A</a> <a id="3639" class="Symbol">:</a> <a id="3641" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="3644" href="foundation.universal-property-truncation.html#3613" class="Bound">l1</a><a id="3646" class="Symbol">}</a> <a id="3648" class="Symbol">(</a><a id="3649" href="foundation.universal-property-truncation.html#3649" class="Bound">B</a> <a id="3651" class="Symbol">:</a> <a id="3653" href="foundation-core.truncated-types.html#1651" class="Function">Truncated-Type</a> <a id="3668" href="foundation.universal-property-truncation.html#3616" class="Bound">l2</a> <a id="3671" href="foundation.universal-property-truncation.html#3629" class="Bound">k</a><a id="3672" class="Symbol">)</a>
    <a id="3678" class="Symbol">(</a><a id="3679" href="foundation.universal-property-truncation.html#3679" class="Bound">e</a> <a id="3681" class="Symbol">:</a> <a id="3683" href="foundation.universal-property-truncation.html#3637" class="Bound">A</a> <a id="3685" href="foundation-core.equivalences.html#1607" class="Function Operator">≃</a> <a id="3687" href="foundation-core.truncated-types.html#1786" class="Function">type-Truncated-Type</a> <a id="3707" href="foundation.universal-property-truncation.html#3649" class="Bound">B</a><a id="3708" class="Symbol">)</a> <a id="3710" class="Symbol">→</a>
    <a id="3716" class="Symbol">{</a><a id="3717" href="foundation.universal-property-truncation.html#3717" class="Bound">l</a> <a id="3719" class="Symbol">:</a> <a id="3721" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="3726" class="Symbol">}</a> <a id="3728" class="Symbol">→</a> <a id="3730" href="foundation.universal-property-truncation.html#1980" class="Function">is-truncation</a> <a id="3744" href="foundation.universal-property-truncation.html#3717" class="Bound">l</a> <a id="3746" href="foundation.universal-property-truncation.html#3649" class="Bound">B</a> <a id="3748" class="Symbol">(</a><a id="3749" href="foundation-core.equivalences.html#1807" class="Function">map-equiv</a> <a id="3759" href="foundation.universal-property-truncation.html#3679" class="Bound">e</a><a id="3760" class="Symbol">)</a>
  <a id="3764" href="foundation.universal-property-truncation.html#3586" class="Function">is-truncation-equiv</a> <a id="3784" href="foundation.universal-property-truncation.html#3784" class="Bound">B</a> <a id="3786" href="foundation.universal-property-truncation.html#3786" class="Bound">e</a> <a id="3788" href="foundation.universal-property-truncation.html#3788" class="Bound">C</a> <a id="3790" class="Symbol">=</a>
    <a id="3796" href="foundation.equivalences.html#9061" class="Function">is-equiv-precomp-is-equiv</a>
      <a id="3828" class="Symbol">(</a> <a id="3830" href="foundation-core.equivalences.html#1807" class="Function">map-equiv</a> <a id="3840" href="foundation.universal-property-truncation.html#3786" class="Bound">e</a><a id="3841" class="Symbol">)</a>
      <a id="3849" class="Symbol">(</a> <a id="3851" href="foundation-core.equivalences.html#1862" class="Function">is-equiv-map-equiv</a> <a id="3870" href="foundation.universal-property-truncation.html#3786" class="Bound">e</a><a id="3871" class="Symbol">)</a>
      <a id="3879" class="Symbol">(</a> <a id="3881" href="foundation-core.truncated-types.html#1786" class="Function">type-Truncated-Type</a> <a id="3901" href="foundation.universal-property-truncation.html#3788" class="Bound">C</a><a id="3902" class="Symbol">)</a>
</pre>
### A map into a truncated type is a truncation if and only if it satisfies the universal property of the truncation

<pre class="Agda"><a id="4035" class="Keyword">module</a> <a id="4042" href="foundation.universal-property-truncation.html#4042" class="Module">_</a>
  <a id="4046" class="Symbol">{</a><a id="4047" href="foundation.universal-property-truncation.html#4047" class="Bound">l1</a> <a id="4050" href="foundation.universal-property-truncation.html#4050" class="Bound">l2</a> <a id="4053" class="Symbol">:</a> <a id="4055" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="4060" class="Symbol">}</a> <a id="4062" class="Symbol">{</a><a id="4063" href="foundation.universal-property-truncation.html#4063" class="Bound">k</a> <a id="4065" class="Symbol">:</a> <a id="4067" href="foundation-core.truncation-levels.html#382" class="Datatype">𝕋</a><a id="4068" class="Symbol">}</a> <a id="4070" class="Symbol">{</a><a id="4071" href="foundation.universal-property-truncation.html#4071" class="Bound">A</a> <a id="4073" class="Symbol">:</a> <a id="4075" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="4078" href="foundation.universal-property-truncation.html#4047" class="Bound">l1</a><a id="4080" class="Symbol">}</a> <a id="4082" class="Symbol">(</a><a id="4083" href="foundation.universal-property-truncation.html#4083" class="Bound">B</a> <a id="4085" class="Symbol">:</a> <a id="4087" href="foundation-core.truncated-types.html#1651" class="Function">Truncated-Type</a> <a id="4102" href="foundation.universal-property-truncation.html#4050" class="Bound">l2</a> <a id="4105" href="foundation.universal-property-truncation.html#4063" class="Bound">k</a><a id="4106" class="Symbol">)</a>
  <a id="4110" class="Symbol">(</a><a id="4111" href="foundation.universal-property-truncation.html#4111" class="Bound">f</a> <a id="4113" class="Symbol">:</a> <a id="4115" href="foundation.universal-property-truncation.html#4071" class="Bound">A</a> <a id="4117" class="Symbol">→</a> <a id="4119" href="foundation-core.truncated-types.html#1786" class="Function">type-Truncated-Type</a> <a id="4139" href="foundation.universal-property-truncation.html#4083" class="Bound">B</a><a id="4140" class="Symbol">)</a>
  <a id="4144" class="Keyword">where</a>

  <a id="4153" class="Keyword">abstract</a>
    <a id="4166" href="foundation.universal-property-truncation.html#4166" class="Function">is-truncation-universal-property-truncation</a> <a id="4210" class="Symbol">:</a>
      <a id="4218" class="Symbol">({</a><a id="4220" href="foundation.universal-property-truncation.html#4220" class="Bound">l</a> <a id="4222" class="Symbol">:</a> <a id="4224" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="4229" class="Symbol">}</a> <a id="4231" class="Symbol">→</a> <a id="4233" href="foundation.universal-property-truncation.html#2270" class="Function">universal-property-truncation</a> <a id="4263" href="foundation.universal-property-truncation.html#4220" class="Bound">l</a> <a id="4265" href="foundation.universal-property-truncation.html#4083" class="Bound">B</a> <a id="4267" href="foundation.universal-property-truncation.html#4111" class="Bound">f</a><a id="4268" class="Symbol">)</a> <a id="4270" class="Symbol">→</a>
      <a id="4278" class="Symbol">({</a><a id="4280" href="foundation.universal-property-truncation.html#4280" class="Bound">l</a> <a id="4282" class="Symbol">:</a> <a id="4284" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="4289" class="Symbol">}</a> <a id="4291" class="Symbol">→</a> <a id="4293" href="foundation.universal-property-truncation.html#1980" class="Function">is-truncation</a> <a id="4307" href="foundation.universal-property-truncation.html#4280" class="Bound">l</a> <a id="4309" href="foundation.universal-property-truncation.html#4083" class="Bound">B</a> <a id="4311" href="foundation.universal-property-truncation.html#4111" class="Bound">f</a><a id="4312" class="Symbol">)</a>
    <a id="4318" href="foundation.universal-property-truncation.html#4166" class="Function">is-truncation-universal-property-truncation</a> <a id="4362" href="foundation.universal-property-truncation.html#4362" class="Bound">H</a> <a id="4364" href="foundation.universal-property-truncation.html#4364" class="Bound">C</a> <a id="4366" class="Symbol">=</a>
      <a id="4374" href="foundation-core.contractible-maps.html#2368" class="Function">is-equiv-is-contr-map</a>
        <a id="4404" class="Symbol">(</a> <a id="4406" class="Symbol">λ</a> <a id="4408" href="foundation.universal-property-truncation.html#4408" class="Bound">g</a> <a id="4410" class="Symbol">→</a>
          <a id="4422" href="foundation-core.contractible-types.html#3230" class="Function">is-contr-equiv</a>
            <a id="4449" class="Symbol">(</a> <a id="4451" href="foundation-core.dependent-pair-types.html#502" class="Record">Σ</a> <a id="4453" class="Symbol">(</a><a id="4454" href="foundation.truncated-types.html#3483" class="Function">type-hom-Truncated-Type</a> <a id="4478" href="foundation.universal-property-truncation.html#4063" class="Bound">k</a> <a id="4480" href="foundation.universal-property-truncation.html#4083" class="Bound">B</a> <a id="4482" href="foundation.universal-property-truncation.html#4364" class="Bound">C</a><a id="4483" class="Symbol">)</a> <a id="4485" class="Symbol">(λ</a> <a id="4488" href="foundation.universal-property-truncation.html#4488" class="Bound">h</a> <a id="4490" class="Symbol">→</a> <a id="4492" class="Symbol">(</a><a id="4493" href="foundation.universal-property-truncation.html#4488" class="Bound">h</a> <a id="4495" href="foundation-core.functions.html#407" class="Function Operator">∘</a> <a id="4497" href="foundation.universal-property-truncation.html#4111" class="Bound">f</a><a id="4498" class="Symbol">)</a> <a id="4500" href="foundation-core.homotopies.html#467" class="Function Operator">~</a> <a id="4502" href="foundation.universal-property-truncation.html#4408" class="Bound">g</a><a id="4503" class="Symbol">))</a>
            <a id="4518" class="Symbol">(</a> <a id="4520" href="foundation-core.functoriality-dependent-pair-types.html#6804" class="Function">equiv-tot</a> <a id="4530" class="Symbol">(λ</a> <a id="4533" href="foundation.universal-property-truncation.html#4533" class="Bound">h</a> <a id="4535" class="Symbol">→</a> <a id="4537" href="foundation.function-extensionality.html#1283" class="Function">equiv-funext</a><a id="4549" class="Symbol">))</a>
            <a id="4564" class="Symbol">(</a> <a id="4566" href="foundation.universal-property-truncation.html#4362" class="Bound">H</a> <a id="4568" href="foundation.universal-property-truncation.html#4364" class="Bound">C</a> <a id="4570" href="foundation.universal-property-truncation.html#4408" class="Bound">g</a><a id="4571" class="Symbol">))</a>

  <a id="4577" class="Keyword">abstract</a>
    <a id="4590" href="foundation.universal-property-truncation.html#4590" class="Function">universal-property-truncation-is-truncation</a> <a id="4634" class="Symbol">:</a>
      <a id="4642" class="Symbol">({</a><a id="4644" href="foundation.universal-property-truncation.html#4644" class="Bound">l</a> <a id="4646" class="Symbol">:</a> <a id="4648" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="4653" class="Symbol">}</a> <a id="4655" class="Symbol">→</a> <a id="4657" href="foundation.universal-property-truncation.html#1980" class="Function">is-truncation</a> <a id="4671" href="foundation.universal-property-truncation.html#4644" class="Bound">l</a> <a id="4673" href="foundation.universal-property-truncation.html#4083" class="Bound">B</a> <a id="4675" href="foundation.universal-property-truncation.html#4111" class="Bound">f</a><a id="4676" class="Symbol">)</a> <a id="4678" class="Symbol">→</a>
      <a id="4686" class="Symbol">({</a><a id="4688" href="foundation.universal-property-truncation.html#4688" class="Bound">l</a> <a id="4690" class="Symbol">:</a> <a id="4692" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="4697" class="Symbol">}</a> <a id="4699" class="Symbol">→</a> <a id="4701" href="foundation.universal-property-truncation.html#2270" class="Function">universal-property-truncation</a> <a id="4731" href="foundation.universal-property-truncation.html#4688" class="Bound">l</a> <a id="4733" href="foundation.universal-property-truncation.html#4083" class="Bound">B</a> <a id="4735" href="foundation.universal-property-truncation.html#4111" class="Bound">f</a><a id="4736" class="Symbol">)</a>
    <a id="4742" href="foundation.universal-property-truncation.html#4590" class="Function">universal-property-truncation-is-truncation</a> <a id="4786" href="foundation.universal-property-truncation.html#4786" class="Bound">H</a> <a id="4788" href="foundation.universal-property-truncation.html#4788" class="Bound">C</a> <a id="4790" href="foundation.universal-property-truncation.html#4790" class="Bound">g</a> <a id="4792" class="Symbol">=</a>
      <a id="4800" href="foundation-core.contractible-types.html#3739" class="Function">is-contr-equiv&#39;</a>
        <a id="4824" class="Symbol">(</a> <a id="4826" href="foundation-core.dependent-pair-types.html#502" class="Record">Σ</a> <a id="4828" class="Symbol">(</a><a id="4829" href="foundation.truncated-types.html#3483" class="Function">type-hom-Truncated-Type</a> <a id="4853" href="foundation.universal-property-truncation.html#4063" class="Bound">k</a> <a id="4855" href="foundation.universal-property-truncation.html#4083" class="Bound">B</a> <a id="4857" href="foundation.universal-property-truncation.html#4788" class="Bound">C</a><a id="4858" class="Symbol">)</a> <a id="4860" class="Symbol">(λ</a> <a id="4863" href="foundation.universal-property-truncation.html#4863" class="Bound">h</a> <a id="4865" class="Symbol">→</a> <a id="4867" href="foundation-core.identity-types.html#641" class="Datatype">Id</a> <a id="4870" class="Symbol">(</a><a id="4871" href="foundation.universal-property-truncation.html#4863" class="Bound">h</a> <a id="4873" href="foundation-core.functions.html#407" class="Function Operator">∘</a> <a id="4875" href="foundation.universal-property-truncation.html#4111" class="Bound">f</a><a id="4876" class="Symbol">)</a> <a id="4878" href="foundation.universal-property-truncation.html#4790" class="Bound">g</a><a id="4879" class="Symbol">))</a>
        <a id="4890" class="Symbol">(</a> <a id="4892" href="foundation-core.functoriality-dependent-pair-types.html#6804" class="Function">equiv-tot</a> <a id="4902" class="Symbol">(λ</a> <a id="4905" href="foundation.universal-property-truncation.html#4905" class="Bound">h</a> <a id="4907" class="Symbol">→</a> <a id="4909" href="foundation.function-extensionality.html#1283" class="Function">equiv-funext</a><a id="4921" class="Symbol">))</a>
        <a id="4932" class="Symbol">(</a> <a id="4934" href="foundation-core.contractible-maps.html#3850" class="Function">is-contr-map-is-equiv</a> <a id="4956" class="Symbol">(</a><a id="4957" href="foundation.universal-property-truncation.html#4786" class="Bound">H</a> <a id="4959" href="foundation.universal-property-truncation.html#4788" class="Bound">C</a><a id="4960" class="Symbol">)</a> <a id="4962" href="foundation.universal-property-truncation.html#4790" class="Bound">g</a><a id="4963" class="Symbol">)</a>

  <a id="4968" href="foundation.universal-property-truncation.html#4968" class="Function">map-is-truncation</a> <a id="4986" class="Symbol">:</a>
    <a id="4992" class="Symbol">({</a><a id="4994" href="foundation.universal-property-truncation.html#4994" class="Bound">l</a> <a id="4996" class="Symbol">:</a> <a id="4998" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="5003" class="Symbol">}</a> <a id="5005" class="Symbol">→</a> <a id="5007" href="foundation.universal-property-truncation.html#1980" class="Function">is-truncation</a> <a id="5021" href="foundation.universal-property-truncation.html#4994" class="Bound">l</a> <a id="5023" href="foundation.universal-property-truncation.html#4083" class="Bound">B</a> <a id="5025" href="foundation.universal-property-truncation.html#4111" class="Bound">f</a><a id="5026" class="Symbol">)</a> <a id="5028" class="Symbol">→</a>
    <a id="5034" class="Symbol">({</a><a id="5036" href="foundation.universal-property-truncation.html#5036" class="Bound">l</a> <a id="5038" class="Symbol">:</a> <a id="5040" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="5045" class="Symbol">}</a> <a id="5047" class="Symbol">(</a><a id="5048" href="foundation.universal-property-truncation.html#5048" class="Bound">C</a> <a id="5050" class="Symbol">:</a> <a id="5052" href="foundation-core.truncated-types.html#1651" class="Function">Truncated-Type</a> <a id="5067" href="foundation.universal-property-truncation.html#5036" class="Bound">l</a> <a id="5069" href="foundation.universal-property-truncation.html#4063" class="Bound">k</a><a id="5070" class="Symbol">)</a> <a id="5072" class="Symbol">(</a><a id="5073" href="foundation.universal-property-truncation.html#5073" class="Bound">g</a> <a id="5075" class="Symbol">:</a> <a id="5077" href="foundation.universal-property-truncation.html#4071" class="Bound">A</a> <a id="5079" class="Symbol">→</a> <a id="5081" href="foundation-core.truncated-types.html#1786" class="Function">type-Truncated-Type</a> <a id="5101" href="foundation.universal-property-truncation.html#5048" class="Bound">C</a><a id="5102" class="Symbol">)</a> <a id="5104" class="Symbol">→</a>
    <a id="5110" href="foundation.truncated-types.html#3483" class="Function">type-hom-Truncated-Type</a> <a id="5134" href="foundation.universal-property-truncation.html#4063" class="Bound">k</a> <a id="5136" href="foundation.universal-property-truncation.html#4083" class="Bound">B</a> <a id="5138" href="foundation.universal-property-truncation.html#5048" class="Bound">C</a><a id="5139" class="Symbol">)</a>
  <a id="5143" href="foundation.universal-property-truncation.html#4968" class="Function">map-is-truncation</a> <a id="5161" href="foundation.universal-property-truncation.html#5161" class="Bound">H</a> <a id="5163" href="foundation.universal-property-truncation.html#5163" class="Bound">C</a> <a id="5165" href="foundation.universal-property-truncation.html#5165" class="Bound">g</a> <a id="5167" class="Symbol">=</a>
    <a id="5173" href="foundation-core.dependent-pair-types.html#592" class="Field">pr1</a> <a id="5177" class="Symbol">(</a><a id="5178" href="foundation-core.contractible-types.html#1018" class="Function">center</a> <a id="5185" class="Symbol">(</a><a id="5186" href="foundation.universal-property-truncation.html#4590" class="Function">universal-property-truncation-is-truncation</a> <a id="5230" href="foundation.universal-property-truncation.html#5161" class="Bound">H</a> <a id="5232" href="foundation.universal-property-truncation.html#5163" class="Bound">C</a> <a id="5234" href="foundation.universal-property-truncation.html#5165" class="Bound">g</a><a id="5235" class="Symbol">))</a>

  <a id="5241" href="foundation.universal-property-truncation.html#5241" class="Function">triangle-is-truncation</a> <a id="5264" class="Symbol">:</a>
    <a id="5270" class="Symbol">(</a><a id="5271" href="foundation.universal-property-truncation.html#5271" class="Bound">H</a> <a id="5273" class="Symbol">:</a> <a id="5275" class="Symbol">{</a><a id="5276" href="foundation.universal-property-truncation.html#5276" class="Bound">l</a> <a id="5278" class="Symbol">:</a> <a id="5280" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="5285" class="Symbol">}</a> <a id="5287" class="Symbol">→</a> <a id="5289" href="foundation.universal-property-truncation.html#1980" class="Function">is-truncation</a> <a id="5303" href="foundation.universal-property-truncation.html#5276" class="Bound">l</a> <a id="5305" href="foundation.universal-property-truncation.html#4083" class="Bound">B</a> <a id="5307" href="foundation.universal-property-truncation.html#4111" class="Bound">f</a><a id="5308" class="Symbol">)</a> <a id="5310" class="Symbol">→</a>
    <a id="5316" class="Symbol">{</a><a id="5317" href="foundation.universal-property-truncation.html#5317" class="Bound">l</a> <a id="5319" class="Symbol">:</a> <a id="5321" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="5326" class="Symbol">}</a> <a id="5328" class="Symbol">(</a><a id="5329" href="foundation.universal-property-truncation.html#5329" class="Bound">C</a> <a id="5331" class="Symbol">:</a> <a id="5333" href="foundation-core.truncated-types.html#1651" class="Function">Truncated-Type</a> <a id="5348" href="foundation.universal-property-truncation.html#5317" class="Bound">l</a> <a id="5350" href="foundation.universal-property-truncation.html#4063" class="Bound">k</a><a id="5351" class="Symbol">)</a> <a id="5353" class="Symbol">(</a><a id="5354" href="foundation.universal-property-truncation.html#5354" class="Bound">g</a> <a id="5356" class="Symbol">:</a> <a id="5358" href="foundation.universal-property-truncation.html#4071" class="Bound">A</a> <a id="5360" class="Symbol">→</a> <a id="5362" href="foundation-core.truncated-types.html#1786" class="Function">type-Truncated-Type</a> <a id="5382" href="foundation.universal-property-truncation.html#5329" class="Bound">C</a><a id="5383" class="Symbol">)</a> <a id="5385" class="Symbol">→</a>
    <a id="5391" class="Symbol">(</a><a id="5392" href="foundation.universal-property-truncation.html#4968" class="Function">map-is-truncation</a> <a id="5410" href="foundation.universal-property-truncation.html#5271" class="Bound">H</a> <a id="5412" href="foundation.universal-property-truncation.html#5329" class="Bound">C</a> <a id="5414" href="foundation.universal-property-truncation.html#5354" class="Bound">g</a> <a id="5416" href="foundation-core.functions.html#407" class="Function Operator">∘</a> <a id="5418" href="foundation.universal-property-truncation.html#4111" class="Bound">f</a><a id="5419" class="Symbol">)</a> <a id="5421" href="foundation-core.homotopies.html#467" class="Function Operator">~</a> <a id="5423" href="foundation.universal-property-truncation.html#5354" class="Bound">g</a>
  <a id="5427" href="foundation.universal-property-truncation.html#5241" class="Function">triangle-is-truncation</a> <a id="5450" href="foundation.universal-property-truncation.html#5450" class="Bound">H</a> <a id="5452" href="foundation.universal-property-truncation.html#5452" class="Bound">C</a> <a id="5454" href="foundation.universal-property-truncation.html#5454" class="Bound">g</a> <a id="5456" class="Symbol">=</a>
    <a id="5462" href="foundation-core.dependent-pair-types.html#604" class="Field">pr2</a> <a id="5466" class="Symbol">(</a><a id="5467" href="foundation-core.contractible-types.html#1018" class="Function">center</a> <a id="5474" class="Symbol">(</a><a id="5475" href="foundation.universal-property-truncation.html#4590" class="Function">universal-property-truncation-is-truncation</a> <a id="5519" href="foundation.universal-property-truncation.html#5450" class="Bound">H</a> <a id="5521" href="foundation.universal-property-truncation.html#5452" class="Bound">C</a> <a id="5523" href="foundation.universal-property-truncation.html#5454" class="Bound">g</a><a id="5524" class="Symbol">))</a>
</pre>
### A map into a truncated type is a truncation if and only if it satisfies the dependent universal property of the truncation

<pre class="Agda"><a id="5668" class="Keyword">module</a> <a id="5675" href="foundation.universal-property-truncation.html#5675" class="Module">_</a>
  <a id="5679" class="Symbol">{</a><a id="5680" href="foundation.universal-property-truncation.html#5680" class="Bound">l1</a> <a id="5683" href="foundation.universal-property-truncation.html#5683" class="Bound">l2</a> <a id="5686" class="Symbol">:</a> <a id="5688" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="5693" class="Symbol">}</a> <a id="5695" class="Symbol">{</a><a id="5696" href="foundation.universal-property-truncation.html#5696" class="Bound">k</a> <a id="5698" class="Symbol">:</a> <a id="5700" href="foundation-core.truncation-levels.html#382" class="Datatype">𝕋</a><a id="5701" class="Symbol">}</a> <a id="5703" class="Symbol">{</a><a id="5704" href="foundation.universal-property-truncation.html#5704" class="Bound">A</a> <a id="5706" class="Symbol">:</a> <a id="5708" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="5711" href="foundation.universal-property-truncation.html#5680" class="Bound">l1</a><a id="5713" class="Symbol">}</a> <a id="5715" class="Symbol">(</a><a id="5716" href="foundation.universal-property-truncation.html#5716" class="Bound">B</a> <a id="5718" class="Symbol">:</a> <a id="5720" href="foundation-core.truncated-types.html#1651" class="Function">Truncated-Type</a> <a id="5735" href="foundation.universal-property-truncation.html#5683" class="Bound">l2</a> <a id="5738" href="foundation.universal-property-truncation.html#5696" class="Bound">k</a><a id="5739" class="Symbol">)</a>
  <a id="5743" class="Symbol">(</a><a id="5744" href="foundation.universal-property-truncation.html#5744" class="Bound">f</a> <a id="5746" class="Symbol">:</a> <a id="5748" href="foundation.universal-property-truncation.html#5704" class="Bound">A</a> <a id="5750" class="Symbol">→</a> <a id="5752" href="foundation-core.truncated-types.html#1786" class="Function">type-Truncated-Type</a> <a id="5772" href="foundation.universal-property-truncation.html#5716" class="Bound">B</a><a id="5773" class="Symbol">)</a>
  <a id="5777" class="Keyword">where</a>

  <a id="5786" class="Keyword">abstract</a>
    <a id="5799" href="foundation.universal-property-truncation.html#5799" class="Function">dependent-universal-property-truncation-is-truncation</a> <a id="5853" class="Symbol">:</a>
      <a id="5861" class="Symbol">({</a><a id="5863" href="foundation.universal-property-truncation.html#5863" class="Bound">l</a> <a id="5865" class="Symbol">:</a> <a id="5867" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="5872" class="Symbol">}</a> <a id="5874" class="Symbol">→</a> <a id="5876" href="foundation.universal-property-truncation.html#1980" class="Function">is-truncation</a> <a id="5890" href="foundation.universal-property-truncation.html#5863" class="Bound">l</a> <a id="5892" href="foundation.universal-property-truncation.html#5716" class="Bound">B</a> <a id="5894" href="foundation.universal-property-truncation.html#5744" class="Bound">f</a><a id="5895" class="Symbol">)</a> <a id="5897" class="Symbol">→</a>
      <a id="5905" class="Symbol">{</a><a id="5906" href="foundation.universal-property-truncation.html#5906" class="Bound">l</a> <a id="5908" class="Symbol">:</a> <a id="5910" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="5915" class="Symbol">}</a> <a id="5917" class="Symbol">→</a> <a id="5919" href="foundation.universal-property-truncation.html#2934" class="Function">dependent-universal-property-truncation</a> <a id="5959" href="foundation.universal-property-truncation.html#5906" class="Bound">l</a> <a id="5961" href="foundation.universal-property-truncation.html#5716" class="Bound">B</a> <a id="5963" href="foundation.universal-property-truncation.html#5744" class="Bound">f</a>
    <a id="5969" href="foundation.universal-property-truncation.html#5799" class="Function">dependent-universal-property-truncation-is-truncation</a> <a id="6023" href="foundation.universal-property-truncation.html#6023" class="Bound">H</a> <a id="6025" href="foundation.universal-property-truncation.html#6025" class="Bound">X</a> <a id="6027" class="Symbol">=</a>
      <a id="6035" href="foundation-core.functoriality-dependent-pair-types.html#10750" class="Function">is-fiberwise-equiv-is-equiv-map-Σ</a>
        <a id="6077" class="Symbol">(</a> <a id="6079" class="Symbol">λ</a> <a id="6081" class="Symbol">(</a><a id="6082" href="foundation.universal-property-truncation.html#6082" class="Bound">h</a> <a id="6084" class="Symbol">:</a> <a id="6086" href="foundation.universal-property-truncation.html#5704" class="Bound">A</a> <a id="6088" class="Symbol">→</a> <a id="6090" href="foundation-core.truncated-types.html#1786" class="Function">type-Truncated-Type</a> <a id="6110" href="foundation.universal-property-truncation.html#5716" class="Bound">B</a><a id="6111" class="Symbol">)</a> <a id="6113" class="Symbol">→</a>
          <a id="6125" class="Symbol">(</a><a id="6126" href="foundation.universal-property-truncation.html#6126" class="Bound">a</a> <a id="6128" class="Symbol">:</a> <a id="6130" href="foundation.universal-property-truncation.html#5704" class="Bound">A</a><a id="6131" class="Symbol">)</a> <a id="6133" class="Symbol">→</a> <a id="6135" href="foundation-core.truncated-types.html#1786" class="Function">type-Truncated-Type</a> <a id="6155" class="Symbol">(</a><a id="6156" href="foundation.universal-property-truncation.html#6025" class="Bound">X</a> <a id="6158" class="Symbol">(</a><a id="6159" href="foundation.universal-property-truncation.html#6082" class="Bound">h</a> <a id="6161" href="foundation.universal-property-truncation.html#6126" class="Bound">a</a><a id="6162" class="Symbol">)))</a>
        <a id="6174" class="Symbol">(</a> <a id="6176" class="Symbol">λ</a> <a id="6178" class="Symbol">(</a><a id="6179" href="foundation.universal-property-truncation.html#6179" class="Bound">g</a> <a id="6181" class="Symbol">:</a> <a id="6183" href="foundation-core.truncated-types.html#1786" class="Function">type-Truncated-Type</a> <a id="6203" href="foundation.universal-property-truncation.html#5716" class="Bound">B</a> <a id="6205" class="Symbol">→</a> <a id="6207" href="foundation-core.truncated-types.html#1786" class="Function">type-Truncated-Type</a> <a id="6227" href="foundation.universal-property-truncation.html#5716" class="Bound">B</a><a id="6228" class="Symbol">)</a> <a id="6230" class="Symbol">→</a> <a id="6232" href="foundation.universal-property-truncation.html#6179" class="Bound">g</a> <a id="6234" href="foundation-core.functions.html#407" class="Function Operator">∘</a> <a id="6236" href="foundation.universal-property-truncation.html#5744" class="Bound">f</a><a id="6237" class="Symbol">)</a>
        <a id="6247" class="Symbol">(</a> <a id="6249" class="Symbol">λ</a> <a id="6251" href="foundation.universal-property-truncation.html#6251" class="Bound">g</a> <a id="6253" class="Symbol">(</a><a id="6254" href="foundation.universal-property-truncation.html#6254" class="Bound">s</a> <a id="6256" class="Symbol">:</a> <a id="6258" class="Symbol">(</a><a id="6259" href="foundation.universal-property-truncation.html#6259" class="Bound">b</a> <a id="6261" class="Symbol">:</a> <a id="6263" href="foundation-core.truncated-types.html#1786" class="Function">type-Truncated-Type</a> <a id="6283" href="foundation.universal-property-truncation.html#5716" class="Bound">B</a><a id="6284" class="Symbol">)</a> <a id="6286" class="Symbol">→</a>
          <a id="6298" href="foundation-core.truncated-types.html#1786" class="Function">type-Truncated-Type</a> <a id="6318" class="Symbol">(</a><a id="6319" href="foundation.universal-property-truncation.html#6025" class="Bound">X</a> <a id="6321" class="Symbol">(</a><a id="6322" href="foundation.universal-property-truncation.html#6251" class="Bound">g</a> <a id="6324" href="foundation.universal-property-truncation.html#6259" class="Bound">b</a><a id="6325" class="Symbol">)))</a> <a id="6329" class="Symbol">(</a><a id="6330" href="foundation.universal-property-truncation.html#6330" class="Bound">a</a> <a id="6332" class="Symbol">:</a> <a id="6334" href="foundation.universal-property-truncation.html#5704" class="Bound">A</a><a id="6335" class="Symbol">)</a> <a id="6337" class="Symbol">→</a> <a id="6339" href="foundation.universal-property-truncation.html#6254" class="Bound">s</a> <a id="6341" class="Symbol">(</a><a id="6342" href="foundation.universal-property-truncation.html#5744" class="Bound">f</a> <a id="6344" href="foundation.universal-property-truncation.html#6330" class="Bound">a</a><a id="6345" class="Symbol">))</a>
        <a id="6356" class="Symbol">(</a> <a id="6358" href="foundation.universal-property-truncation.html#6023" class="Bound">H</a> <a id="6360" href="foundation.universal-property-truncation.html#5716" class="Bound">B</a><a id="6361" class="Symbol">)</a>
        <a id="6371" class="Symbol">(</a> <a id="6373" href="foundation-core.equivalences.html#12773" class="Function">is-equiv-equiv</a>
          <a id="6398" class="Symbol">(</a> <a id="6400" href="foundation.distributivity-of-dependent-functions-over-dependent-pairs.html#5106" class="Function">inv-distributive-Π-Σ</a><a id="6420" class="Symbol">)</a>
          <a id="6432" class="Symbol">(</a> <a id="6434" href="foundation.distributivity-of-dependent-functions-over-dependent-pairs.html#5106" class="Function">inv-distributive-Π-Σ</a><a id="6454" class="Symbol">)</a>
          <a id="6466" class="Symbol">(</a> <a id="6468" href="foundation-core.dependent-pair-types.html#687" class="Function">ind-Σ</a> <a id="6474" class="Symbol">(λ</a> <a id="6477" href="foundation.universal-property-truncation.html#6477" class="Bound">g</a> <a id="6479" href="foundation.universal-property-truncation.html#6479" class="Bound">s</a> <a id="6481" class="Symbol">→</a> <a id="6483" href="foundation-core.identity-types.html#694" class="InductiveConstructor">refl</a><a id="6487" class="Symbol">))</a>
          <a id="6500" class="Symbol">(</a> <a id="6502" href="foundation.universal-property-truncation.html#6023" class="Bound">H</a> <a id="6504" class="Symbol">(</a><a id="6505" href="foundation-core.truncated-types.html#6022" class="Function">Σ-Truncated-Type</a> <a id="6522" href="foundation.universal-property-truncation.html#5716" class="Bound">B</a> <a id="6524" href="foundation.universal-property-truncation.html#6025" class="Bound">X</a><a id="6525" class="Symbol">)))</a>
        <a id="6537" class="Symbol">(</a> <a id="6539" href="foundation-core.functions.html#309" class="Function">id</a><a id="6541" class="Symbol">)</a>

  <a id="6546" class="Keyword">abstract</a>
    <a id="6559" href="foundation.universal-property-truncation.html#6559" class="Function">is-truncation-dependent-universal-property-truncation</a> <a id="6613" class="Symbol">:</a>
      <a id="6621" class="Symbol">({</a><a id="6623" href="foundation.universal-property-truncation.html#6623" class="Bound">l</a> <a id="6625" class="Symbol">:</a> <a id="6627" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="6632" class="Symbol">}</a> <a id="6634" class="Symbol">→</a> <a id="6636" href="foundation.universal-property-truncation.html#2934" class="Function">dependent-universal-property-truncation</a> <a id="6676" href="foundation.universal-property-truncation.html#6623" class="Bound">l</a> <a id="6678" href="foundation.universal-property-truncation.html#5716" class="Bound">B</a> <a id="6680" href="foundation.universal-property-truncation.html#5744" class="Bound">f</a><a id="6681" class="Symbol">)</a> <a id="6683" class="Symbol">→</a>
      <a id="6691" class="Symbol">{</a><a id="6692" href="foundation.universal-property-truncation.html#6692" class="Bound">l</a> <a id="6694" class="Symbol">:</a> <a id="6696" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="6701" class="Symbol">}</a> <a id="6703" class="Symbol">→</a> <a id="6705" href="foundation.universal-property-truncation.html#1980" class="Function">is-truncation</a> <a id="6719" href="foundation.universal-property-truncation.html#6692" class="Bound">l</a> <a id="6721" href="foundation.universal-property-truncation.html#5716" class="Bound">B</a> <a id="6723" href="foundation.universal-property-truncation.html#5744" class="Bound">f</a>
    <a id="6729" href="foundation.universal-property-truncation.html#6559" class="Function">is-truncation-dependent-universal-property-truncation</a> <a id="6783" href="foundation.universal-property-truncation.html#6783" class="Bound">H</a> <a id="6785" href="foundation.universal-property-truncation.html#6785" class="Bound">X</a> <a id="6787" class="Symbol">=</a>
      <a id="6795" href="foundation.universal-property-truncation.html#6783" class="Bound">H</a> <a id="6797" class="Symbol">(λ</a> <a id="6800" href="foundation.universal-property-truncation.html#6800" class="Bound">b</a> <a id="6802" class="Symbol">→</a> <a id="6804" href="foundation.universal-property-truncation.html#6785" class="Bound">X</a><a id="6805" class="Symbol">)</a>

  <a id="6810" href="foundation.universal-property-truncation.html#6810" class="Function">sec-is-truncation</a> <a id="6828" class="Symbol">:</a>
    <a id="6834" class="Symbol">({</a><a id="6836" href="foundation.universal-property-truncation.html#6836" class="Bound">l</a> <a id="6838" class="Symbol">:</a> <a id="6840" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="6845" class="Symbol">}</a> <a id="6847" class="Symbol">→</a> <a id="6849" href="foundation.universal-property-truncation.html#1980" class="Function">is-truncation</a> <a id="6863" href="foundation.universal-property-truncation.html#6836" class="Bound">l</a> <a id="6865" href="foundation.universal-property-truncation.html#5716" class="Bound">B</a> <a id="6867" href="foundation.universal-property-truncation.html#5744" class="Bound">f</a><a id="6868" class="Symbol">)</a> <a id="6870" class="Symbol">→</a>
    <a id="6876" class="Symbol">{</a><a id="6877" href="foundation.universal-property-truncation.html#6877" class="Bound">l3</a> <a id="6880" class="Symbol">:</a> <a id="6882" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="6887" class="Symbol">}</a> <a id="6889" class="Symbol">(</a><a id="6890" href="foundation.universal-property-truncation.html#6890" class="Bound">C</a> <a id="6892" class="Symbol">:</a> <a id="6894" href="foundation-core.truncated-types.html#1651" class="Function">Truncated-Type</a> <a id="6909" href="foundation.universal-property-truncation.html#6877" class="Bound">l3</a> <a id="6912" href="foundation.universal-property-truncation.html#5696" class="Bound">k</a><a id="6913" class="Symbol">)</a>
    <a id="6919" class="Symbol">(</a><a id="6920" href="foundation.universal-property-truncation.html#6920" class="Bound">h</a> <a id="6922" class="Symbol">:</a> <a id="6924" href="foundation.universal-property-truncation.html#5704" class="Bound">A</a> <a id="6926" class="Symbol">→</a> <a id="6928" href="foundation-core.truncated-types.html#1786" class="Function">type-Truncated-Type</a> <a id="6948" href="foundation.universal-property-truncation.html#6890" class="Bound">C</a><a id="6949" class="Symbol">)</a> <a id="6951" class="Symbol">(</a><a id="6952" href="foundation.universal-property-truncation.html#6952" class="Bound">g</a> <a id="6954" class="Symbol">:</a> <a id="6956" href="foundation.truncated-types.html#3483" class="Function">type-hom-Truncated-Type</a> <a id="6980" href="foundation.universal-property-truncation.html#5696" class="Bound">k</a> <a id="6982" href="foundation.universal-property-truncation.html#6890" class="Bound">C</a> <a id="6984" href="foundation.universal-property-truncation.html#5716" class="Bound">B</a><a id="6985" class="Symbol">)</a> <a id="6987" class="Symbol">→</a>
    <a id="6993" href="foundation.universal-property-truncation.html#5744" class="Bound">f</a> <a id="6995" href="foundation-core.homotopies.html#467" class="Function Operator">~</a> <a id="6997" class="Symbol">(</a><a id="6998" href="foundation.universal-property-truncation.html#6952" class="Bound">g</a> <a id="7000" href="foundation-core.functions.html#407" class="Function Operator">∘</a> <a id="7002" href="foundation.universal-property-truncation.html#6920" class="Bound">h</a><a id="7003" class="Symbol">)</a> <a id="7005" class="Symbol">→</a> <a id="7007" href="foundation-core.sections.html#521" class="Function">sec</a> <a id="7011" href="foundation.universal-property-truncation.html#6952" class="Bound">g</a>
  <a id="7015" href="foundation.universal-property-truncation.html#6810" class="Function">sec-is-truncation</a> <a id="7033" href="foundation.universal-property-truncation.html#7033" class="Bound">H</a> <a id="7035" href="foundation.universal-property-truncation.html#7035" class="Bound">C</a> <a id="7037" href="foundation.universal-property-truncation.html#7037" class="Bound">h</a> <a id="7039" href="foundation.universal-property-truncation.html#7039" class="Bound">g</a> <a id="7041" href="foundation.universal-property-truncation.html#7041" class="Bound">K</a> <a id="7043" class="Symbol">=</a>
    <a id="7049" href="foundation.distributivity-of-dependent-functions-over-dependent-pairs.html#2808" class="Function">map-distributive-Π-Σ</a>
      <a id="7076" class="Symbol">(</a> <a id="7078" href="foundation-core.equivalences.html#4173" class="Function">map-inv-is-equiv</a>
        <a id="7103" class="Symbol">(</a> <a id="7105" href="foundation.universal-property-truncation.html#5799" class="Function">dependent-universal-property-truncation-is-truncation</a> <a id="7159" href="foundation.universal-property-truncation.html#7033" class="Bound">H</a>
          <a id="7171" class="Symbol">(</a> <a id="7173" href="foundation-core.truncated-types.html#6396" class="Function">fib-Truncated-Type</a> <a id="7192" href="foundation.universal-property-truncation.html#7035" class="Bound">C</a> <a id="7194" href="foundation.universal-property-truncation.html#5716" class="Bound">B</a> <a id="7196" href="foundation.universal-property-truncation.html#7039" class="Bound">g</a><a id="7197" class="Symbol">))</a>
        <a id="7208" class="Symbol">(</a> <a id="7210" class="Symbol">λ</a> <a id="7212" href="foundation.universal-property-truncation.html#7212" class="Bound">a</a> <a id="7214" class="Symbol">→</a> <a id="7216" href="foundation-core.dependent-pair-types.html#575" class="InductiveConstructor">pair</a> <a id="7221" class="Symbol">(</a><a id="7222" href="foundation.universal-property-truncation.html#7037" class="Bound">h</a> <a id="7224" href="foundation.universal-property-truncation.html#7212" class="Bound">a</a><a id="7225" class="Symbol">)</a> <a id="7227" class="Symbol">(</a><a id="7228" href="foundation-core.identity-types.html#1552" class="Function">inv</a> <a id="7232" class="Symbol">(</a><a id="7233" href="foundation.universal-property-truncation.html#7041" class="Bound">K</a> <a id="7235" href="foundation.universal-property-truncation.html#7212" class="Bound">a</a><a id="7236" class="Symbol">))))</a>
</pre>
## To do

<pre class="Agda">
<a id="7265" class="Comment">{-

-- Theorem 18.5.2 Condition (iii)

mere-eq-Eq-Rel : {l1 : Level} (A : UU l1) → Eq-Rel l1 A
mere-eq-Eq-Rel A =
  pair
    mere-eq-Prop
    ( pair refl-mere-eq (pair symm-mere-eq trans-mere-eq))

-- Theorem 18.5.2 (iii) implies (i)

reflects-mere-eq :
  {l1 l2 : Level} {A : UU l1} (X : UU-Set l2) (f : A → type-Set X) →
  reflects-Eq-Rel (mere-eq-Eq-Rel A) f
reflects-mere-eq X f {x} {y} r =
  apply-universal-property-trunc-Prop r
    ( Id-Prop X (f x) (f y))
    ( ap f)

reflecting-map-mere-eq :
  {l1 l2 : Level} {A : UU l1} (X : UU-Set l2) (f : A → type-Set X) →
  reflecting-map-Eq-Rel (mere-eq-Eq-Rel A) (type-Set X)
reflecting-map-mere-eq X f = pair f (reflects-mere-eq X f)

abstract
  is-set-truncation-is-set-quotient :
    {l1 l2 l3 : Level} {A : UU l1} (B : UU-Set l2) (f : A → type-Set B) →
    ( {l : Level} →
      is-set-quotient l (mere-eq-Eq-Rel A) B (reflecting-map-mere-eq B f)) →
    is-set-truncation l3 B f
  is-set-truncation-is-set-quotient {A = A} B f H X =
    is-equiv-comp
      ( precomp-Set f X)
      ( pr1)
      ( precomp-Set-Quotient
        ( mere-eq-Eq-Rel A)
        ( B)
        ( reflecting-map-mere-eq B f)
        ( X))
      ( refl-htpy)
      ( H X)
      ( is-equiv-pr1-is-contr
        ( λ h →
          is-proof-irrelevant-is-prop
            ( is-prop-reflects-Eq-Rel (mere-eq-Eq-Rel A) X h)
            ( reflects-mere-eq X h)))

abstract
  is-set-quotient-is-set-truncation :
    {l1 l2 l3 : Level} {A : UU l1} (B : UU-Set l2) (f : A → type-Set B) →
    ( {l : Level} → is-set-truncation l B f) →
    is-set-quotient l3 (mere-eq-Eq-Rel A) B (reflecting-map-mere-eq B f)
  is-set-quotient-is-set-truncation {A = A} B f H X =
    is-equiv-right-factor
      ( precomp-Set f X)
      ( pr1)
      ( precomp-Set-Quotient
        ( mere-eq-Eq-Rel A)
        ( B)
        ( reflecting-map-mere-eq B f)
        ( X))
      ( refl-htpy)
      ( is-equiv-pr1-is-contr
        ( λ h →
          is-proof-irrelevant-is-prop
            ( is-prop-reflects-Eq-Rel (mere-eq-Eq-Rel A) X h)
            ( reflects-mere-eq X h)))
      ( H X)

-- Definition 18.5.3

-- Corollary 18.5.4

reflecting-map-mere-eq-unit-trunc-Set :
  {l : Level} (A : UU l) →
  reflecting-map-Eq-Rel (mere-eq-Eq-Rel A) (type-trunc-Set A)
reflecting-map-mere-eq-unit-trunc-Set A =
  pair unit-trunc-Set (reflects-mere-eq (trunc-Set A) unit-trunc-Set)

abstract
  is-set-quotient-trunc-Set :
    {l1 l2 : Level} (A : UU l1) →
    is-set-quotient l2
      ( mere-eq-Eq-Rel A)
      ( trunc-Set A)
      ( reflecting-map-mere-eq-unit-trunc-Set A)
  is-set-quotient-trunc-Set A =
    is-set-quotient-is-set-truncation
      ( trunc-Set A)
      ( unit-trunc-Set)
      ( λ {l} → is-set-truncation-trunc-Set A)

abstract
  is-surjective-and-effective-unit-trunc-Set :
    {l1 : Level} (A : UU l1) →
    is-surjective-and-effective (mere-eq-Eq-Rel A) unit-trunc-Set
  is-surjective-and-effective-unit-trunc-Set A =
    is-surjective-and-effective-is-set-quotient
      ( mere-eq-Eq-Rel A)
      ( trunc-Set A)
      ( unit-trunc-Set)
      ( reflects-mere-eq (trunc-Set A) unit-trunc-Set)
      ( λ {l} → is-set-quotient-trunc-Set A)

abstract
  is-surjective-unit-trunc-Set :
    {l1 : Level} (A : UU l1) → is-surjective (unit-trunc-Set {A = A})
  is-surjective-unit-trunc-Set A =
    pr1 (is-surjective-and-effective-unit-trunc-Set A)

abstract
  is-effective-unit-trunc-Set :
    {l1 : Level} (A : UU l1) →
    is-effective (mere-eq-Eq-Rel A) (unit-trunc-Set {A = A})
  is-effective-unit-trunc-Set A =
    pr2 (is-surjective-and-effective-unit-trunc-Set A)

abstract
  apply-effectiveness-unit-trunc-Set :
    {l1 : Level} {A : UU l1} {x y : A} →
    Id (unit-trunc-Set x) (unit-trunc-Set y) → mere-eq x y
  apply-effectiveness-unit-trunc-Set {A = A} {x} {y} =
    map-equiv (is-effective-unit-trunc-Set A x y)

abstract
  apply-effectiveness-unit-trunc-Set&#39; :
    {l1 : Level} {A : UU l1} {x y : A} →
    mere-eq x y → Id (unit-trunc-Set x) (unit-trunc-Set y)
  apply-effectiveness-unit-trunc-Set&#39; {A = A} {x} {y} =
    map-inv-equiv (is-effective-unit-trunc-Set A x y)

emb-trunc-Set :
  {l1 : Level} (A : UU l1) → type-trunc-Set A ↪ (A → UU-Prop l1)
emb-trunc-Set A =
  emb-is-surjective-and-effective
    ( mere-eq-Eq-Rel A)
    ( trunc-Set A)
    ( unit-trunc-Set)
    ( is-surjective-and-effective-unit-trunc-Set A)

hom-slice-trunc-Set :
  {l1 : Level} (A : UU l1) →
  hom-slice (mere-eq-Prop {A = A}) (map-emb (emb-trunc-Set A))
hom-slice-trunc-Set A =
  pair
    ( unit-trunc-Set)
    ( triangle-emb-is-surjective-and-effective
      ( mere-eq-Eq-Rel A)
      ( trunc-Set A)
      ( unit-trunc-Set)
      ( is-surjective-and-effective-unit-trunc-Set A))

abstract
  is-image-trunc-Set :
    {l1 l2 : Level} (A : UU l1) →
    is-image l2
      ( mere-eq-Prop {A = A})
      ( emb-trunc-Set A)
      ( hom-slice-trunc-Set A)
  is-image-trunc-Set A =
    is-image-is-surjective-and-effective
      ( mere-eq-Eq-Rel A)
      ( trunc-Set A)
      ( unit-trunc-Set)
      ( is-surjective-and-effective-unit-trunc-Set A)

-- Uniqueness of trunc-Set

module _
  {l1 l2 : Level} {A : UU l1} (B : UU-Set l2) (f : A → type-Set B)
  {h : type-hom-Set B (trunc-Set A)} (H : (h ∘ f) ~ unit-trunc-Set)
  where

  abstract
    is-equiv-is-set-truncation&#39; :
      ({l : Level} → is-set-truncation l B f) → is-equiv h
    is-equiv-is-set-truncation&#39; Sf =
      is-equiv-is-set-truncation-is-set-truncation
        ( B)
        ( f)
        ( trunc-Set A)
        ( unit-trunc-Set)
        ( H)
        ( Sf)
        ( λ {h} → is-set-truncation-trunc-Set A)

  abstract
    is-set-truncation-is-equiv&#39; :
      is-equiv h → ({l : Level} → is-set-truncation l B f)
    is-set-truncation-is-equiv&#39; Eh =
      is-set-truncation-is-equiv-is-set-truncation
        ( B)
        ( f)
        ( trunc-Set A)
        ( unit-trunc-Set)
        ( H)
        ( λ {l} → is-set-truncation-trunc-Set A)
        ( Eh)

module _
  {l1 l2 : Level} {A : UU l1} (B : UU-Set l2) (f : A → type-Set B)
  {h : type-hom-Set (trunc-Set A) B} (H : (h ∘ unit-trunc-Set) ~ f)
  where

  abstract
    is-equiv-is-set-truncation :
      ({l : Level} → is-set-truncation l B f) → is-equiv h
    is-equiv-is-set-truncation Sf =
      is-equiv-is-set-truncation-is-set-truncation
        ( trunc-Set A)
        ( unit-trunc-Set)
        ( B)
        ( f)
        ( H)
        ( λ {l} → is-set-truncation-trunc-Set A)
        ( Sf)

  abstract
    is-set-truncation-is-equiv :
      is-equiv h → ({l : Level} → is-set-truncation l B f)
    is-set-truncation-is-equiv Eh =
      is-set-truncation-is-set-truncation-is-equiv
        ( trunc-Set A)
        ( unit-trunc-Set)
        ( B)
        ( f)
        ( H)
        ( Eh)
        ( λ {l} → is-set-truncation-trunc-Set A)

abstract
  is-equiv-unit-trunc-Set :
    {l : Level} (A : UU-Set l) → is-equiv (unit-trunc-Set {A = type-Set A})
  is-equiv-unit-trunc-Set A =
    is-equiv-is-set-truncation&#39; A id refl-htpy
      ( is-set-truncation-id (is-set-type-Set A))

equiv-unit-trunc-Set :
  {l : Level} (A : UU-Set l) → type-Set A ≃ type-trunc-Set (type-Set A)
equiv-unit-trunc-Set A =
  pair unit-trunc-Set (is-equiv-unit-trunc-Set A)

equiv-unit-trunc-empty-Set : empty ≃ type-trunc-Set empty
equiv-unit-trunc-empty-Set = equiv-unit-trunc-Set empty-Set

abstract
  is-empty-trunc-Set :
    {l : Level} {A : UU l} → is-empty A → is-empty (type-trunc-Set A)
  is-empty-trunc-Set f x = apply-universal-property-trunc-Set x empty-Set f

abstract
  is-empty-is-empty-trunc-Set :
    {l : Level} {A : UU l} → is-empty (type-trunc-Set A) → is-empty A
  is-empty-is-empty-trunc-Set f = f ∘ unit-trunc-Set

equiv-unit-trunc-unit-Set : unit ≃ type-trunc-Set unit
equiv-unit-trunc-unit-Set = equiv-unit-trunc-Set unit-Set

equiv-unit-trunc-ℕ-Set : ℕ ≃ type-trunc-Set ℕ
equiv-unit-trunc-ℕ-Set = equiv-unit-trunc-Set ℕ-Set

equiv-unit-trunc-ℤ-Set : ℤ ≃ type-trunc-Set ℤ
equiv-unit-trunc-ℤ-Set = equiv-unit-trunc-Set ℤ-Set

equiv-unit-trunc-Fin-Set : (k : ℕ) → Fin k ≃ type-trunc-Set (Fin k)
equiv-unit-trunc-Fin-Set k = equiv-unit-trunc-Set (Fin-Set k)

abstract
  is-contr-trunc-Set :
    {l : Level} {A : UU l} → is-contr A → is-contr (type-trunc-Set A)
  is-contr-trunc-Set {l} {A} H =
    is-contr-equiv&#39;
      ( A)
      ( equiv-unit-trunc-Set (pair A (is-set-is-contr H)))
      ( H)

module _
  {l1 l2 : Level} {A : UU l1} (B : UU-Set l2) (f : A → type-Set B)
  (Sf : {l : Level} → is-set-truncation l B f)
  where

  abstract
    uniqueness-trunc-Set :
      is-contr
        ( Σ (type-trunc-Set A ≃ type-Set B)
        ( λ e → (map-equiv e ∘ unit-trunc-Set) ~ f))
    uniqueness-trunc-Set =
      uniqueness-set-truncation (trunc-Set A) unit-trunc-Set B f
        ( λ {l} → is-set-truncation-trunc-Set A)
        ( Sf)

  equiv-uniqueness-trunc-Set : type-trunc-Set A ≃ type-Set B
  equiv-uniqueness-trunc-Set =
    pr1 (center uniqueness-trunc-Set)

  map-equiv-uniqueness-trunc-Set : type-trunc-Set A → type-Set B
  map-equiv-uniqueness-trunc-Set =
    map-equiv equiv-uniqueness-trunc-Set

  triangle-uniqueness-trunc-Set :
    (map-equiv-uniqueness-trunc-Set ∘ unit-trunc-Set) ~ f
  triangle-uniqueness-trunc-Set =
    pr2 (center uniqueness-trunc-Set)

module _
  {l1 l2 : Level} {A : UU l1} (B : UU-Set l2) (f : A → type-Set B)
  (Sf : {l : Level} → is-set-truncation l B f)
  where

  abstract
    uniqueness-trunc-Set&#39; :
      is-contr
        ( Σ ( type-Set B ≃ type-trunc-Set A)
            ( λ e → (map-equiv e ∘ f) ~ unit-trunc-Set))
    uniqueness-trunc-Set&#39; =
      uniqueness-set-truncation B f (trunc-Set A) unit-trunc-Set Sf
        ( λ {l} → is-set-truncation-trunc-Set A)

  equiv-uniqueness-trunc-Set&#39; : type-Set B ≃ type-trunc-Set A
  equiv-uniqueness-trunc-Set&#39; =
    pr1 (center uniqueness-trunc-Set&#39;)

  map-equiv-uniqueness-trunc-Set&#39; : type-Set B → type-trunc-Set A
  map-equiv-uniqueness-trunc-Set&#39; =
    map-equiv equiv-uniqueness-trunc-Set&#39;
  
  triangle-uniqueness-trunc-Set&#39; :
    (map-equiv-uniqueness-trunc-Set&#39; ∘ f) ~ unit-trunc-Set
  triangle-uniqueness-trunc-Set&#39; =
    pr2 (center uniqueness-trunc-Set&#39;)

-- Proposition 18.5.5

module _
  {l1 l2 : Level} {A : UU l1} {B : UU l2} (f : A → B)
  where

  abstract
    unique-map-trunc-Set :
      is-contr
        ( Σ ( type-trunc-Set A → type-trunc-Set B)
            ( λ h → (h ∘ unit-trunc-Set) ~ (unit-trunc-Set ∘ f)))
    unique-map-trunc-Set =
      universal-property-trunc-Set A (trunc-Set B) (unit-trunc-Set ∘ f)

  map-trunc-Set :
    type-trunc-Set A → type-trunc-Set B
  map-trunc-Set =
    pr1 (center unique-map-trunc-Set)

  naturality-trunc-Set :
    (map-trunc-Set ∘ unit-trunc-Set) ~ (unit-trunc-Set ∘ f)
  naturality-trunc-Set =
    pr2 (center unique-map-trunc-Set)

  htpy-map-trunc-Set :
    (h : type-trunc-Set A → type-trunc-Set B) →
    (H : (h ∘ unit-trunc-Set) ~ (unit-trunc-Set ∘ f)) →
    map-trunc-Set ~ h
  htpy-map-trunc-Set h H =
    htpy-eq
      ( ap pr1
        ( eq-is-contr unique-map-trunc-Set
          { pair map-trunc-Set naturality-trunc-Set}
          { pair h H}))

map-id-trunc-Set :
  {l1 : Level} {A : UU l1} → map-trunc-Set (id {A = A}) ~ id
map-id-trunc-Set {l1} {A} =
  htpy-eq
    ( ap pr1
      ( eq-is-contr
        ( universal-property-trunc-Set A (trunc-Set A) unit-trunc-Set)
        { pair (map-trunc-Set id) (naturality-trunc-Set id)}
        { pair id refl-htpy}))

map-comp-trunc-Set :
  {l1 l2 l3 : Level} {A : UU l1} {B : UU l2} {C : UU l3}
  (g : B → C) (f : A → B) →
  map-trunc-Set (g ∘ f) ~ (map-trunc-Set g ∘ map-trunc-Set f)
map-comp-trunc-Set {A = A} {C = C} g f =
  htpy-eq
    ( ap pr1
      ( eq-is-contr
        ( universal-property-trunc-Set
          A
          (trunc-Set C)
          (unit-trunc-Set ∘ (g ∘ f)))
        { pair (map-trunc-Set (g ∘ f)) (naturality-trunc-Set (g ∘ f))}
        { pair ( map-trunc-Set g ∘ map-trunc-Set f)
               ( ( map-trunc-Set g ·l naturality-trunc-Set f) ∙h
                 ( naturality-trunc-Set g ·r f))}))

htpy-trunc-Set :
  {l1 l2 : Level} {A : UU l1} {B : UU l2} {f g : A → B} →
  (f ~ g) → (map-trunc-Set f ~ map-trunc-Set g)
htpy-trunc-Set {B = B} {f = f} {g} H =
  map-inv-is-equiv
    ( dependent-universal-property-trunc-Set
      ( λ x →
        set-Prop
          ( Id-Prop (trunc-Set B) (map-trunc-Set f x) (map-trunc-Set g x))))
    ( λ a →
      ( naturality-trunc-Set f a) ∙
      ( ( ap unit-trunc-Set (H a)) ∙
        ( inv (naturality-trunc-Set g a))))

abstract
  is-equiv-map-trunc-Set :
    {l1 l2 : Level} {A : UU l1} {B : UU l2} {f : A → B} →
    is-equiv f → is-equiv (map-trunc-Set f)
  is-equiv-map-trunc-Set {f = f} H =
    pair
      ( pair
        ( map-trunc-Set (pr1 (pr1 H)))
        ( ( inv-htpy (map-comp-trunc-Set f (pr1 (pr1 H)))) ∙h
          ( ( htpy-trunc-Set (pr2 (pr1 H))) ∙h
            ( map-id-trunc-Set))))
      ( pair
        ( map-trunc-Set (pr1 (pr2 H)))
        ( ( inv-htpy (map-comp-trunc-Set (pr1 (pr2 H)) f)) ∙h
          ( ( htpy-trunc-Set (pr2 (pr2 H))) ∙h
            ( map-id-trunc-Set))))

equiv-trunc-Set :
  {l1 l2 : Level} {A : UU l1} {B : UU l2} →
  (A ≃ B) → (type-trunc-Set A ≃ type-trunc-Set B)
equiv-trunc-Set e =
  pair
    ( map-trunc-Set (map-equiv e))
    ( is-equiv-map-trunc-Set (is-equiv-map-equiv e))

map-equiv-trunc-Set :
  {l1 l2 : Level} {A : UU l1} {B : UU l2} →
  (A ≃ B) → type-trunc-Set A → type-trunc-Set B
map-equiv-trunc-Set e = map-equiv (equiv-trunc-Set e)

--------------------------------------------------------------------------------

module _
  {l1 l2 : Level} (A : UU l1) (B : UU l2)
  where

  abstract
    distributive-trunc-coprod-Set :
      is-contr
        ( Σ ( type-equiv-Set
              ( trunc-Set (coprod A B))
              ( coprod-Set (trunc-Set A) (trunc-Set B)))
            ( λ e →
              ( map-equiv e ∘ unit-trunc-Set) ~
              ( map-coprod unit-trunc-Set unit-trunc-Set)))
    distributive-trunc-coprod-Set =
      uniqueness-trunc-Set
        ( coprod-Set (trunc-Set A) (trunc-Set B))
        ( map-coprod unit-trunc-Set unit-trunc-Set)
        ( λ {l} C →
          is-equiv-right-factor&#39;
            ( ev-inl-inr (λ x → type-Set C))
            ( precomp-Set (map-coprod unit-trunc-Set unit-trunc-Set) C)
            ( universal-property-coprod (type-Set C))
            ( is-equiv-comp&#39;
              ( map-prod
                ( precomp-Set unit-trunc-Set C)
                ( precomp-Set unit-trunc-Set C))
              ( ev-inl-inr (λ x → type-Set C))
              ( universal-property-coprod (type-Set C))
              ( is-equiv-map-prod
                ( precomp-Set unit-trunc-Set C)
                ( precomp-Set unit-trunc-Set C)
                ( is-set-truncation-trunc-Set A C)
                ( is-set-truncation-trunc-Set B C))))

  equiv-distributive-trunc-coprod-Set :
    type-equiv-Set
      ( trunc-Set (coprod A B))
      ( coprod-Set (trunc-Set A) (trunc-Set B))
  equiv-distributive-trunc-coprod-Set =
    pr1 (center distributive-trunc-coprod-Set)

  map-equiv-distributive-trunc-coprod-Set :
    type-hom-Set
      ( trunc-Set (coprod A B))
      ( coprod-Set (trunc-Set A) (trunc-Set B))
  map-equiv-distributive-trunc-coprod-Set =
    map-equiv equiv-distributive-trunc-coprod-Set

  triangle-distributive-trunc-coprod-Set :
    ( map-equiv-distributive-trunc-coprod-Set ∘ unit-trunc-Set) ~
    ( map-coprod unit-trunc-Set unit-trunc-Set)
  triangle-distributive-trunc-coprod-Set =
    pr2 (center distributive-trunc-coprod-Set)

-- Set truncations of Σ-types

module _
  {l1 l2 : Level} (A : UU l1) (B : A → UU l2)
  where

  abstract
    trunc-Σ-Set :
      is-contr
        ( Σ ( type-trunc-Set (Σ A B) ≃
              type-trunc-Set (Σ A (λ x → type-trunc-Set (B x))))
            ( λ e →
              ( map-equiv e ∘ unit-trunc-Set) ~
              ( unit-trunc-Set ∘ tot (λ x → unit-trunc-Set))))
    trunc-Σ-Set =
      uniqueness-trunc-Set
        ( trunc-Set (Σ A (λ x → type-trunc-Set (B x))))
        ( unit-trunc-Set ∘ tot (λ x → unit-trunc-Set))
        ( λ {l} C →
          is-equiv-right-factor&#39;
            ( ev-pair)
            ( precomp-Set (unit-trunc-Set ∘ tot (λ x → unit-trunc-Set)) C)
            ( is-equiv-ev-pair)
            ( is-equiv-htpy-equiv
              ( ( equiv-map-Π
                  ( λ x → equiv-universal-property-trunc-Set (B x) C)) ∘e
                ( ( equiv-ev-pair) ∘e
                  ( equiv-universal-property-trunc-Set
                    ( Σ A (type-trunc-Set ∘ B)) C)))
              ( refl-htpy)))

  equiv-trunc-Σ-Set :
    type-trunc-Set (Σ A B) ≃ type-trunc-Set (Σ A (λ x → type-trunc-Set (B x)))
  equiv-trunc-Σ-Set =
    pr1 (center trunc-Σ-Set)

  map-equiv-trunc-Σ-Set :
    type-trunc-Set (Σ A B) → type-trunc-Set (Σ A (λ x → type-trunc-Set (B x)))
  map-equiv-trunc-Σ-Set =
    map-equiv equiv-trunc-Σ-Set

  square-trunc-Σ-Set :
    ( map-equiv-trunc-Σ-Set ∘ unit-trunc-Set) ~
    ( unit-trunc-Set ∘ tot (λ x → unit-trunc-Set))
  square-trunc-Σ-Set =
    pr2 (center trunc-Σ-Set)

  htpy-map-equiv-trunc-Σ-Set :
    map-trunc-Set (tot (λ x → unit-trunc-Set)) ~ map-equiv-trunc-Σ-Set
  htpy-map-equiv-trunc-Σ-Set =
    htpy-map-trunc-Set
      ( tot (λ x → unit-trunc-Set))
      ( map-equiv-trunc-Σ-Set)
      ( square-trunc-Σ-Set)

  abstract
    is-equiv-map-trunc-tot-unit-trunc-Set :
      is-equiv (map-trunc-Set (tot (λ (x : A) → unit-trunc-Set {A = B x})))
    is-equiv-map-trunc-tot-unit-trunc-Set =
      is-equiv-htpy-equiv
        ( equiv-trunc-Σ-Set)
        ( htpy-map-equiv-trunc-Σ-Set)

-- trunc-Set distributes over products

module _
  {l1 l2 : Level} (A : UU l1) (B : UU l2)
  where

  abstract
    distributive-trunc-prod-Set :
      is-contr
        ( Σ ( type-trunc-Set (A × B) ≃ ( type-trunc-Set A × type-trunc-Set B))
            ( λ e →
              ( map-equiv e ∘ unit-trunc-Set) ~
              ( map-prod unit-trunc-Set unit-trunc-Set)))
    distributive-trunc-prod-Set =
      uniqueness-trunc-Set
        ( prod-Set (trunc-Set A) (trunc-Set B))
        ( map-prod unit-trunc-Set unit-trunc-Set)
        ( λ {l} C →
          is-equiv-right-factor&#39;
            ( ev-pair)
            ( precomp-Set (map-prod unit-trunc-Set unit-trunc-Set) C)
            ( is-equiv-ev-pair)
            ( is-equiv-htpy-equiv
              ( ( equiv-universal-property-trunc-Set A (Π-Set&#39; B (λ y → C))) ∘e
                ( ( equiv-postcomp
                    ( type-trunc-Set A)
                    (equiv-universal-property-trunc-Set B C)) ∘e
                  ( equiv-ev-pair)))
              ( refl-htpy)))

  equiv-distributive-trunc-prod-Set :
    type-trunc-Set (A × B) ≃ ( type-trunc-Set A × type-trunc-Set B)
  equiv-distributive-trunc-prod-Set =
    pr1 (center distributive-trunc-prod-Set)

  map-equiv-distributive-trunc-prod-Set :
    type-trunc-Set (A × B) → type-trunc-Set A × type-trunc-Set B
  map-equiv-distributive-trunc-prod-Set =
    map-equiv equiv-distributive-trunc-prod-Set

  triangle-distributive-trunc-prod-Set :
    ( map-equiv-distributive-trunc-prod-Set ∘ unit-trunc-Set) ~
    ( map-prod unit-trunc-Set unit-trunc-Set)
  triangle-distributive-trunc-prod-Set =
    pr2 (center distributive-trunc-prod-Set)

-- trunc-Set distributes over Π indexed by Fin

abstract
  distributive-trunc-Π-Fin-Set :
    {l : Level} (k : ℕ) (A : Fin k → UU l) →
    is-contr
      ( Σ ( ( type-trunc-Set ((x : Fin k) → A x)) ≃
            ( (x : Fin k) → type-trunc-Set (A x)))
          ( λ e →
            ( map-equiv e ∘ unit-trunc-Set) ~
            ( map-Π (λ x → unit-trunc-Set))))
  distributive-trunc-Π-Fin-Set zero-ℕ A =
    uniqueness-trunc-Set
      ( Π-Set empty-Set (λ x → trunc-Set (A x)))
      ( map-Π (λ x → unit-trunc-Set))
      ( λ {l} B →
        is-equiv-precomp-is-equiv
          ( map-Π (λ x → unit-trunc-Set))
          ( is-equiv-is-contr
            ( map-Π (λ x → unit-trunc-Set))
            ( dependent-universal-property-empty&#39; A)
            ( dependent-universal-property-empty&#39; (type-trunc-Set ∘ A)))
          ( type-Set B))
  distributive-trunc-Π-Fin-Set (succ-ℕ k) A =
    uniqueness-trunc-Set
      ( Π-Set (Fin-Set (succ-ℕ k)) (λ x → trunc-Set (A x)))
      ( map-Π (λ x → unit-trunc-Set))
      ( λ {l} B →
        is-equiv-left-factor&#39;
          ( precomp (map-Π (λ x → unit-trunc-Set)) (type-Set B))
          ( precomp (ev-Maybe {B = type-trunc-Set ∘ A}) (type-Set B))
          ( is-equiv-comp&#39;
            ( precomp ev-Maybe (type-Set B))
            ( precomp
              ( map-prod (map-Π (λ x → unit-trunc-Set)) unit-trunc-Set)
              ( type-Set B))
            ( is-equiv-right-factor&#39;
              ( ev-pair)
              ( precomp
                ( map-prod (map-Π (λ x → unit-trunc-Set)) unit-trunc-Set)
                ( type-Set B))
              ( is-equiv-ev-pair)
              ( is-equiv-htpy-equiv
                ( ( ( pair
                      ( precomp
                        ( (map-Π (λ x → unit-trunc-Set)))
                        ( A (inr star) → type-Set B))
                      ( is-set-truncation-is-equiv
                        ( Π-Set (Fin-Set k) (λ x → trunc-Set (A (inl x))))
                        ( map-Π (λ x → unit-trunc-Set))
                        { map-equiv
                          ( pr1
                            ( center
                              ( distributive-trunc-Π-Fin-Set k (A ∘ inl))))}
                        ( pr2
                          ( center (distributive-trunc-Π-Fin-Set k (A ∘ inl))))
                        ( is-equiv-map-equiv
                          ( pr1
                            ( center
                              ( distributive-trunc-Π-Fin-Set k (A ∘ inl)))))
                        ( Π-Set&#39; (A (inr star)) (λ a → B)))) ∘e
                    ( equiv-postcomp
                      ( (x : Fin k) → type-trunc-Set (A (inl x)))
                      ( equiv-universal-property-trunc-Set
                        ( A (inr star))
                        ( B)))) ∘e
                  ( equiv-ev-pair))
                ( refl-htpy)))
            ( is-equiv-precomp-is-equiv
              ( ev-Maybe)
              ( dependent-universal-property-Maybe)
              ( type-Set B)))
          ( is-equiv-precomp-is-equiv
            ( ev-Maybe)
            ( dependent-universal-property-Maybe)
            ( type-Set B)))

module _
  {l : Level} (k : ℕ) (A : Fin k → UU l)
  where

  equiv-distributive-trunc-Π-Fin-Set :
    type-trunc-Set ((x : Fin k) → A x) ≃ ((x : Fin k) → type-trunc-Set (A x))
  equiv-distributive-trunc-Π-Fin-Set =
    pr1 (center (distributive-trunc-Π-Fin-Set k A))

  map-equiv-distributive-trunc-Π-Fin-Set :
    type-trunc-Set ((x : Fin k) → A x) → ((x : Fin k) → type-trunc-Set (A x))
  map-equiv-distributive-trunc-Π-Fin-Set =
    map-equiv equiv-distributive-trunc-Π-Fin-Set

  triangle-distributive-trunc-Π-Fin-Set :
    ( map-equiv-distributive-trunc-Π-Fin-Set ∘ unit-trunc-Set) ~
    ( map-Π (λ x → unit-trunc-Set))
  triangle-distributive-trunc-Π-Fin-Set =
    pr2 (center (distributive-trunc-Π-Fin-Set k A))

module _
  {l1 l2 : Level} {A : UU l1} (B : A → UU l2)
  where

  abstract
    distributive-trunc-Π-count-Set :
      count A → 
      is-contr
        ( Σ ( ( type-trunc-Set ((x : A) → B x)) ≃
              ( (x : A) → type-trunc-Set (B x)))
            ( λ e →
              ( map-equiv e ∘ unit-trunc-Set) ~
              ( map-Π (λ x → unit-trunc-Set))))
    distributive-trunc-Π-count-Set (pair k e) =
      is-contr-equiv
        ( Σ ( ( type-trunc-Set ((x : A) → B x)) ≃
              ( (x : Fin k) → type-trunc-Set (B (map-equiv e x))))
            ( λ f →
              ( map-equiv f ∘ unit-trunc-Set) ~
              ( map-Π (λ x → unit-trunc-Set) ∘ precomp-Π (map-equiv e) B)))
        ( equiv-Σ
          ( λ f →
            ( map-equiv f ∘ unit-trunc-Set) ~
            ( map-Π (λ x → unit-trunc-Set) ∘ precomp-Π (map-equiv e) B))
          ( equiv-postcomp-equiv
            ( equiv-precomp-Π e (type-trunc-Set ∘ B))
            ( type-trunc-Set ((x : A) → B x)))
          ( λ f →
            equiv-map-Π
              ( λ h →
                ( ( inv-equiv equiv-funext) ∘e
                  ( equiv-precomp-Π e
                    ( λ x → Id ((map-equiv f ∘ unit-trunc-Set) h x)
                    ( map-Π (λ y → unit-trunc-Set) h x)))) ∘e
                ( equiv-funext))))
        ( is-contr-equiv&#39;
          ( Σ ( ( type-trunc-Set ((x : Fin k) → B (map-equiv e x))) ≃
                ( (x : Fin k) → type-trunc-Set (B (map-equiv e x))))
              ( λ f →
                ( map-equiv f ∘ unit-trunc-Set) ~
                ( map-Π (λ x → unit-trunc-Set))))
          ( equiv-Σ
            ( λ f →
              ( map-equiv f ∘ unit-trunc-Set) ~
              ( map-Π (λ x → unit-trunc-Set) ∘ precomp-Π (map-equiv e) B))
            ( equiv-precomp-equiv
              ( equiv-trunc-Set (equiv-precomp-Π e B))
              ( (x : Fin k) → type-trunc-Set (B (map-equiv e x))))
            ( λ f →
              equiv-Π
                ( λ h →
                  Id ( map-equiv f
                       ( map-equiv
                         ( equiv-trunc-Set (equiv-precomp-Π e B))
                         ( unit-trunc-Set h)))
                     ( map-Π (λ x → unit-trunc-Set) (λ x → h (map-equiv e x))))
                ( equiv-Π B e (λ x → id-equiv))
                ( λ h →
                  ( ( inv-equiv equiv-funext) ∘e
                    ( equiv-Π
                      ( λ x →
                        Id ( map-equiv f
                             ( map-equiv-trunc-Set
                               ( equiv-precomp-Π e B)
                               ( unit-trunc-Set
                                 ( map-equiv-Π B e (λ x → id-equiv) h)))
                             ( x))
                           ( unit-trunc-Set
                             ( map-equiv-Π B e
                               ( λ z → id-equiv)
                               ( h)
                               ( map-equiv e x))))
                      ( id-equiv)
                      ( λ x →
                        ( equiv-concat
                          ( ap
                            ( λ t → map-equiv f t x)
                            ( ( naturality-trunc-Set (precomp-Π (map-equiv e) B)
                                ( map-equiv-Π B e (λ _ → id-equiv) h)) ∙
                              ( ap
                                ( unit-trunc-Set)
                                ( eq-htpy
                                  ( compute-map-equiv-Π B e
                                    ( λ _ → id-equiv)
                                    ( h))))))
                          ( unit-trunc-Set
                            ( map-equiv-Π B e
                              ( λ _ → id-equiv)
                              ( h)
                              ( map-equiv e x)))) ∘e
                        ( equiv-concat&#39;
                          ( map-equiv f (unit-trunc-Set h) x)
                          ( ap unit-trunc-Set
                            ( inv
                              ( compute-map-equiv-Π B e
                                ( λ _ → id-equiv)
                                ( h)
                                ( x)))))))) ∘e
                  ( equiv-funext))))
          ( distributive-trunc-Π-Fin-Set k (B ∘ map-equiv e)))

module _
  {l1 l2 : Level} {A : UU l1} (B : A → UU l2) (c : count A)
  where

  equiv-distributive-trunc-Π-count-Set :
    ( type-trunc-Set ((x : A) → B x)) ≃ ((x : A) → type-trunc-Set (B x))
  equiv-distributive-trunc-Π-count-Set =
    pr1 (center (distributive-trunc-Π-count-Set B c))

  map-equiv-distributive-trunc-Π-count-Set :
    ( type-trunc-Set ((x : A) → B x)) → ((x : A) → type-trunc-Set (B x))
  map-equiv-distributive-trunc-Π-count-Set =
    map-equiv equiv-distributive-trunc-Π-count-Set

  triangle-distributive-trunc-Π-count-Set :
    ( map-equiv-distributive-trunc-Π-count-Set ∘ unit-trunc-Set) ~
    ( map-Π (λ x → unit-trunc-Set))
  triangle-distributive-trunc-Π-count-Set =
    pr2 (center (distributive-trunc-Π-count-Set B c))

module _
  {l1 l2 : Level} {A : UU l1} (B : A → UU l2) (H : is-finite A)
  where

  abstract
    distributive-trunc-Π-is-finite-Set :
      is-contr
        ( Σ ( ( type-trunc-Set ((x : A) → B x)) ≃
              ( (x : A) → type-trunc-Set (B x)))
            ( λ e →
              ( map-equiv e ∘ unit-trunc-Set) ~
              ( map-Π (λ x → unit-trunc-Set))))
    distributive-trunc-Π-is-finite-Set =
      apply-universal-property-trunc-Prop H
        ( is-contr-Prop _)
        ( distributive-trunc-Π-count-Set B)

  equiv-distributive-trunc-Π-is-finite-Set :
    ( type-trunc-Set ((x : A) → B x)) ≃ ((x : A) → type-trunc-Set (B x))
  equiv-distributive-trunc-Π-is-finite-Set =
    pr1 (center distributive-trunc-Π-is-finite-Set)

  map-equiv-distributive-trunc-Π-is-finite-Set :
    ( type-trunc-Set ((x : A) → B x)) → ((x : A) → type-trunc-Set (B x))
  map-equiv-distributive-trunc-Π-is-finite-Set =
    map-equiv equiv-distributive-trunc-Π-is-finite-Set

  triangle-distributive-trunc-Π-is-finite-Set :
    ( map-equiv-distributive-trunc-Π-is-finite-Set ∘ unit-trunc-Set) ~
    ( map-Π (λ x → unit-trunc-Set))
  triangle-distributive-trunc-Π-is-finite-Set =
    pr2 (center distributive-trunc-Π-is-finite-Set)
    -}</a>
</pre>