# Connected graphs

<pre class="Agda"><a id="29" class="Symbol">{-#</a> <a id="33" class="Keyword">OPTIONS</a> <a id="41" class="Pragma">--without-K</a> <a id="53" class="Pragma">--exact-split</a> <a id="67" class="Symbol">#-}</a>

<a id="72" class="Keyword">module</a> <a id="79" href="graph-theory.connected-undirected-graphs.html" class="Module">graph-theory.connected-undirected-graphs</a> <a id="120" class="Keyword">where</a>

<a id="127" class="Keyword">open</a> <a id="132" class="Keyword">import</a> <a id="139" href="foundation.propositional-truncations.html" class="Module">foundation.propositional-truncations</a> <a id="176" class="Keyword">using</a> <a id="182" class="Symbol">(</a><a id="183" href="foundation.propositional-truncations.html#1701" class="Postulate">type-trunc-Prop</a><a id="198" class="Symbol">;</a> <a id="200" href="foundation.propositional-truncations.html#1951" class="Function">is-prop-type-trunc-Prop</a><a id="223" class="Symbol">)</a>
<a id="225" class="Keyword">open</a> <a id="230" class="Keyword">import</a> <a id="237" href="foundation.propositions.html" class="Module">foundation.propositions</a> <a id="261" class="Keyword">using</a>
  <a id="269" class="Symbol">(</a> <a id="271" href="foundation-core.propositions.html#1246" class="Function">is-prop</a><a id="278" class="Symbol">;</a> <a id="280" href="foundation.propositions.html#1492" class="Function">is-prop-Π</a> <a id="290" class="Symbol">)</a>
<a id="292" class="Keyword">open</a> <a id="297" class="Keyword">import</a> <a id="304" href="foundation.universe-levels.html" class="Module">foundation.universe-levels</a> <a id="331" class="Keyword">using</a> <a id="337" class="Symbol">(</a><a id="338" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="343" class="Symbol">;</a> <a id="345" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a><a id="347" class="Symbol">;</a> <a id="349" href="Agda.Primitive.html#810" class="Primitive Operator">_⊔_</a><a id="352" class="Symbol">;</a> <a id="354" href="Agda.Primitive.html#780" class="Primitive">lsuc</a><a id="358" class="Symbol">;</a> <a id="360" href="Agda.Primitive.html#764" class="Primitive">lzero</a><a id="365" class="Symbol">)</a>

<a id="368" class="Keyword">open</a> <a id="373" class="Keyword">import</a> <a id="380" href="graph-theory.paths-undirected-graphs.html" class="Module">graph-theory.paths-undirected-graphs</a> <a id="417" class="Keyword">using</a>
  <a id="425" class="Symbol">(</a> <a id="427" href="graph-theory.paths-undirected-graphs.html#784" class="Datatype">path-Undirected-Graph</a><a id="448" class="Symbol">)</a>
<a id="450" class="Keyword">open</a> <a id="455" class="Keyword">import</a> <a id="462" href="graph-theory.undirected-graphs.html" class="Module">graph-theory.undirected-graphs</a> <a id="493" class="Keyword">using</a>
  <a id="501" class="Symbol">(</a> <a id="503" href="graph-theory.undirected-graphs.html#785" class="Function">Undirected-Graph</a><a id="519" class="Symbol">;</a> <a id="521" href="graph-theory.undirected-graphs.html#981" class="Function">vertex-Undirected-Graph</a><a id="544" class="Symbol">)</a>
</pre>
## Idea

A graph is said to be connected if any point can be reached from any point by a path of edges

## Definition

<pre class="Agda"><a id="678" class="Keyword">module</a> <a id="685" href="graph-theory.connected-undirected-graphs.html#685" class="Module">_</a>
  <a id="689" class="Symbol">{</a><a id="690" href="graph-theory.connected-undirected-graphs.html#690" class="Bound">l1</a> <a id="693" href="graph-theory.connected-undirected-graphs.html#693" class="Bound">l2</a> <a id="696" class="Symbol">:</a> <a id="698" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="703" class="Symbol">}</a> <a id="705" class="Symbol">(</a><a id="706" href="graph-theory.connected-undirected-graphs.html#706" class="Bound">G</a> <a id="708" class="Symbol">:</a> <a id="710" href="graph-theory.undirected-graphs.html#785" class="Function">Undirected-Graph</a> <a id="727" href="graph-theory.connected-undirected-graphs.html#690" class="Bound">l1</a> <a id="730" href="graph-theory.connected-undirected-graphs.html#693" class="Bound">l2</a><a id="732" class="Symbol">)</a>
  <a id="736" class="Keyword">where</a>

  <a id="745" href="graph-theory.connected-undirected-graphs.html#745" class="Function">is-connected-Undirected-Graph</a> <a id="775" class="Symbol">:</a> <a id="777" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="780" class="Symbol">(</a><a id="781" href="graph-theory.connected-undirected-graphs.html#690" class="Bound">l1</a> <a id="784" href="Agda.Primitive.html#810" class="Primitive Operator">⊔</a> <a id="786" href="graph-theory.connected-undirected-graphs.html#693" class="Bound">l2</a> <a id="789" href="Agda.Primitive.html#810" class="Primitive Operator">⊔</a> <a id="791" href="Agda.Primitive.html#780" class="Primitive">lsuc</a> <a id="796" href="Agda.Primitive.html#764" class="Primitive">lzero</a><a id="801" class="Symbol">)</a>
  <a id="805" href="graph-theory.connected-undirected-graphs.html#745" class="Function">is-connected-Undirected-Graph</a> <a id="835" class="Symbol">=</a>
    <a id="841" class="Symbol">(</a><a id="842" href="graph-theory.connected-undirected-graphs.html#842" class="Bound">x</a> <a id="844" href="graph-theory.connected-undirected-graphs.html#844" class="Bound">y</a> <a id="846" class="Symbol">:</a> <a id="848" href="graph-theory.undirected-graphs.html#981" class="Function">vertex-Undirected-Graph</a> <a id="872" href="graph-theory.connected-undirected-graphs.html#706" class="Bound">G</a><a id="873" class="Symbol">)</a> <a id="875" class="Symbol">→</a>
    <a id="881" href="foundation.propositional-truncations.html#1701" class="Postulate">type-trunc-Prop</a> <a id="897" class="Symbol">(</a><a id="898" href="graph-theory.paths-undirected-graphs.html#784" class="Datatype">path-Undirected-Graph</a> <a id="920" href="graph-theory.connected-undirected-graphs.html#706" class="Bound">G</a> <a id="922" href="graph-theory.connected-undirected-graphs.html#842" class="Bound">x</a> <a id="924" href="graph-theory.connected-undirected-graphs.html#844" class="Bound">y</a><a id="925" class="Symbol">)</a>
</pre>
## Properties

### The property of being connected for an undirected graph is a proposition

<pre class="Agda">  <a id="1035" href="graph-theory.connected-undirected-graphs.html#1035" class="Function">is-prop-is-connected-Undirected-Graph</a>
    <a id="1077" class="Symbol">:</a> <a id="1079" href="foundation-core.propositions.html#1246" class="Function">is-prop</a> <a id="1087" href="graph-theory.connected-undirected-graphs.html#745" class="Function">is-connected-Undirected-Graph</a>
  <a id="1119" href="graph-theory.connected-undirected-graphs.html#1035" class="Function">is-prop-is-connected-Undirected-Graph</a> <a id="1157" class="Symbol">=</a>
     <a id="1164" href="foundation.propositions.html#1492" class="Function">is-prop-Π</a> <a id="1174" class="Symbol">(λ</a> <a id="1177" href="graph-theory.connected-undirected-graphs.html#1177" class="Bound">_</a> <a id="1179" class="Symbol">→</a> <a id="1181" href="foundation.propositions.html#1492" class="Function">is-prop-Π</a> <a id="1191" class="Symbol">(λ</a> <a id="1194" href="graph-theory.connected-undirected-graphs.html#1194" class="Bound">_</a> <a id="1196" class="Symbol">→</a> <a id="1198" href="foundation.propositional-truncations.html#1951" class="Function">is-prop-type-trunc-Prop</a><a id="1221" class="Symbol">))</a>
</pre>