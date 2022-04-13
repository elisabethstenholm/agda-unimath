# Total preorders

<pre class="Agda"><a id="28" class="Symbol">{-#</a> <a id="32" class="Keyword">OPTIONS</a> <a id="40" class="Pragma">--without-K</a> <a id="52" class="Pragma">--exact-split</a> <a id="66" class="Symbol">#-}</a>

<a id="71" class="Keyword">module</a> <a id="78" href="order-theory.total-preorders.html" class="Module">order-theory.total-preorders</a> <a id="107" class="Keyword">where</a>

<a id="114" class="Keyword">open</a> <a id="119" class="Keyword">import</a> <a id="126" href="foundation.disjunction.html" class="Module">foundation.disjunction</a> <a id="149" class="Keyword">using</a> <a id="155" class="Symbol">(</a><a id="156" href="foundation.disjunction.html#1135" class="Function">disj-Prop</a><a id="165" class="Symbol">)</a>
<a id="167" class="Keyword">open</a> <a id="172" class="Keyword">import</a> <a id="179" href="foundation.propositions.html" class="Module">foundation.propositions</a> <a id="203" class="Keyword">using</a>
  <a id="211" class="Symbol">(</a> <a id="213" href="foundation-core.propositions.html#1322" class="Function">UU-Prop</a><a id="220" class="Symbol">;</a> <a id="222" href="foundation-core.propositions.html#1424" class="Function">type-Prop</a><a id="231" class="Symbol">;</a> <a id="233" href="foundation-core.propositions.html#1491" class="Function">is-prop-type-Prop</a><a id="250" class="Symbol">;</a> <a id="252" href="foundation-core.propositions.html#1246" class="Function">is-prop</a><a id="259" class="Symbol">;</a> <a id="261" href="foundation.propositions.html#1941" class="Function">Π-Prop</a><a id="267" class="Symbol">)</a>
<a id="269" class="Keyword">open</a> <a id="274" class="Keyword">import</a> <a id="281" href="foundation.universe-levels.html" class="Module">foundation.universe-levels</a> <a id="308" class="Keyword">using</a> <a id="314" class="Symbol">(</a><a id="315" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="320" class="Symbol">;</a> <a id="322" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a><a id="324" class="Symbol">;</a> <a id="326" href="Agda.Primitive.html#810" class="Primitive Operator">_⊔_</a><a id="329" class="Symbol">)</a>

<a id="332" class="Keyword">open</a> <a id="337" class="Keyword">import</a> <a id="344" href="order-theory.preorders.html" class="Module">order-theory.preorders</a> <a id="367" class="Keyword">using</a>
  <a id="375" class="Symbol">(</a> <a id="377" href="order-theory.preorders.html#531" class="Function">Preorder</a><a id="385" class="Symbol">;</a> <a id="387" href="order-theory.preorders.html#873" class="Function">element-Preorder</a><a id="403" class="Symbol">;</a> <a id="405" href="order-theory.preorders.html#928" class="Function">leq-preorder-Prop</a><a id="422" class="Symbol">)</a>
</pre>
## Definition

<pre class="Agda"><a id="452" class="Keyword">module</a> <a id="459" href="order-theory.total-preorders.html#459" class="Module">_</a>
  <a id="463" class="Symbol">{</a><a id="464" href="order-theory.total-preorders.html#464" class="Bound">l1</a> <a id="467" href="order-theory.total-preorders.html#467" class="Bound">l2</a> <a id="470" class="Symbol">:</a> <a id="472" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="477" class="Symbol">}</a> <a id="479" class="Symbol">(</a><a id="480" href="order-theory.total-preorders.html#480" class="Bound">X</a> <a id="482" class="Symbol">:</a> <a id="484" href="order-theory.preorders.html#531" class="Function">Preorder</a> <a id="493" href="order-theory.total-preorders.html#464" class="Bound">l1</a> <a id="496" href="order-theory.total-preorders.html#467" class="Bound">l2</a><a id="498" class="Symbol">)</a>
  <a id="502" class="Keyword">where</a>

  <a id="511" href="order-theory.total-preorders.html#511" class="Function">incident-preorder-Prop</a> <a id="534" class="Symbol">:</a> <a id="536" class="Symbol">(</a><a id="537" href="order-theory.total-preorders.html#537" class="Bound">x</a> <a id="539" href="order-theory.total-preorders.html#539" class="Bound">y</a> <a id="541" class="Symbol">:</a> <a id="543" href="order-theory.preorders.html#873" class="Function">element-Preorder</a> <a id="560" href="order-theory.total-preorders.html#480" class="Bound">X</a><a id="561" class="Symbol">)</a> <a id="563" class="Symbol">→</a> <a id="565" href="foundation-core.propositions.html#1322" class="Function">UU-Prop</a> <a id="573" href="order-theory.total-preorders.html#467" class="Bound">l2</a>
  <a id="578" href="order-theory.total-preorders.html#511" class="Function">incident-preorder-Prop</a> <a id="601" href="order-theory.total-preorders.html#601" class="Bound">x</a> <a id="603" href="order-theory.total-preorders.html#603" class="Bound">y</a> <a id="605" class="Symbol">=</a>
    <a id="611" href="foundation.disjunction.html#1135" class="Function">disj-Prop</a> <a id="621" class="Symbol">(</a><a id="622" href="order-theory.preorders.html#928" class="Function">leq-preorder-Prop</a> <a id="640" href="order-theory.total-preorders.html#480" class="Bound">X</a> <a id="642" href="order-theory.total-preorders.html#601" class="Bound">x</a> <a id="644" href="order-theory.total-preorders.html#603" class="Bound">y</a><a id="645" class="Symbol">)</a> <a id="647" class="Symbol">(</a><a id="648" href="order-theory.preorders.html#928" class="Function">leq-preorder-Prop</a> <a id="666" href="order-theory.total-preorders.html#480" class="Bound">X</a> <a id="668" href="order-theory.total-preorders.html#603" class="Bound">y</a> <a id="670" href="order-theory.total-preorders.html#601" class="Bound">x</a><a id="671" class="Symbol">)</a>

  <a id="676" href="order-theory.total-preorders.html#676" class="Function">incident-Preorder</a> <a id="694" class="Symbol">:</a> <a id="696" class="Symbol">(</a><a id="697" href="order-theory.total-preorders.html#697" class="Bound">x</a> <a id="699" href="order-theory.total-preorders.html#699" class="Bound">y</a> <a id="701" class="Symbol">:</a> <a id="703" href="order-theory.preorders.html#873" class="Function">element-Preorder</a> <a id="720" href="order-theory.total-preorders.html#480" class="Bound">X</a><a id="721" class="Symbol">)</a> <a id="723" class="Symbol">→</a> <a id="725" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="728" href="order-theory.total-preorders.html#467" class="Bound">l2</a>
  <a id="733" href="order-theory.total-preorders.html#676" class="Function">incident-Preorder</a> <a id="751" href="order-theory.total-preorders.html#751" class="Bound">x</a> <a id="753" href="order-theory.total-preorders.html#753" class="Bound">y</a> <a id="755" class="Symbol">=</a> <a id="757" href="foundation-core.propositions.html#1424" class="Function">type-Prop</a> <a id="767" class="Symbol">(</a><a id="768" href="order-theory.total-preorders.html#511" class="Function">incident-preorder-Prop</a> <a id="791" href="order-theory.total-preorders.html#751" class="Bound">x</a> <a id="793" href="order-theory.total-preorders.html#753" class="Bound">y</a><a id="794" class="Symbol">)</a>

  <a id="799" href="order-theory.total-preorders.html#799" class="Function">is-prop-incident-Preorder</a> <a id="825" class="Symbol">:</a>
    <a id="831" class="Symbol">(</a><a id="832" href="order-theory.total-preorders.html#832" class="Bound">x</a> <a id="834" href="order-theory.total-preorders.html#834" class="Bound">y</a> <a id="836" class="Symbol">:</a> <a id="838" href="order-theory.preorders.html#873" class="Function">element-Preorder</a> <a id="855" href="order-theory.total-preorders.html#480" class="Bound">X</a><a id="856" class="Symbol">)</a> <a id="858" class="Symbol">→</a> <a id="860" href="foundation-core.propositions.html#1246" class="Function">is-prop</a> <a id="868" class="Symbol">(</a><a id="869" href="order-theory.total-preorders.html#676" class="Function">incident-Preorder</a> <a id="887" href="order-theory.total-preorders.html#832" class="Bound">x</a> <a id="889" href="order-theory.total-preorders.html#834" class="Bound">y</a><a id="890" class="Symbol">)</a>
  <a id="894" href="order-theory.total-preorders.html#799" class="Function">is-prop-incident-Preorder</a> <a id="920" href="order-theory.total-preorders.html#920" class="Bound">x</a> <a id="922" href="order-theory.total-preorders.html#922" class="Bound">y</a> <a id="924" class="Symbol">=</a> <a id="926" href="foundation-core.propositions.html#1491" class="Function">is-prop-type-Prop</a> <a id="944" class="Symbol">(</a><a id="945" href="order-theory.total-preorders.html#511" class="Function">incident-preorder-Prop</a> <a id="968" href="order-theory.total-preorders.html#920" class="Bound">x</a> <a id="970" href="order-theory.total-preorders.html#922" class="Bound">y</a><a id="971" class="Symbol">)</a>

  <a id="976" href="order-theory.total-preorders.html#976" class="Function">is-total-preorder-Prop</a> <a id="999" class="Symbol">:</a> <a id="1001" href="foundation-core.propositions.html#1322" class="Function">UU-Prop</a> <a id="1009" class="Symbol">(</a><a id="1010" href="order-theory.total-preorders.html#464" class="Bound">l1</a> <a id="1013" href="Agda.Primitive.html#810" class="Primitive Operator">⊔</a> <a id="1015" href="order-theory.total-preorders.html#467" class="Bound">l2</a><a id="1017" class="Symbol">)</a>
  <a id="1021" href="order-theory.total-preorders.html#976" class="Function">is-total-preorder-Prop</a> <a id="1044" class="Symbol">=</a>
    <a id="1050" href="foundation.propositions.html#1941" class="Function">Π-Prop</a>
      <a id="1063" class="Symbol">(</a> <a id="1065" href="order-theory.preorders.html#873" class="Function">element-Preorder</a> <a id="1082" href="order-theory.total-preorders.html#480" class="Bound">X</a><a id="1083" class="Symbol">)</a>
      <a id="1091" class="Symbol">(</a> <a id="1093" class="Symbol">λ</a> <a id="1095" href="order-theory.total-preorders.html#1095" class="Bound">x</a> <a id="1097" class="Symbol">→</a> <a id="1099" href="foundation.propositions.html#1941" class="Function">Π-Prop</a> <a id="1106" class="Symbol">(</a> <a id="1108" href="order-theory.preorders.html#873" class="Function">element-Preorder</a> <a id="1125" href="order-theory.total-preorders.html#480" class="Bound">X</a><a id="1126" class="Symbol">)</a> <a id="1128" class="Symbol">(λ</a> <a id="1131" href="order-theory.total-preorders.html#1131" class="Bound">y</a> <a id="1133" class="Symbol">→</a> <a id="1135" href="order-theory.total-preorders.html#511" class="Function">incident-preorder-Prop</a> <a id="1158" href="order-theory.total-preorders.html#1095" class="Bound">x</a> <a id="1160" href="order-theory.total-preorders.html#1131" class="Bound">y</a><a id="1161" class="Symbol">))</a>

  <a id="1167" href="order-theory.total-preorders.html#1167" class="Function">is-total-Preorder</a> <a id="1185" class="Symbol">:</a> <a id="1187" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="1190" class="Symbol">(</a><a id="1191" href="order-theory.total-preorders.html#464" class="Bound">l1</a> <a id="1194" href="Agda.Primitive.html#810" class="Primitive Operator">⊔</a> <a id="1196" href="order-theory.total-preorders.html#467" class="Bound">l2</a><a id="1198" class="Symbol">)</a>
  <a id="1202" href="order-theory.total-preorders.html#1167" class="Function">is-total-Preorder</a> <a id="1220" class="Symbol">=</a> <a id="1222" href="foundation-core.propositions.html#1424" class="Function">type-Prop</a> <a id="1232" href="order-theory.total-preorders.html#976" class="Function">is-total-preorder-Prop</a>

  <a id="1258" href="order-theory.total-preorders.html#1258" class="Function">is-prop-is-total-Preorder</a> <a id="1284" class="Symbol">:</a> <a id="1286" href="foundation-core.propositions.html#1246" class="Function">is-prop</a> <a id="1294" href="order-theory.total-preorders.html#1167" class="Function">is-total-Preorder</a>
  <a id="1314" href="order-theory.total-preorders.html#1258" class="Function">is-prop-is-total-Preorder</a> <a id="1340" class="Symbol">=</a> <a id="1342" href="foundation-core.propositions.html#1491" class="Function">is-prop-type-Prop</a> <a id="1360" href="order-theory.total-preorders.html#976" class="Function">is-total-preorder-Prop</a>
</pre>