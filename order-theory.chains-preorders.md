# Chains in preorders

<pre class="Agda"><a id="32" class="Symbol">{-#</a> <a id="36" class="Keyword">OPTIONS</a> <a id="44" class="Pragma">--without-K</a> <a id="56" class="Pragma">--exact-split</a> <a id="70" class="Symbol">#-}</a>

<a id="75" class="Keyword">module</a> <a id="82" href="order-theory.chains-preorders.html" class="Module">order-theory.chains-preorders</a> <a id="112" class="Keyword">where</a>

<a id="119" class="Keyword">open</a> <a id="124" class="Keyword">import</a> <a id="131" href="foundation.dependent-pair-types.html" class="Module">foundation.dependent-pair-types</a> <a id="163" class="Keyword">using</a> <a id="169" class="Symbol">(</a><a id="170" href="foundation-core.dependent-pair-types.html#502" class="Record">Σ</a><a id="171" class="Symbol">;</a> <a id="173" href="foundation-core.dependent-pair-types.html#575" class="InductiveConstructor">pair</a><a id="177" class="Symbol">;</a> <a id="179" href="foundation-core.dependent-pair-types.html#592" class="Field">pr1</a><a id="182" class="Symbol">;</a> <a id="184" href="foundation-core.dependent-pair-types.html#604" class="Field">pr2</a><a id="187" class="Symbol">)</a>
<a id="189" class="Keyword">open</a> <a id="194" class="Keyword">import</a> <a id="201" href="foundation.propositions.html" class="Module">foundation.propositions</a> <a id="225" class="Keyword">using</a>
  <a id="233" class="Symbol">(</a> <a id="235" href="foundation-core.propositions.html#1380" class="Function">UU-Prop</a><a id="242" class="Symbol">;</a> <a id="244" href="foundation-core.propositions.html#1482" class="Function">type-Prop</a><a id="253" class="Symbol">;</a> <a id="255" href="foundation-core.propositions.html#1295" class="Function">is-prop</a><a id="262" class="Symbol">;</a> <a id="264" href="foundation-core.propositions.html#1549" class="Function">is-prop-type-Prop</a><a id="281" class="Symbol">)</a>
<a id="283" class="Keyword">open</a> <a id="288" class="Keyword">import</a> <a id="295" href="foundation.subtypes.html" class="Module">foundation.subtypes</a> <a id="315" class="Keyword">using</a> <a id="321" class="Symbol">(</a><a id="322" href="foundation-core.subtypes.html#2541" class="Function">type-subtype</a><a id="334" class="Symbol">)</a>
<a id="336" class="Keyword">open</a> <a id="341" class="Keyword">import</a> <a id="348" href="foundation.universe-levels.html" class="Module">foundation.universe-levels</a> <a id="375" class="Keyword">using</a> <a id="381" class="Symbol">(</a><a id="382" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="387" class="Symbol">;</a> <a id="389" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a><a id="391" class="Symbol">;</a> <a id="393" href="Agda.Primitive.html#810" class="Primitive Operator">_⊔_</a><a id="396" class="Symbol">;</a> <a id="398" href="Agda.Primitive.html#780" class="Primitive">lsuc</a><a id="402" class="Symbol">)</a>

<a id="405" class="Keyword">open</a> <a id="410" class="Keyword">import</a> <a id="417" href="order-theory.preorders.html" class="Module">order-theory.preorders</a> <a id="440" class="Keyword">using</a> <a id="446" class="Symbol">(</a><a id="447" href="order-theory.preorders.html#531" class="Function">Preorder</a><a id="455" class="Symbol">;</a> <a id="457" href="order-theory.preorders.html#873" class="Function">element-Preorder</a><a id="473" class="Symbol">)</a>
<a id="475" class="Keyword">open</a> <a id="480" class="Keyword">import</a> <a id="487" href="order-theory.subpreorders.html" class="Module">order-theory.subpreorders</a> <a id="513" class="Keyword">using</a>
  <a id="521" class="Symbol">(</a> <a id="523" href="order-theory.subpreorders.html#1826" class="Function">sub-Preorder</a><a id="535" class="Symbol">;</a> <a id="537" href="order-theory.subpreorders.html#2302" class="Function">inclusion-sub-preorder-Prop</a><a id="564" class="Symbol">)</a>
<a id="566" class="Keyword">open</a> <a id="571" class="Keyword">import</a> <a id="578" href="order-theory.total-preorders.html" class="Module">order-theory.total-preorders</a> <a id="607" class="Keyword">using</a> <a id="613" class="Symbol">(</a><a id="614" href="order-theory.total-preorders.html#976" class="Function">is-total-preorder-Prop</a><a id="636" class="Symbol">)</a>
</pre>
## Definition

<pre class="Agda"><a id="666" class="Keyword">module</a> <a id="673" href="order-theory.chains-preorders.html#673" class="Module">_</a>
  <a id="677" class="Symbol">{</a><a id="678" href="order-theory.chains-preorders.html#678" class="Bound">l1</a> <a id="681" href="order-theory.chains-preorders.html#681" class="Bound">l2</a> <a id="684" class="Symbol">:</a> <a id="686" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="691" class="Symbol">}</a> <a id="693" class="Symbol">(</a><a id="694" href="order-theory.chains-preorders.html#694" class="Bound">X</a> <a id="696" class="Symbol">:</a> <a id="698" href="order-theory.preorders.html#531" class="Function">Preorder</a> <a id="707" href="order-theory.chains-preorders.html#678" class="Bound">l1</a> <a id="710" href="order-theory.chains-preorders.html#681" class="Bound">l2</a><a id="712" class="Symbol">)</a>
  <a id="716" class="Keyword">where</a>

  <a id="725" href="order-theory.chains-preorders.html#725" class="Function">is-chain-sub-preorder-Prop</a> <a id="752" class="Symbol">:</a>
    <a id="758" class="Symbol">{</a><a id="759" href="order-theory.chains-preorders.html#759" class="Bound">l3</a> <a id="762" class="Symbol">:</a> <a id="764" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="769" class="Symbol">}</a> <a id="771" class="Symbol">(</a><a id="772" href="order-theory.chains-preorders.html#772" class="Bound">S</a> <a id="774" class="Symbol">:</a> <a id="776" href="order-theory.preorders.html#873" class="Function">element-Preorder</a> <a id="793" href="order-theory.chains-preorders.html#694" class="Bound">X</a> <a id="795" class="Symbol">→</a> <a id="797" href="foundation-core.propositions.html#1380" class="Function">UU-Prop</a> <a id="805" href="order-theory.chains-preorders.html#759" class="Bound">l3</a><a id="807" class="Symbol">)</a> <a id="809" class="Symbol">→</a> <a id="811" href="foundation-core.propositions.html#1380" class="Function">UU-Prop</a> <a id="819" class="Symbol">(</a><a id="820" href="order-theory.chains-preorders.html#678" class="Bound">l1</a> <a id="823" href="Agda.Primitive.html#810" class="Primitive Operator">⊔</a> <a id="825" href="order-theory.chains-preorders.html#681" class="Bound">l2</a> <a id="828" href="Agda.Primitive.html#810" class="Primitive Operator">⊔</a> <a id="830" href="order-theory.chains-preorders.html#759" class="Bound">l3</a><a id="832" class="Symbol">)</a>
  <a id="836" href="order-theory.chains-preorders.html#725" class="Function">is-chain-sub-preorder-Prop</a> <a id="863" href="order-theory.chains-preorders.html#863" class="Bound">S</a> <a id="865" class="Symbol">=</a> <a id="867" href="order-theory.total-preorders.html#976" class="Function">is-total-preorder-Prop</a> <a id="890" class="Symbol">(</a><a id="891" href="order-theory.subpreorders.html#1826" class="Function">sub-Preorder</a> <a id="904" href="order-theory.chains-preorders.html#694" class="Bound">X</a> <a id="906" href="order-theory.chains-preorders.html#863" class="Bound">S</a><a id="907" class="Symbol">)</a>

  <a id="912" href="order-theory.chains-preorders.html#912" class="Function">is-chain-sub-Preorder</a> <a id="934" class="Symbol">:</a>
    <a id="940" class="Symbol">{</a><a id="941" href="order-theory.chains-preorders.html#941" class="Bound">l3</a> <a id="944" class="Symbol">:</a> <a id="946" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="951" class="Symbol">}</a> <a id="953" class="Symbol">(</a><a id="954" href="order-theory.chains-preorders.html#954" class="Bound">S</a> <a id="956" class="Symbol">:</a> <a id="958" href="order-theory.preorders.html#873" class="Function">element-Preorder</a> <a id="975" href="order-theory.chains-preorders.html#694" class="Bound">X</a> <a id="977" class="Symbol">→</a> <a id="979" href="foundation-core.propositions.html#1380" class="Function">UU-Prop</a> <a id="987" href="order-theory.chains-preorders.html#941" class="Bound">l3</a><a id="989" class="Symbol">)</a> <a id="991" class="Symbol">→</a> <a id="993" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="996" class="Symbol">(</a><a id="997" href="order-theory.chains-preorders.html#678" class="Bound">l1</a> <a id="1000" href="Agda.Primitive.html#810" class="Primitive Operator">⊔</a> <a id="1002" href="order-theory.chains-preorders.html#681" class="Bound">l2</a> <a id="1005" href="Agda.Primitive.html#810" class="Primitive Operator">⊔</a> <a id="1007" href="order-theory.chains-preorders.html#941" class="Bound">l3</a><a id="1009" class="Symbol">)</a>
  <a id="1013" href="order-theory.chains-preorders.html#912" class="Function">is-chain-sub-Preorder</a> <a id="1035" href="order-theory.chains-preorders.html#1035" class="Bound">S</a> <a id="1037" class="Symbol">=</a> <a id="1039" href="foundation-core.propositions.html#1482" class="Function">type-Prop</a> <a id="1049" class="Symbol">(</a><a id="1050" href="order-theory.chains-preorders.html#725" class="Function">is-chain-sub-preorder-Prop</a> <a id="1077" href="order-theory.chains-preorders.html#1035" class="Bound">S</a><a id="1078" class="Symbol">)</a>

  <a id="1083" href="order-theory.chains-preorders.html#1083" class="Function">is-prop-is-chain-sub-Preorder</a> <a id="1113" class="Symbol">:</a>
    <a id="1119" class="Symbol">{</a><a id="1120" href="order-theory.chains-preorders.html#1120" class="Bound">l3</a> <a id="1123" class="Symbol">:</a> <a id="1125" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="1130" class="Symbol">}</a> <a id="1132" class="Symbol">(</a><a id="1133" href="order-theory.chains-preorders.html#1133" class="Bound">S</a> <a id="1135" class="Symbol">:</a> <a id="1137" href="order-theory.preorders.html#873" class="Function">element-Preorder</a> <a id="1154" href="order-theory.chains-preorders.html#694" class="Bound">X</a> <a id="1156" class="Symbol">→</a> <a id="1158" href="foundation-core.propositions.html#1380" class="Function">UU-Prop</a> <a id="1166" href="order-theory.chains-preorders.html#1120" class="Bound">l3</a><a id="1168" class="Symbol">)</a> <a id="1170" class="Symbol">→</a>
    <a id="1176" href="foundation-core.propositions.html#1295" class="Function">is-prop</a> <a id="1184" class="Symbol">(</a><a id="1185" href="order-theory.chains-preorders.html#912" class="Function">is-chain-sub-Preorder</a> <a id="1207" href="order-theory.chains-preorders.html#1133" class="Bound">S</a><a id="1208" class="Symbol">)</a>
  <a id="1212" href="order-theory.chains-preorders.html#1083" class="Function">is-prop-is-chain-sub-Preorder</a> <a id="1242" href="order-theory.chains-preorders.html#1242" class="Bound">S</a> <a id="1244" class="Symbol">=</a>
    <a id="1250" href="foundation-core.propositions.html#1549" class="Function">is-prop-type-Prop</a> <a id="1268" class="Symbol">(</a><a id="1269" href="order-theory.chains-preorders.html#725" class="Function">is-chain-sub-preorder-Prop</a> <a id="1296" href="order-theory.chains-preorders.html#1242" class="Bound">S</a><a id="1297" class="Symbol">)</a>

<a id="chain-Preorder"></a><a id="1300" href="order-theory.chains-preorders.html#1300" class="Function">chain-Preorder</a> <a id="1315" class="Symbol">:</a>
  <a id="1319" class="Symbol">{</a><a id="1320" href="order-theory.chains-preorders.html#1320" class="Bound">l1</a> <a id="1323" href="order-theory.chains-preorders.html#1323" class="Bound">l2</a> <a id="1326" class="Symbol">:</a> <a id="1328" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="1333" class="Symbol">}</a> <a id="1335" class="Symbol">(</a><a id="1336" href="order-theory.chains-preorders.html#1336" class="Bound">l</a> <a id="1338" class="Symbol">:</a> <a id="1340" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="1345" class="Symbol">)</a> <a id="1347" class="Symbol">(</a><a id="1348" href="order-theory.chains-preorders.html#1348" class="Bound">X</a> <a id="1350" class="Symbol">:</a> <a id="1352" href="order-theory.preorders.html#531" class="Function">Preorder</a> <a id="1361" href="order-theory.chains-preorders.html#1320" class="Bound">l1</a> <a id="1364" href="order-theory.chains-preorders.html#1323" class="Bound">l2</a><a id="1366" class="Symbol">)</a> <a id="1368" class="Symbol">→</a> <a id="1370" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="1373" class="Symbol">(</a><a id="1374" href="order-theory.chains-preorders.html#1320" class="Bound">l1</a> <a id="1377" href="Agda.Primitive.html#810" class="Primitive Operator">⊔</a> <a id="1379" href="order-theory.chains-preorders.html#1323" class="Bound">l2</a> <a id="1382" href="Agda.Primitive.html#810" class="Primitive Operator">⊔</a> <a id="1384" href="Agda.Primitive.html#780" class="Primitive">lsuc</a> <a id="1389" href="order-theory.chains-preorders.html#1336" class="Bound">l</a><a id="1390" class="Symbol">)</a>
<a id="1392" href="order-theory.chains-preorders.html#1300" class="Function">chain-Preorder</a> <a id="1407" href="order-theory.chains-preorders.html#1407" class="Bound">l</a> <a id="1409" href="order-theory.chains-preorders.html#1409" class="Bound">X</a> <a id="1411" class="Symbol">=</a>
  <a id="1415" href="foundation-core.dependent-pair-types.html#502" class="Record">Σ</a> <a id="1417" class="Symbol">(</a><a id="1418" href="order-theory.preorders.html#873" class="Function">element-Preorder</a> <a id="1435" href="order-theory.chains-preorders.html#1409" class="Bound">X</a> <a id="1437" class="Symbol">→</a> <a id="1439" href="foundation-core.propositions.html#1380" class="Function">UU-Prop</a> <a id="1447" href="order-theory.chains-preorders.html#1407" class="Bound">l</a><a id="1448" class="Symbol">)</a> <a id="1450" class="Symbol">(</a><a id="1451" href="order-theory.chains-preorders.html#912" class="Function">is-chain-sub-Preorder</a> <a id="1473" href="order-theory.chains-preorders.html#1409" class="Bound">X</a><a id="1474" class="Symbol">)</a>

<a id="1477" class="Keyword">module</a> <a id="1484" href="order-theory.chains-preorders.html#1484" class="Module">_</a>
  <a id="1488" class="Symbol">{</a><a id="1489" href="order-theory.chains-preorders.html#1489" class="Bound">l1</a> <a id="1492" href="order-theory.chains-preorders.html#1492" class="Bound">l2</a> <a id="1495" href="order-theory.chains-preorders.html#1495" class="Bound">l3</a> <a id="1498" class="Symbol">:</a> <a id="1500" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="1505" class="Symbol">}</a> <a id="1507" class="Symbol">(</a><a id="1508" href="order-theory.chains-preorders.html#1508" class="Bound">X</a> <a id="1510" class="Symbol">:</a> <a id="1512" href="order-theory.preorders.html#531" class="Function">Preorder</a> <a id="1521" href="order-theory.chains-preorders.html#1489" class="Bound">l1</a> <a id="1524" href="order-theory.chains-preorders.html#1492" class="Bound">l2</a><a id="1526" class="Symbol">)</a> <a id="1528" class="Symbol">(</a><a id="1529" href="order-theory.chains-preorders.html#1529" class="Bound">C</a> <a id="1531" class="Symbol">:</a> <a id="1533" href="order-theory.chains-preorders.html#1300" class="Function">chain-Preorder</a> <a id="1548" href="order-theory.chains-preorders.html#1495" class="Bound">l3</a> <a id="1551" href="order-theory.chains-preorders.html#1508" class="Bound">X</a><a id="1552" class="Symbol">)</a>
  <a id="1556" class="Keyword">where</a>

  <a id="1565" href="order-theory.chains-preorders.html#1565" class="Function">sub-preorder-chain-Preorder</a> <a id="1593" class="Symbol">:</a> <a id="1595" href="order-theory.preorders.html#873" class="Function">element-Preorder</a> <a id="1612" href="order-theory.chains-preorders.html#1508" class="Bound">X</a> <a id="1614" class="Symbol">→</a> <a id="1616" href="foundation-core.propositions.html#1380" class="Function">UU-Prop</a> <a id="1624" href="order-theory.chains-preorders.html#1495" class="Bound">l3</a>
  <a id="1629" href="order-theory.chains-preorders.html#1565" class="Function">sub-preorder-chain-Preorder</a> <a id="1657" class="Symbol">=</a> <a id="1659" href="foundation-core.dependent-pair-types.html#592" class="Field">pr1</a> <a id="1663" href="order-theory.chains-preorders.html#1529" class="Bound">C</a>

  <a id="1668" href="order-theory.chains-preorders.html#1668" class="Function">element-chain-Preorder</a> <a id="1691" class="Symbol">:</a> <a id="1693" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="1696" class="Symbol">(</a><a id="1697" href="order-theory.chains-preorders.html#1489" class="Bound">l1</a> <a id="1700" href="Agda.Primitive.html#810" class="Primitive Operator">⊔</a> <a id="1702" href="order-theory.chains-preorders.html#1495" class="Bound">l3</a><a id="1704" class="Symbol">)</a>
  <a id="1708" href="order-theory.chains-preorders.html#1668" class="Function">element-chain-Preorder</a> <a id="1731" class="Symbol">=</a> <a id="1733" href="foundation-core.subtypes.html#2541" class="Function">type-subtype</a> <a id="1746" href="order-theory.chains-preorders.html#1565" class="Function">sub-preorder-chain-Preorder</a>

<a id="1775" class="Keyword">module</a> <a id="1782" href="order-theory.chains-preorders.html#1782" class="Module">_</a>
  <a id="1786" class="Symbol">{</a><a id="1787" href="order-theory.chains-preorders.html#1787" class="Bound">l1</a> <a id="1790" href="order-theory.chains-preorders.html#1790" class="Bound">l2</a> <a id="1793" class="Symbol">:</a> <a id="1795" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="1800" class="Symbol">}</a> <a id="1802" class="Symbol">(</a><a id="1803" href="order-theory.chains-preorders.html#1803" class="Bound">X</a> <a id="1805" class="Symbol">:</a> <a id="1807" href="order-theory.preorders.html#531" class="Function">Preorder</a> <a id="1816" href="order-theory.chains-preorders.html#1787" class="Bound">l1</a> <a id="1819" href="order-theory.chains-preorders.html#1790" class="Bound">l2</a><a id="1821" class="Symbol">)</a>
  <a id="1825" class="Keyword">where</a>
  
  <a id="1836" href="order-theory.chains-preorders.html#1836" class="Function">inclusion-chain-preorder-Prop</a> <a id="1866" class="Symbol">:</a>
    <a id="1872" class="Symbol">{</a><a id="1873" href="order-theory.chains-preorders.html#1873" class="Bound">l3</a> <a id="1876" href="order-theory.chains-preorders.html#1876" class="Bound">l4</a> <a id="1879" class="Symbol">:</a> <a id="1881" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="1886" class="Symbol">}</a> <a id="1888" class="Symbol">→</a> <a id="1890" href="order-theory.chains-preorders.html#1300" class="Function">chain-Preorder</a> <a id="1905" href="order-theory.chains-preorders.html#1873" class="Bound">l3</a> <a id="1908" href="order-theory.chains-preorders.html#1803" class="Bound">X</a> <a id="1910" class="Symbol">→</a> <a id="1912" href="order-theory.chains-preorders.html#1300" class="Function">chain-Preorder</a> <a id="1927" href="order-theory.chains-preorders.html#1876" class="Bound">l4</a> <a id="1930" href="order-theory.chains-preorders.html#1803" class="Bound">X</a> <a id="1932" class="Symbol">→</a>
    <a id="1938" href="foundation-core.propositions.html#1380" class="Function">UU-Prop</a> <a id="1946" class="Symbol">(</a><a id="1947" href="order-theory.chains-preorders.html#1787" class="Bound">l1</a> <a id="1950" href="Agda.Primitive.html#810" class="Primitive Operator">⊔</a> <a id="1952" href="order-theory.chains-preorders.html#1873" class="Bound">l3</a> <a id="1955" href="Agda.Primitive.html#810" class="Primitive Operator">⊔</a> <a id="1957" href="order-theory.chains-preorders.html#1876" class="Bound">l4</a><a id="1959" class="Symbol">)</a>
  <a id="1963" href="order-theory.chains-preorders.html#1836" class="Function">inclusion-chain-preorder-Prop</a> <a id="1993" href="order-theory.chains-preorders.html#1993" class="Bound">C</a> <a id="1995" href="order-theory.chains-preorders.html#1995" class="Bound">D</a> <a id="1997" class="Symbol">=</a>
    <a id="2003" href="order-theory.subpreorders.html#2302" class="Function">inclusion-sub-preorder-Prop</a> <a id="2031" href="order-theory.chains-preorders.html#1803" class="Bound">X</a>
      <a id="2039" class="Symbol">(</a> <a id="2041" href="order-theory.chains-preorders.html#1565" class="Function">sub-preorder-chain-Preorder</a> <a id="2069" href="order-theory.chains-preorders.html#1803" class="Bound">X</a> <a id="2071" href="order-theory.chains-preorders.html#1993" class="Bound">C</a><a id="2072" class="Symbol">)</a>
      <a id="2080" class="Symbol">(</a> <a id="2082" href="order-theory.chains-preorders.html#1565" class="Function">sub-preorder-chain-Preorder</a> <a id="2110" href="order-theory.chains-preorders.html#1803" class="Bound">X</a> <a id="2112" href="order-theory.chains-preorders.html#1995" class="Bound">D</a><a id="2113" class="Symbol">)</a>

  <a id="2118" href="order-theory.chains-preorders.html#2118" class="Function">inclusion-chain-Preorder</a> <a id="2143" class="Symbol">:</a>
    <a id="2149" class="Symbol">{</a><a id="2150" href="order-theory.chains-preorders.html#2150" class="Bound">l3</a> <a id="2153" href="order-theory.chains-preorders.html#2153" class="Bound">l4</a> <a id="2156" class="Symbol">:</a> <a id="2158" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="2163" class="Symbol">}</a> <a id="2165" class="Symbol">→</a> <a id="2167" href="order-theory.chains-preorders.html#1300" class="Function">chain-Preorder</a> <a id="2182" href="order-theory.chains-preorders.html#2150" class="Bound">l3</a> <a id="2185" href="order-theory.chains-preorders.html#1803" class="Bound">X</a> <a id="2187" class="Symbol">→</a> <a id="2189" href="order-theory.chains-preorders.html#1300" class="Function">chain-Preorder</a> <a id="2204" href="order-theory.chains-preorders.html#2153" class="Bound">l4</a> <a id="2207" href="order-theory.chains-preorders.html#1803" class="Bound">X</a> <a id="2209" class="Symbol">→</a>
    <a id="2215" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="2218" class="Symbol">(</a><a id="2219" href="order-theory.chains-preorders.html#1787" class="Bound">l1</a> <a id="2222" href="Agda.Primitive.html#810" class="Primitive Operator">⊔</a> <a id="2224" href="order-theory.chains-preorders.html#2150" class="Bound">l3</a> <a id="2227" href="Agda.Primitive.html#810" class="Primitive Operator">⊔</a> <a id="2229" href="order-theory.chains-preorders.html#2153" class="Bound">l4</a><a id="2231" class="Symbol">)</a>
  <a id="2235" href="order-theory.chains-preorders.html#2118" class="Function">inclusion-chain-Preorder</a> <a id="2260" href="order-theory.chains-preorders.html#2260" class="Bound">C</a> <a id="2262" href="order-theory.chains-preorders.html#2262" class="Bound">D</a> <a id="2264" class="Symbol">=</a> <a id="2266" href="foundation-core.propositions.html#1482" class="Function">type-Prop</a> <a id="2276" class="Symbol">(</a><a id="2277" href="order-theory.chains-preorders.html#1836" class="Function">inclusion-chain-preorder-Prop</a> <a id="2307" href="order-theory.chains-preorders.html#2260" class="Bound">C</a> <a id="2309" href="order-theory.chains-preorders.html#2262" class="Bound">D</a><a id="2310" class="Symbol">)</a>

  <a id="2315" href="order-theory.chains-preorders.html#2315" class="Function">is-prop-inclusion-chain-Preorder</a> <a id="2348" class="Symbol">:</a>
    <a id="2354" class="Symbol">{</a><a id="2355" href="order-theory.chains-preorders.html#2355" class="Bound">l3</a> <a id="2358" href="order-theory.chains-preorders.html#2358" class="Bound">l4</a> <a id="2361" class="Symbol">:</a> <a id="2363" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="2368" class="Symbol">}</a> <a id="2370" class="Symbol">(</a><a id="2371" href="order-theory.chains-preorders.html#2371" class="Bound">C</a> <a id="2373" class="Symbol">:</a> <a id="2375" href="order-theory.chains-preorders.html#1300" class="Function">chain-Preorder</a> <a id="2390" href="order-theory.chains-preorders.html#2355" class="Bound">l3</a> <a id="2393" href="order-theory.chains-preorders.html#1803" class="Bound">X</a><a id="2394" class="Symbol">)</a> <a id="2396" class="Symbol">(</a><a id="2397" href="order-theory.chains-preorders.html#2397" class="Bound">D</a> <a id="2399" class="Symbol">:</a> <a id="2401" href="order-theory.chains-preorders.html#1300" class="Function">chain-Preorder</a> <a id="2416" href="order-theory.chains-preorders.html#2358" class="Bound">l4</a> <a id="2419" href="order-theory.chains-preorders.html#1803" class="Bound">X</a><a id="2420" class="Symbol">)</a> <a id="2422" class="Symbol">→</a>
    <a id="2428" href="foundation-core.propositions.html#1295" class="Function">is-prop</a> <a id="2436" class="Symbol">(</a><a id="2437" href="order-theory.chains-preorders.html#2118" class="Function">inclusion-chain-Preorder</a> <a id="2462" href="order-theory.chains-preorders.html#2371" class="Bound">C</a> <a id="2464" href="order-theory.chains-preorders.html#2397" class="Bound">D</a><a id="2465" class="Symbol">)</a>
  <a id="2469" href="order-theory.chains-preorders.html#2315" class="Function">is-prop-inclusion-chain-Preorder</a> <a id="2502" href="order-theory.chains-preorders.html#2502" class="Bound">C</a> <a id="2504" href="order-theory.chains-preorders.html#2504" class="Bound">D</a> <a id="2506" class="Symbol">=</a>
    <a id="2512" href="foundation-core.propositions.html#1549" class="Function">is-prop-type-Prop</a> <a id="2530" class="Symbol">(</a><a id="2531" href="order-theory.chains-preorders.html#1836" class="Function">inclusion-chain-preorder-Prop</a> <a id="2561" href="order-theory.chains-preorders.html#2502" class="Bound">C</a> <a id="2563" href="order-theory.chains-preorders.html#2504" class="Bound">D</a><a id="2564" class="Symbol">)</a>
</pre>