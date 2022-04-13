# Order theory

<pre class="Agda"><a id="25" class="Symbol">{-#</a> <a id="29" class="Keyword">OPTIONS</a> <a id="37" class="Pragma">--without-K</a> <a id="49" class="Pragma">--exact-split</a> <a id="63" class="Symbol">#-}</a>

<a id="68" class="Keyword">module</a> <a id="75" href="order-theory.html" class="Module">order-theory</a> <a id="88" class="Keyword">where</a>

<a id="95" class="Keyword">open</a> <a id="100" class="Keyword">import</a> <a id="107" href="order-theory.chains-posets.html" class="Module">order-theory.chains-posets</a> <a id="134" class="Keyword">public</a>
<a id="141" class="Keyword">open</a> <a id="146" class="Keyword">import</a> <a id="153" href="order-theory.chains-preorders.html" class="Module">order-theory.chains-preorders</a> <a id="183" class="Keyword">public</a>
<a id="190" class="Keyword">open</a> <a id="195" class="Keyword">import</a> <a id="202" href="order-theory.decidable-subposets.html" class="Module">order-theory.decidable-subposets</a> <a id="235" class="Keyword">public</a>
<a id="242" class="Keyword">open</a> <a id="247" class="Keyword">import</a> <a id="254" href="order-theory.decidable-subpreorders.html" class="Module">order-theory.decidable-subpreorders</a> <a id="290" class="Keyword">public</a>
<a id="297" class="Keyword">open</a> <a id="302" class="Keyword">import</a> <a id="309" href="order-theory.finite-posets.html" class="Module">order-theory.finite-posets</a> <a id="336" class="Keyword">public</a>
<a id="343" class="Keyword">open</a> <a id="348" class="Keyword">import</a> <a id="355" href="order-theory.finite-preorders.html" class="Module">order-theory.finite-preorders</a> <a id="385" class="Keyword">public</a>
<a id="392" class="Keyword">open</a> <a id="397" class="Keyword">import</a> <a id="404" href="order-theory.finitely-graded-posets.html" class="Module">order-theory.finitely-graded-posets</a> <a id="440" class="Keyword">public</a>
<a id="447" class="Keyword">open</a> <a id="452" class="Keyword">import</a> <a id="459" href="order-theory.greatest-lower-bounds-posets.html" class="Module">order-theory.greatest-lower-bounds-posets</a> <a id="501" class="Keyword">public</a>
<a id="508" class="Keyword">open</a> <a id="513" class="Keyword">import</a> <a id="520" href="order-theory.interval-subposets.html" class="Module">order-theory.interval-subposets</a> <a id="552" class="Keyword">public</a>
<a id="559" class="Keyword">open</a> <a id="564" class="Keyword">import</a> <a id="571" href="order-theory.largest-elements-posets.html" class="Module">order-theory.largest-elements-posets</a> <a id="608" class="Keyword">public</a>
<a id="615" class="Keyword">open</a> <a id="620" class="Keyword">import</a> <a id="627" href="order-theory.largest-elements-preorders.html" class="Module">order-theory.largest-elements-preorders</a> <a id="667" class="Keyword">public</a>
<a id="674" class="Keyword">open</a> <a id="679" class="Keyword">import</a> <a id="686" href="order-theory.least-elements-posets.html" class="Module">order-theory.least-elements-posets</a> <a id="721" class="Keyword">public</a>
<a id="728" class="Keyword">open</a> <a id="733" class="Keyword">import</a> <a id="740" href="order-theory.least-elements-preorders.html" class="Module">order-theory.least-elements-preorders</a> <a id="778" class="Keyword">public</a>
<a id="785" class="Keyword">open</a> <a id="790" class="Keyword">import</a> <a id="797" href="order-theory.locally-finite-posets.html" class="Module">order-theory.locally-finite-posets</a> <a id="832" class="Keyword">public</a>
<a id="839" class="Keyword">open</a> <a id="844" class="Keyword">import</a> <a id="851" href="order-theory.maximal-chains-posets.html" class="Module">order-theory.maximal-chains-posets</a> <a id="886" class="Keyword">public</a>
<a id="893" class="Keyword">open</a> <a id="898" class="Keyword">import</a> <a id="905" href="order-theory.maximal-chains-preorders.html" class="Module">order-theory.maximal-chains-preorders</a> <a id="943" class="Keyword">public</a>
<a id="950" class="Keyword">open</a> <a id="955" class="Keyword">import</a> <a id="962" href="order-theory.meet-semilattices.html" class="Module">order-theory.meet-semilattices</a> <a id="993" class="Keyword">public</a>
<a id="1000" class="Keyword">open</a> <a id="1005" class="Keyword">import</a> <a id="1012" href="order-theory.planar-binary-trees.html" class="Module">order-theory.planar-binary-trees</a> <a id="1045" class="Keyword">public</a>
<a id="1052" class="Keyword">open</a> <a id="1057" class="Keyword">import</a> <a id="1064" href="order-theory.posets.html" class="Module">order-theory.posets</a> <a id="1084" class="Keyword">public</a>
<a id="1091" class="Keyword">open</a> <a id="1096" class="Keyword">import</a> <a id="1103" href="order-theory.preorders.html" class="Module">order-theory.preorders</a> <a id="1126" class="Keyword">public</a>
<a id="1133" class="Keyword">open</a> <a id="1138" class="Keyword">import</a> <a id="1145" href="order-theory.subposets.html" class="Module">order-theory.subposets</a> <a id="1168" class="Keyword">public</a>
<a id="1175" class="Keyword">open</a> <a id="1180" class="Keyword">import</a> <a id="1187" href="order-theory.subpreorders.html" class="Module">order-theory.subpreorders</a> <a id="1213" class="Keyword">public</a>
<a id="1220" class="Keyword">open</a> <a id="1225" class="Keyword">import</a> <a id="1232" href="order-theory.total-posets.html" class="Module">order-theory.total-posets</a> <a id="1258" class="Keyword">public</a>
<a id="1265" class="Keyword">open</a> <a id="1270" class="Keyword">import</a> <a id="1277" href="order-theory.total-preorders.html" class="Module">order-theory.total-preorders</a> <a id="1306" class="Keyword">public</a>
</pre>