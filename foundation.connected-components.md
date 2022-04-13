# Connected components of types

<pre class="Agda"><a id="42" class="Symbol">{-#</a> <a id="46" class="Keyword">OPTIONS</a> <a id="54" class="Pragma">--without-K</a> <a id="66" class="Pragma">--exact-split</a> <a id="80" class="Symbol">#-}</a>

<a id="85" class="Keyword">module</a> <a id="92" href="foundation.connected-components.html" class="Module">foundation.connected-components</a> <a id="124" class="Keyword">where</a>

<a id="131" class="Keyword">open</a> <a id="136" class="Keyword">import</a> <a id="143" href="foundation.connected-types.html" class="Module">foundation.connected-types</a> <a id="170" class="Keyword">using</a> <a id="176" class="Symbol">(</a><a id="177" href="foundation.connected-types.html#1682" class="Function">is-path-connected</a><a id="194" class="Symbol">;</a> <a id="196" href="foundation.connected-types.html#2287" class="Function">is-path-connected-mere-eq</a><a id="221" class="Symbol">)</a>
<a id="223" class="Keyword">open</a> <a id="228" class="Keyword">import</a> <a id="235" href="foundation.dependent-pair-types.html" class="Module">foundation.dependent-pair-types</a> <a id="267" class="Keyword">using</a> <a id="273" class="Symbol">(</a><a id="274" href="foundation-core.dependent-pair-types.html#502" class="Record">Σ</a><a id="275" class="Symbol">;</a> <a id="277" href="foundation-core.dependent-pair-types.html#575" class="InductiveConstructor">pair</a><a id="281" class="Symbol">;</a> <a id="283" href="foundation-core.dependent-pair-types.html#592" class="Field">pr1</a><a id="286" class="Symbol">;</a> <a id="288" href="foundation-core.dependent-pair-types.html#604" class="Field">pr2</a><a id="291" class="Symbol">)</a>
<a id="293" class="Keyword">open</a> <a id="298" class="Keyword">import</a> <a id="305" href="foundation.equality-dependent-pair-types.html" class="Module">foundation.equality-dependent-pair-types</a> <a id="346" class="Keyword">using</a> <a id="352" class="Symbol">(</a><a id="353" href="foundation.equality-dependent-pair-types.html#1273" class="Function">eq-pair-Σ</a><a id="362" class="Symbol">)</a>
<a id="364" class="Keyword">open</a> <a id="369" class="Keyword">import</a> <a id="376" href="foundation.identity-types.html" class="Module">foundation.identity-types</a> <a id="402" class="Keyword">using</a> <a id="408" class="Symbol">(</a><a id="409" href="foundation-core.identity-types.html#641" class="Datatype">Id</a><a id="411" class="Symbol">;</a> <a id="413" href="foundation-core.identity-types.html#694" class="InductiveConstructor">refl</a><a id="417" class="Symbol">;</a> <a id="419" href="foundation-core.identity-types.html#1552" class="Function">inv</a><a id="422" class="Symbol">)</a>
<a id="424" class="Keyword">open</a> <a id="429" class="Keyword">import</a> <a id="436" href="foundation.propositional-truncations.html" class="Module">foundation.propositional-truncations</a> <a id="473" class="Keyword">using</a>
  <a id="481" class="Symbol">(</a> <a id="483" href="foundation.propositional-truncations.html#2510" class="Function">trunc-Prop</a><a id="493" class="Symbol">;</a> <a id="495" href="foundation.propositional-truncations.html#2012" class="Function">type-trunc-Prop</a><a id="510" class="Symbol">;</a> <a id="512" href="foundation.propositional-truncations.html#2096" class="Function">unit-trunc-Prop</a><a id="527" class="Symbol">;</a> <a id="529" href="foundation.propositional-truncations.html#5581" class="Function">apply-universal-property-trunc-Prop</a><a id="564" class="Symbol">;</a>
    <a id="570" href="foundation.propositional-truncations.html#2317" class="Function">all-elements-equal-type-trunc-Prop</a><a id="604" class="Symbol">;</a> <a id="606" href="foundation.propositional-truncations.html#2191" class="Function">is-prop-type-trunc-Prop</a><a id="629" class="Symbol">)</a>
<a id="631" class="Keyword">open</a> <a id="636" class="Keyword">import</a> <a id="643" href="foundation.propositions.html" class="Module">foundation.propositions</a> <a id="667" class="Keyword">using</a> <a id="673" class="Symbol">(</a><a id="674" href="foundation.propositions.html#940" class="Function">is-trunc-is-prop</a><a id="690" class="Symbol">)</a>
<a id="692" class="Keyword">open</a> <a id="697" class="Keyword">import</a> <a id="704" href="foundation.truncated-types.html" class="Module">foundation.truncated-types</a> <a id="731" class="Keyword">using</a> <a id="737" class="Symbol">(</a><a id="738" href="foundation-core.truncated-types.html#1466" class="Function">is-trunc</a><a id="746" class="Symbol">;</a> <a id="748" href="foundation-core.truncated-types.html#5489" class="Function">is-trunc-Σ</a><a id="758" class="Symbol">)</a>
<a id="760" class="Keyword">open</a> <a id="765" class="Keyword">import</a> <a id="772" href="foundation.truncation-levels.html" class="Module">foundation.truncation-levels</a> <a id="801" class="Keyword">using</a> <a id="807" class="Symbol">(</a><a id="808" href="foundation-core.truncation-levels.html#382" class="Datatype">𝕋</a><a id="809" class="Symbol">;</a> <a id="811" href="foundation-core.truncation-levels.html#419" class="InductiveConstructor">succ-𝕋</a><a id="817" class="Symbol">)</a>
<a id="819" class="Keyword">open</a> <a id="824" class="Keyword">import</a> <a id="831" href="foundation.universe-levels.html" class="Module">foundation.universe-levels</a> <a id="858" class="Keyword">using</a> <a id="864" class="Symbol">(</a><a id="865" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a><a id="867" class="Symbol">;</a> <a id="869" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="874" class="Symbol">)</a>
</pre>
## Idea

The connected component of a type `A` at an element `a : A` is the type of all `x : A` that are merely equal to `a`.

## Definition

<pre class="Agda"><a id="1031" class="Keyword">module</a> <a id="1038" href="foundation.connected-components.html#1038" class="Module">_</a>
  <a id="1042" class="Symbol">{</a><a id="1043" href="foundation.connected-components.html#1043" class="Bound">l</a> <a id="1045" class="Symbol">:</a> <a id="1047" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="1052" class="Symbol">}</a> <a id="1054" class="Symbol">(</a><a id="1055" href="foundation.connected-components.html#1055" class="Bound">A</a> <a id="1057" class="Symbol">:</a> <a id="1059" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="1062" href="foundation.connected-components.html#1043" class="Bound">l</a><a id="1063" class="Symbol">)</a> <a id="1065" class="Symbol">(</a><a id="1066" href="foundation.connected-components.html#1066" class="Bound">a</a> <a id="1068" class="Symbol">:</a> <a id="1070" href="foundation.connected-components.html#1055" class="Bound">A</a><a id="1071" class="Symbol">)</a>
  <a id="1075" class="Keyword">where</a>

  <a id="1084" href="foundation.connected-components.html#1084" class="Function">connected-component</a> <a id="1104" class="Symbol">:</a> <a id="1106" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="1109" href="foundation.connected-components.html#1043" class="Bound">l</a>
  <a id="1113" href="foundation.connected-components.html#1084" class="Function">connected-component</a> <a id="1133" class="Symbol">=</a>
    <a id="1139" href="foundation-core.dependent-pair-types.html#502" class="Record">Σ</a> <a id="1141" href="foundation.connected-components.html#1055" class="Bound">A</a> <a id="1143" class="Symbol">(λ</a> <a id="1146" href="foundation.connected-components.html#1146" class="Bound">x</a> <a id="1148" class="Symbol">→</a> <a id="1150" href="foundation.propositional-truncations.html#2012" class="Function">type-trunc-Prop</a> <a id="1166" class="Symbol">(</a><a id="1167" href="foundation-core.identity-types.html#641" class="Datatype">Id</a> <a id="1170" href="foundation.connected-components.html#1146" class="Bound">x</a> <a id="1172" href="foundation.connected-components.html#1066" class="Bound">a</a><a id="1173" class="Symbol">))</a>

  <a id="1179" href="foundation.connected-components.html#1179" class="Function">value-connected-component</a> <a id="1205" class="Symbol">:</a>
    <a id="1211" href="foundation.connected-components.html#1084" class="Function">connected-component</a> <a id="1231" class="Symbol">→</a> <a id="1233" href="foundation.connected-components.html#1055" class="Bound">A</a>
  <a id="1237" href="foundation.connected-components.html#1179" class="Function">value-connected-component</a> <a id="1263" href="foundation.connected-components.html#1263" class="Bound">X</a> <a id="1265" class="Symbol">=</a> <a id="1267" href="foundation-core.dependent-pair-types.html#592" class="Field">pr1</a> <a id="1271" href="foundation.connected-components.html#1263" class="Bound">X</a>

  <a id="1276" class="Keyword">abstract</a>
    <a id="1289" href="foundation.connected-components.html#1289" class="Function">mere-equality-connected-component</a> <a id="1323" class="Symbol">:</a> <a id="1325" class="Symbol">(</a><a id="1326" href="foundation.connected-components.html#1326" class="Bound">X</a> <a id="1328" class="Symbol">:</a> <a id="1330" href="foundation.connected-components.html#1084" class="Function">connected-component</a><a id="1349" class="Symbol">)</a> <a id="1351" class="Symbol">→</a>
      <a id="1359" href="foundation.propositional-truncations.html#2012" class="Function">type-trunc-Prop</a> <a id="1375" class="Symbol">(</a><a id="1376" href="foundation-core.identity-types.html#641" class="Datatype">Id</a> <a id="1379" class="Symbol">(</a><a id="1380" href="foundation.connected-components.html#1179" class="Function">value-connected-component</a> <a id="1406" href="foundation.connected-components.html#1326" class="Bound">X</a><a id="1407" class="Symbol">)</a> <a id="1409" href="foundation.connected-components.html#1066" class="Bound">a</a><a id="1410" class="Symbol">)</a>
    <a id="1416" href="foundation.connected-components.html#1289" class="Function">mere-equality-connected-component</a> <a id="1450" href="foundation.connected-components.html#1450" class="Bound">X</a> <a id="1452" class="Symbol">=</a> <a id="1454" href="foundation-core.dependent-pair-types.html#604" class="Field">pr2</a> <a id="1458" href="foundation.connected-components.html#1450" class="Bound">X</a>
</pre>
## Properties

### Connected components are path-connected

<pre class="Agda"><a id="1533" class="Keyword">abstract</a>
  <a id="is-path-connected-connected-component"></a><a id="1544" href="foundation.connected-components.html#1544" class="Function">is-path-connected-connected-component</a> <a id="1582" class="Symbol">:</a>
    <a id="1588" class="Symbol">{</a><a id="1589" href="foundation.connected-components.html#1589" class="Bound">l</a> <a id="1591" class="Symbol">:</a> <a id="1593" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="1598" class="Symbol">}</a> <a id="1600" class="Symbol">(</a><a id="1601" href="foundation.connected-components.html#1601" class="Bound">A</a> <a id="1603" class="Symbol">:</a> <a id="1605" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="1608" href="foundation.connected-components.html#1589" class="Bound">l</a><a id="1609" class="Symbol">)</a> <a id="1611" class="Symbol">(</a><a id="1612" href="foundation.connected-components.html#1612" class="Bound">a</a> <a id="1614" class="Symbol">:</a> <a id="1616" href="foundation.connected-components.html#1601" class="Bound">A</a><a id="1617" class="Symbol">)</a> <a id="1619" class="Symbol">→</a>
    <a id="1625" href="foundation.connected-types.html#1682" class="Function">is-path-connected</a> <a id="1643" class="Symbol">(</a><a id="1644" href="foundation.connected-components.html#1084" class="Function">connected-component</a> <a id="1664" href="foundation.connected-components.html#1601" class="Bound">A</a> <a id="1666" href="foundation.connected-components.html#1612" class="Bound">a</a><a id="1667" class="Symbol">)</a>
  <a id="1671" href="foundation.connected-components.html#1544" class="Function">is-path-connected-connected-component</a> <a id="1709" href="foundation.connected-components.html#1709" class="Bound">A</a> <a id="1711" href="foundation.connected-components.html#1711" class="Bound">a</a> <a id="1713" class="Symbol">=</a>
    <a id="1719" href="foundation.connected-types.html#2287" class="Function">is-path-connected-mere-eq</a>
      <a id="1751" class="Symbol">(</a> <a id="1753" href="foundation-core.dependent-pair-types.html#575" class="InductiveConstructor">pair</a> <a id="1758" href="foundation.connected-components.html#1711" class="Bound">a</a> <a id="1760" class="Symbol">(</a><a id="1761" href="foundation.propositional-truncations.html#2096" class="Function">unit-trunc-Prop</a> <a id="1777" href="foundation-core.identity-types.html#694" class="InductiveConstructor">refl</a><a id="1781" class="Symbol">))</a>
      <a id="1790" class="Symbol">(</a> <a id="1792" class="Symbol">λ</a> <a id="1794" class="Symbol">(</a><a id="1795" href="foundation-core.dependent-pair-types.html#575" class="InductiveConstructor">pair</a> <a id="1800" href="foundation.connected-components.html#1800" class="Bound">x</a> <a id="1802" href="foundation.connected-components.html#1802" class="Bound">p</a><a id="1803" class="Symbol">)</a> <a id="1805" class="Symbol">→</a>
        <a id="1815" href="foundation.propositional-truncations.html#5581" class="Function">apply-universal-property-trunc-Prop</a>
          <a id="1861" class="Symbol">(</a> <a id="1863" href="foundation.connected-components.html#1802" class="Bound">p</a><a id="1864" class="Symbol">)</a>
          <a id="1876" class="Symbol">(</a> <a id="1878" href="foundation.propositional-truncations.html#2510" class="Function">trunc-Prop</a> <a id="1889" class="Symbol">(</a><a id="1890" href="foundation-core.identity-types.html#641" class="Datatype">Id</a> <a id="1893" class="Symbol">(</a><a id="1894" href="foundation-core.dependent-pair-types.html#575" class="InductiveConstructor">pair</a> <a id="1899" href="foundation.connected-components.html#1711" class="Bound">a</a> <a id="1901" class="Symbol">(</a><a id="1902" href="foundation.propositional-truncations.html#2096" class="Function">unit-trunc-Prop</a> <a id="1918" href="foundation-core.identity-types.html#694" class="InductiveConstructor">refl</a><a id="1922" class="Symbol">))</a> <a id="1925" class="Symbol">(</a><a id="1926" href="foundation-core.dependent-pair-types.html#575" class="InductiveConstructor">pair</a> <a id="1931" href="foundation.connected-components.html#1800" class="Bound">x</a> <a id="1933" href="foundation.connected-components.html#1802" class="Bound">p</a><a id="1934" class="Symbol">)))</a>
          <a id="1948" class="Symbol">(</a> <a id="1950" class="Symbol">λ</a> <a id="1952" href="foundation.connected-components.html#1952" class="Bound">p&#39;</a> <a id="1955" class="Symbol">→</a>
            <a id="1969" href="foundation.propositional-truncations.html#2096" class="Function">unit-trunc-Prop</a>
              <a id="1999" class="Symbol">(</a> <a id="2001" href="foundation.equality-dependent-pair-types.html#1273" class="Function">eq-pair-Σ</a>
                <a id="2027" class="Symbol">(</a> <a id="2029" href="foundation-core.identity-types.html#1552" class="Function">inv</a> <a id="2033" href="foundation.connected-components.html#1952" class="Bound">p&#39;</a><a id="2035" class="Symbol">)</a>
                <a id="2053" class="Symbol">(</a> <a id="2055" href="foundation.propositional-truncations.html#2317" class="Function">all-elements-equal-type-trunc-Prop</a> <a id="2090" class="Symbol">_</a> <a id="2092" href="foundation.connected-components.html#1802" class="Bound">p</a><a id="2093" class="Symbol">))))</a>
</pre>
### If `A` is (k+1)-truncated, then the connected component of `a` in `A` is (k+1)-truncated.

<pre class="Agda"><a id="is-trunc-connected-component"></a><a id="2206" href="foundation.connected-components.html#2206" class="Function">is-trunc-connected-component</a> <a id="2235" class="Symbol">:</a>
  <a id="2239" class="Symbol">{</a><a id="2240" href="foundation.connected-components.html#2240" class="Bound">l</a> <a id="2242" class="Symbol">:</a> <a id="2244" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="2249" class="Symbol">}</a> <a id="2251" class="Symbol">{</a><a id="2252" href="foundation.connected-components.html#2252" class="Bound">k</a> <a id="2254" class="Symbol">:</a> <a id="2256" href="foundation-core.truncation-levels.html#382" class="Datatype">𝕋</a><a id="2257" class="Symbol">}</a> <a id="2259" class="Symbol">(</a><a id="2260" href="foundation.connected-components.html#2260" class="Bound">A</a> <a id="2262" class="Symbol">:</a> <a id="2264" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="2267" href="foundation.connected-components.html#2240" class="Bound">l</a><a id="2268" class="Symbol">)</a> <a id="2270" class="Symbol">(</a><a id="2271" href="foundation.connected-components.html#2271" class="Bound">a</a> <a id="2273" class="Symbol">:</a> <a id="2275" href="foundation.connected-components.html#2260" class="Bound">A</a><a id="2276" class="Symbol">)</a> <a id="2278" class="Symbol">→</a>
  <a id="2282" href="foundation-core.truncated-types.html#1466" class="Function">is-trunc</a> <a id="2291" class="Symbol">(</a><a id="2292" href="foundation-core.truncation-levels.html#419" class="InductiveConstructor">succ-𝕋</a> <a id="2299" href="foundation.connected-components.html#2252" class="Bound">k</a><a id="2300" class="Symbol">)</a> <a id="2302" href="foundation.connected-components.html#2260" class="Bound">A</a> <a id="2304" class="Symbol">→</a> <a id="2306" href="foundation-core.truncated-types.html#1466" class="Function">is-trunc</a> <a id="2315" class="Symbol">(</a><a id="2316" href="foundation-core.truncation-levels.html#419" class="InductiveConstructor">succ-𝕋</a> <a id="2323" href="foundation.connected-components.html#2252" class="Bound">k</a><a id="2324" class="Symbol">)</a> <a id="2326" class="Symbol">(</a><a id="2327" href="foundation.connected-components.html#1084" class="Function">connected-component</a> <a id="2347" href="foundation.connected-components.html#2260" class="Bound">A</a> <a id="2349" href="foundation.connected-components.html#2271" class="Bound">a</a><a id="2350" class="Symbol">)</a>
<a id="2352" href="foundation.connected-components.html#2206" class="Function">is-trunc-connected-component</a> <a id="2381" class="Symbol">{</a><a id="2382" href="foundation.connected-components.html#2382" class="Bound">l</a><a id="2383" class="Symbol">}</a> <a id="2385" class="Symbol">{</a><a id="2386" href="foundation.connected-components.html#2386" class="Bound">k</a><a id="2387" class="Symbol">}</a> <a id="2389" href="foundation.connected-components.html#2389" class="Bound">A</a> <a id="2391" href="foundation.connected-components.html#2391" class="Bound">a</a> <a id="2393" href="foundation.connected-components.html#2393" class="Bound">H</a> <a id="2395" class="Symbol">=</a>
  <a id="2399" href="foundation-core.truncated-types.html#5489" class="Function">is-trunc-Σ</a> <a id="2410" href="foundation.connected-components.html#2393" class="Bound">H</a> <a id="2412" class="Symbol">(λ</a> <a id="2415" href="foundation.connected-components.html#2415" class="Bound">x</a> <a id="2417" class="Symbol">→</a> <a id="2419" href="foundation.propositions.html#940" class="Function">is-trunc-is-prop</a> <a id="2436" href="foundation.connected-components.html#2386" class="Bound">k</a> <a id="2438" href="foundation.propositional-truncations.html#2191" class="Function">is-prop-type-trunc-Prop</a><a id="2461" class="Symbol">)</a>

</pre>