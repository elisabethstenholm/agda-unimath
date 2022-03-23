# Functoriality of the loop space operation

<pre class="Agda"><a id="54" class="Symbol">{-#</a> <a id="58" class="Keyword">OPTIONS</a> <a id="66" class="Pragma">--without-K</a> <a id="78" class="Pragma">--exact-split</a> <a id="92" class="Symbol">#-}</a>

<a id="97" class="Keyword">module</a> <a id="104" href="synthetic-homotopy-theory.functoriality-loop-spaces.html" class="Module">synthetic-homotopy-theory.functoriality-loop-spaces</a> <a id="156" class="Keyword">where</a>

<a id="163" class="Keyword">open</a> <a id="168" class="Keyword">import</a> <a id="175" href="foundation.dependent-pair-types.html" class="Module">foundation.dependent-pair-types</a> <a id="207" class="Keyword">using</a> <a id="213" class="Symbol">(</a><a id="214" href="foundation-core.dependent-pair-types.html#502" class="Record">Σ</a><a id="215" class="Symbol">;</a> <a id="217" href="foundation-core.dependent-pair-types.html#575" class="InductiveConstructor">pair</a><a id="221" class="Symbol">;</a> <a id="223" href="foundation-core.dependent-pair-types.html#592" class="Field">pr1</a><a id="226" class="Symbol">;</a> <a id="228" href="foundation-core.dependent-pair-types.html#604" class="Field">pr2</a><a id="231" class="Symbol">)</a>
<a id="233" class="Keyword">open</a> <a id="238" class="Keyword">import</a> <a id="245" href="foundation.identity-types.html" class="Module">foundation.identity-types</a> <a id="271" class="Keyword">using</a>
  <a id="279" class="Symbol">(</a> <a id="281" href="foundation-core.identity-types.html#641" class="Datatype">Id</a><a id="283" class="Symbol">;</a> <a id="285" href="foundation-core.identity-types.html#694" class="InductiveConstructor">refl</a><a id="289" class="Symbol">;</a> <a id="291" href="foundation-core.identity-types.html#2853" class="Function">ap</a><a id="293" class="Symbol">;</a> <a id="295" href="foundation-core.identity-types.html#7592" class="Function">ap-concat</a><a id="304" class="Symbol">;</a> <a id="306" href="foundation-core.identity-types.html#1239" class="Function Operator">_∙_</a><a id="309" class="Symbol">;</a> <a id="311" href="foundation-core.identity-types.html#7763" class="Function">ap-inv</a><a id="317" class="Symbol">)</a>
<a id="319" class="Keyword">open</a> <a id="324" class="Keyword">import</a> <a id="331" href="foundation.universe-levels.html" class="Module">foundation.universe-levels</a> <a id="358" class="Keyword">using</a> <a id="364" class="Symbol">(</a><a id="365" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="370" class="Symbol">;</a> <a id="372" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a><a id="374" class="Symbol">)</a>

<a id="377" class="Keyword">open</a> <a id="382" class="Keyword">import</a> <a id="389" href="synthetic-homotopy-theory.loop-spaces.html" class="Module">synthetic-homotopy-theory.loop-spaces</a> <a id="427" class="Keyword">using</a>
  <a id="435" class="Symbol">(</a> <a id="437" href="synthetic-homotopy-theory.loop-spaces.html#937" class="Function">type-Ω</a><a id="443" class="Symbol">;</a> <a id="445" href="synthetic-homotopy-theory.loop-spaces.html#2151" class="Function">tr-type-Ω</a><a id="454" class="Symbol">;</a> <a id="456" href="synthetic-homotopy-theory.loop-spaces.html#2385" class="Function">preserves-refl-tr-Ω</a><a id="475" class="Symbol">;</a> <a id="477" href="synthetic-homotopy-theory.loop-spaces.html#1043" class="Function">Ω</a><a id="478" class="Symbol">;</a> <a id="480" href="synthetic-homotopy-theory.loop-spaces.html#1132" class="Function">mul-Ω</a><a id="485" class="Symbol">;</a> <a id="487" href="synthetic-homotopy-theory.loop-spaces.html#2486" class="Function">preserves-mul-tr-Ω</a><a id="505" class="Symbol">;</a> <a id="507" href="synthetic-homotopy-theory.loop-spaces.html#1188" class="Function">inv-Ω</a><a id="512" class="Symbol">;</a>
    <a id="518" href="synthetic-homotopy-theory.loop-spaces.html#2696" class="Function">preserves-inv-tr-Ω</a><a id="536" class="Symbol">)</a>
<a id="538" class="Keyword">open</a> <a id="543" class="Keyword">import</a> <a id="550" href="synthetic-homotopy-theory.pointed-maps.html" class="Module">synthetic-homotopy-theory.pointed-maps</a> <a id="589" class="Keyword">using</a>
  <a id="597" class="Symbol">(</a> <a id="599" href="synthetic-homotopy-theory.pointed-maps.html#1003" class="Function Operator">_→*_</a><a id="603" class="Symbol">;</a> <a id="605" href="synthetic-homotopy-theory.pointed-maps.html#1516" class="Function">preserves-point-map-pointed-map</a><a id="636" class="Symbol">;</a> <a id="638" href="synthetic-homotopy-theory.pointed-maps.html#1416" class="Function">map-pointed-map</a><a id="653" class="Symbol">)</a>
<a id="655" class="Keyword">open</a> <a id="660" class="Keyword">import</a> <a id="667" href="synthetic-homotopy-theory.pointed-types.html" class="Module">synthetic-homotopy-theory.pointed-types</a> <a id="707" class="Keyword">using</a>
  <a id="715" class="Symbol">(</a> <a id="717" href="synthetic-homotopy-theory.pointed-types.html#392" class="Function">Pointed-Type</a><a id="729" class="Symbol">)</a>
</pre>
## Idea

Any pointed map `f : A →* B` induces a map `map-Ω f : Ω A →* Ω B`. Furthermore, this operation respects the groupoidal operations on loop spaces.

## Definition

<pre class="Agda"><a id="915" class="Keyword">module</a> <a id="922" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#922" class="Module">_</a>
  <a id="926" class="Symbol">{</a><a id="927" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#927" class="Bound">l1</a> <a id="930" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#930" class="Bound">l2</a> <a id="933" class="Symbol">:</a> <a id="935" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="940" class="Symbol">}</a> <a id="942" class="Symbol">(</a><a id="943" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#943" class="Bound">A</a> <a id="945" class="Symbol">:</a> <a id="947" href="synthetic-homotopy-theory.pointed-types.html#392" class="Function">Pointed-Type</a> <a id="960" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#927" class="Bound">l1</a><a id="962" class="Symbol">)</a> <a id="964" class="Symbol">(</a><a id="965" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#965" class="Bound">B</a> <a id="967" class="Symbol">:</a> <a id="969" href="synthetic-homotopy-theory.pointed-types.html#392" class="Function">Pointed-Type</a> <a id="982" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#930" class="Bound">l2</a><a id="984" class="Symbol">)</a> <a id="986" class="Symbol">(</a><a id="987" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#987" class="Bound">f</a> <a id="989" class="Symbol">:</a> <a id="991" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#943" class="Bound">A</a> <a id="993" href="synthetic-homotopy-theory.pointed-maps.html#1003" class="Function Operator">→*</a> <a id="996" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#965" class="Bound">B</a><a id="997" class="Symbol">)</a>
  <a id="1001" class="Keyword">where</a>

  <a id="1010" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#1010" class="Function">map-Ω</a> <a id="1016" class="Symbol">:</a> <a id="1018" href="synthetic-homotopy-theory.loop-spaces.html#937" class="Function">type-Ω</a> <a id="1025" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#943" class="Bound">A</a> <a id="1027" class="Symbol">→</a> <a id="1029" href="synthetic-homotopy-theory.loop-spaces.html#937" class="Function">type-Ω</a> <a id="1036" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#965" class="Bound">B</a>
  <a id="1040" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#1010" class="Function">map-Ω</a> <a id="1046" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#1046" class="Bound">p</a> <a id="1048" class="Symbol">=</a>
    <a id="1054" href="synthetic-homotopy-theory.loop-spaces.html#2151" class="Function">tr-type-Ω</a>
      <a id="1070" class="Symbol">(</a> <a id="1072" href="synthetic-homotopy-theory.pointed-maps.html#1516" class="Function">preserves-point-map-pointed-map</a> <a id="1104" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#943" class="Bound">A</a> <a id="1106" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#965" class="Bound">B</a> <a id="1108" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#987" class="Bound">f</a><a id="1109" class="Symbol">)</a>
      <a id="1117" class="Symbol">(</a> <a id="1119" href="foundation-core.identity-types.html#2853" class="Function">ap</a> <a id="1122" class="Symbol">(</a><a id="1123" href="synthetic-homotopy-theory.pointed-maps.html#1416" class="Function">map-pointed-map</a> <a id="1139" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#943" class="Bound">A</a> <a id="1141" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#965" class="Bound">B</a> <a id="1143" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#987" class="Bound">f</a><a id="1144" class="Symbol">)</a> <a id="1146" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#1046" class="Bound">p</a><a id="1147" class="Symbol">)</a>
  
  <a id="1154" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#1154" class="Function">preserves-refl-map-Ω</a> <a id="1175" class="Symbol">:</a> <a id="1177" href="foundation-core.identity-types.html#641" class="Datatype">Id</a> <a id="1180" class="Symbol">(</a><a id="1181" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#1010" class="Function">map-Ω</a> <a id="1187" href="foundation-core.identity-types.html#694" class="InductiveConstructor">refl</a><a id="1191" class="Symbol">)</a> <a id="1193" href="foundation-core.identity-types.html#694" class="InductiveConstructor">refl</a>
  <a id="1200" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#1154" class="Function">preserves-refl-map-Ω</a> <a id="1221" class="Symbol">=</a> <a id="1223" href="synthetic-homotopy-theory.loop-spaces.html#2385" class="Function">preserves-refl-tr-Ω</a> <a id="1243" class="Symbol">(</a><a id="1244" href="foundation-core.dependent-pair-types.html#604" class="Field">pr2</a> <a id="1248" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#987" class="Bound">f</a><a id="1249" class="Symbol">)</a>

  <a id="1254" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#1254" class="Function">pointed-map-Ω</a> <a id="1268" class="Symbol">:</a> <a id="1270" href="synthetic-homotopy-theory.loop-spaces.html#1043" class="Function">Ω</a> <a id="1272" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#943" class="Bound">A</a> <a id="1274" href="synthetic-homotopy-theory.pointed-maps.html#1003" class="Function Operator">→*</a> <a id="1277" href="synthetic-homotopy-theory.loop-spaces.html#1043" class="Function">Ω</a> <a id="1279" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#965" class="Bound">B</a>
  <a id="1283" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#1254" class="Function">pointed-map-Ω</a> <a id="1297" class="Symbol">=</a> <a id="1299" href="foundation-core.dependent-pair-types.html#575" class="InductiveConstructor">pair</a> <a id="1304" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#1010" class="Function">map-Ω</a> <a id="1310" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#1154" class="Function">preserves-refl-map-Ω</a>

  <a id="1334" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#1334" class="Function">preserves-mul-map-Ω</a> <a id="1354" class="Symbol">:</a>
    <a id="1360" class="Symbol">(</a><a id="1361" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#1361" class="Bound">x</a> <a id="1363" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#1363" class="Bound">y</a> <a id="1365" class="Symbol">:</a> <a id="1367" href="synthetic-homotopy-theory.loop-spaces.html#937" class="Function">type-Ω</a> <a id="1374" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#943" class="Bound">A</a><a id="1375" class="Symbol">)</a> <a id="1377" class="Symbol">→</a> <a id="1379" href="foundation-core.identity-types.html#641" class="Datatype">Id</a> <a id="1382" class="Symbol">(</a><a id="1383" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#1010" class="Function">map-Ω</a> <a id="1389" class="Symbol">(</a><a id="1390" href="synthetic-homotopy-theory.loop-spaces.html#1132" class="Function">mul-Ω</a> <a id="1396" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#943" class="Bound">A</a> <a id="1398" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#1361" class="Bound">x</a> <a id="1400" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#1363" class="Bound">y</a><a id="1401" class="Symbol">))</a> <a id="1404" class="Symbol">(</a><a id="1405" href="synthetic-homotopy-theory.loop-spaces.html#1132" class="Function">mul-Ω</a> <a id="1411" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#965" class="Bound">B</a> <a id="1413" class="Symbol">(</a><a id="1414" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#1010" class="Function">map-Ω</a> <a id="1420" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#1361" class="Bound">x</a><a id="1421" class="Symbol">)</a> <a id="1423" class="Symbol">(</a><a id="1424" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#1010" class="Function">map-Ω</a> <a id="1430" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#1363" class="Bound">y</a><a id="1431" class="Symbol">))</a>
  <a id="1436" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#1334" class="Function">preserves-mul-map-Ω</a> <a id="1456" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#1456" class="Bound">x</a> <a id="1458" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#1458" class="Bound">y</a> <a id="1460" class="Symbol">=</a>
    <a id="1466" class="Symbol">(</a> <a id="1468" href="foundation-core.identity-types.html#2853" class="Function">ap</a>
      <a id="1477" class="Symbol">(</a> <a id="1479" href="synthetic-homotopy-theory.loop-spaces.html#2151" class="Function">tr-type-Ω</a> <a id="1489" class="Symbol">(</a><a id="1490" href="synthetic-homotopy-theory.pointed-maps.html#1516" class="Function">preserves-point-map-pointed-map</a> <a id="1522" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#943" class="Bound">A</a> <a id="1524" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#965" class="Bound">B</a> <a id="1526" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#987" class="Bound">f</a><a id="1527" class="Symbol">))</a>
      <a id="1536" class="Symbol">(</a> <a id="1538" href="foundation-core.identity-types.html#7592" class="Function">ap-concat</a> <a id="1548" class="Symbol">(</a><a id="1549" href="synthetic-homotopy-theory.pointed-maps.html#1416" class="Function">map-pointed-map</a> <a id="1565" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#943" class="Bound">A</a> <a id="1567" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#965" class="Bound">B</a> <a id="1569" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#987" class="Bound">f</a><a id="1570" class="Symbol">)</a> <a id="1572" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#1456" class="Bound">x</a> <a id="1574" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#1458" class="Bound">y</a><a id="1575" class="Symbol">))</a> <a id="1578" href="foundation-core.identity-types.html#1239" class="Function Operator">∙</a>
    <a id="1584" class="Symbol">(</a> <a id="1586" href="synthetic-homotopy-theory.loop-spaces.html#2486" class="Function">preserves-mul-tr-Ω</a>
      <a id="1611" class="Symbol">(</a> <a id="1613" href="synthetic-homotopy-theory.pointed-maps.html#1516" class="Function">preserves-point-map-pointed-map</a> <a id="1645" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#943" class="Bound">A</a> <a id="1647" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#965" class="Bound">B</a> <a id="1649" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#987" class="Bound">f</a><a id="1650" class="Symbol">)</a>
      <a id="1658" class="Symbol">(</a> <a id="1660" href="foundation-core.identity-types.html#2853" class="Function">ap</a> <a id="1663" class="Symbol">(</a><a id="1664" href="synthetic-homotopy-theory.pointed-maps.html#1416" class="Function">map-pointed-map</a> <a id="1680" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#943" class="Bound">A</a> <a id="1682" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#965" class="Bound">B</a> <a id="1684" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#987" class="Bound">f</a><a id="1685" class="Symbol">)</a> <a id="1687" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#1456" class="Bound">x</a><a id="1688" class="Symbol">)</a>
      <a id="1696" class="Symbol">(</a> <a id="1698" href="foundation-core.identity-types.html#2853" class="Function">ap</a> <a id="1701" class="Symbol">(</a><a id="1702" href="synthetic-homotopy-theory.pointed-maps.html#1416" class="Function">map-pointed-map</a> <a id="1718" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#943" class="Bound">A</a> <a id="1720" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#965" class="Bound">B</a> <a id="1722" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#987" class="Bound">f</a><a id="1723" class="Symbol">)</a> <a id="1725" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#1458" class="Bound">y</a><a id="1726" class="Symbol">))</a>

  <a id="1732" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#1732" class="Function">preserves-inv-map-Ω</a> <a id="1752" class="Symbol">:</a>
    <a id="1758" class="Symbol">(</a><a id="1759" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#1759" class="Bound">x</a> <a id="1761" class="Symbol">:</a> <a id="1763" href="synthetic-homotopy-theory.loop-spaces.html#937" class="Function">type-Ω</a> <a id="1770" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#943" class="Bound">A</a><a id="1771" class="Symbol">)</a> <a id="1773" class="Symbol">→</a> <a id="1775" href="foundation-core.identity-types.html#641" class="Datatype">Id</a> <a id="1778" class="Symbol">(</a><a id="1779" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#1010" class="Function">map-Ω</a> <a id="1785" class="Symbol">(</a><a id="1786" href="synthetic-homotopy-theory.loop-spaces.html#1188" class="Function">inv-Ω</a> <a id="1792" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#943" class="Bound">A</a> <a id="1794" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#1759" class="Bound">x</a><a id="1795" class="Symbol">))</a> <a id="1798" class="Symbol">(</a><a id="1799" href="synthetic-homotopy-theory.loop-spaces.html#1188" class="Function">inv-Ω</a> <a id="1805" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#965" class="Bound">B</a> <a id="1807" class="Symbol">(</a><a id="1808" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#1010" class="Function">map-Ω</a> <a id="1814" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#1759" class="Bound">x</a><a id="1815" class="Symbol">))</a>
  <a id="1820" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#1732" class="Function">preserves-inv-map-Ω</a> <a id="1840" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#1840" class="Bound">x</a> <a id="1842" class="Symbol">=</a>
    <a id="1848" class="Symbol">(</a> <a id="1850" href="foundation-core.identity-types.html#2853" class="Function">ap</a>
      <a id="1859" class="Symbol">(</a> <a id="1861" href="synthetic-homotopy-theory.loop-spaces.html#2151" class="Function">tr-type-Ω</a> <a id="1871" class="Symbol">(</a><a id="1872" href="synthetic-homotopy-theory.pointed-maps.html#1516" class="Function">preserves-point-map-pointed-map</a> <a id="1904" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#943" class="Bound">A</a> <a id="1906" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#965" class="Bound">B</a> <a id="1908" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#987" class="Bound">f</a><a id="1909" class="Symbol">))</a>
      <a id="1918" class="Symbol">(</a> <a id="1920" href="foundation-core.identity-types.html#7763" class="Function">ap-inv</a> <a id="1927" class="Symbol">(</a><a id="1928" href="synthetic-homotopy-theory.pointed-maps.html#1416" class="Function">map-pointed-map</a> <a id="1944" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#943" class="Bound">A</a> <a id="1946" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#965" class="Bound">B</a> <a id="1948" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#987" class="Bound">f</a><a id="1949" class="Symbol">)</a> <a id="1951" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#1840" class="Bound">x</a><a id="1952" class="Symbol">))</a> <a id="1955" href="foundation-core.identity-types.html#1239" class="Function Operator">∙</a>
    <a id="1961" class="Symbol">(</a> <a id="1963" href="synthetic-homotopy-theory.loop-spaces.html#2696" class="Function">preserves-inv-tr-Ω</a>
      <a id="1988" class="Symbol">(</a> <a id="1990" href="synthetic-homotopy-theory.pointed-maps.html#1516" class="Function">preserves-point-map-pointed-map</a> <a id="2022" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#943" class="Bound">A</a> <a id="2024" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#965" class="Bound">B</a> <a id="2026" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#987" class="Bound">f</a><a id="2027" class="Symbol">)</a>
      <a id="2035" class="Symbol">(</a> <a id="2037" href="foundation-core.identity-types.html#2853" class="Function">ap</a> <a id="2040" class="Symbol">(</a><a id="2041" href="synthetic-homotopy-theory.pointed-maps.html#1416" class="Function">map-pointed-map</a> <a id="2057" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#943" class="Bound">A</a> <a id="2059" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#965" class="Bound">B</a> <a id="2061" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#987" class="Bound">f</a><a id="2062" class="Symbol">)</a> <a id="2064" href="synthetic-homotopy-theory.functoriality-loop-spaces.html#1840" class="Bound">x</a><a id="2065" class="Symbol">))</a>
</pre>