# Scalar multiplication on matrices

<pre class="Agda"><a id="46" class="Symbol">{-#</a> <a id="50" class="Keyword">OPTIONS</a> <a id="58" class="Pragma">--without-K</a> <a id="70" class="Pragma">--exact-split</a> <a id="84" class="Symbol">#-}</a>

<a id="89" class="Keyword">module</a> <a id="96" href="linear-algebra.scalar-multiplication-matrices.html" class="Module">linear-algebra.scalar-multiplication-matrices</a> <a id="142" class="Keyword">where</a>

<a id="149" class="Keyword">open</a> <a id="154" class="Keyword">import</a> <a id="161" href="elementary-number-theory.natural-numbers.html" class="Module">elementary-number-theory.natural-numbers</a> <a id="202" class="Keyword">using</a> <a id="208" class="Symbol">(</a><a id="209" href="elementary-number-theory.natural-numbers.html#1444" class="Datatype">ℕ</a><a id="210" class="Symbol">)</a>

<a id="213" class="Keyword">open</a> <a id="218" class="Keyword">import</a> <a id="225" href="foundation.universe-levels.html" class="Module">foundation.universe-levels</a> <a id="252" class="Keyword">using</a> <a id="258" class="Symbol">(</a><a id="259" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="264" class="Symbol">;</a> <a id="266" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a><a id="268" class="Symbol">)</a>

<a id="271" class="Keyword">open</a> <a id="276" class="Keyword">import</a> <a id="283" href="linear-algebra.matrices.html" class="Module">linear-algebra.matrices</a> <a id="307" class="Keyword">using</a> <a id="313" class="Symbol">(</a><a id="314" href="linear-algebra.matrices.html#839" class="Function">matrix</a><a id="320" class="Symbol">)</a>
<a id="322" class="Keyword">open</a> <a id="327" class="Keyword">import</a> <a id="334" href="linear-algebra.scalar-multiplication-vectors.html" class="Module">linear-algebra.scalar-multiplication-vectors</a> <a id="379" class="Keyword">using</a> <a id="385" class="Symbol">(</a><a id="386" href="linear-algebra.scalar-multiplication-vectors.html#527" class="Function">scalar-mul-vec</a><a id="400" class="Symbol">)</a>
</pre>
<pre class="Agda"><a id="scalar-mul-matrix"></a><a id="415" href="linear-algebra.scalar-multiplication-matrices.html#415" class="Function">scalar-mul-matrix</a> <a id="433" class="Symbol">:</a>
  <a id="437" class="Symbol">{</a><a id="438" href="linear-algebra.scalar-multiplication-matrices.html#438" class="Bound">l1</a> <a id="441" href="linear-algebra.scalar-multiplication-matrices.html#441" class="Bound">l2</a> <a id="444" class="Symbol">:</a> <a id="446" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="451" class="Symbol">}</a> <a id="453" class="Symbol">{</a><a id="454" href="linear-algebra.scalar-multiplication-matrices.html#454" class="Bound">B</a> <a id="456" class="Symbol">:</a> <a id="458" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="461" href="linear-algebra.scalar-multiplication-matrices.html#438" class="Bound">l1</a><a id="463" class="Symbol">}</a> <a id="465" class="Symbol">{</a><a id="466" href="linear-algebra.scalar-multiplication-matrices.html#466" class="Bound">A</a> <a id="468" class="Symbol">:</a> <a id="470" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="473" href="linear-algebra.scalar-multiplication-matrices.html#441" class="Bound">l2</a><a id="475" class="Symbol">}</a> <a id="477" class="Symbol">{</a><a id="478" href="linear-algebra.scalar-multiplication-matrices.html#478" class="Bound">m</a> <a id="480" href="linear-algebra.scalar-multiplication-matrices.html#480" class="Bound">n</a> <a id="482" class="Symbol">:</a> <a id="484" href="elementary-number-theory.natural-numbers.html#1444" class="Datatype">ℕ</a><a id="485" class="Symbol">}</a> <a id="487" class="Symbol">→</a>
  <a id="491" class="Symbol">(</a><a id="492" href="linear-algebra.scalar-multiplication-matrices.html#454" class="Bound">B</a> <a id="494" class="Symbol">→</a> <a id="496" href="linear-algebra.scalar-multiplication-matrices.html#466" class="Bound">A</a> <a id="498" class="Symbol">→</a> <a id="500" href="linear-algebra.scalar-multiplication-matrices.html#466" class="Bound">A</a><a id="501" class="Symbol">)</a> <a id="503" class="Symbol">→</a> <a id="505" href="linear-algebra.scalar-multiplication-matrices.html#454" class="Bound">B</a> <a id="507" class="Symbol">→</a> <a id="509" href="linear-algebra.matrices.html#839" class="Function">matrix</a> <a id="516" href="linear-algebra.scalar-multiplication-matrices.html#466" class="Bound">A</a> <a id="518" href="linear-algebra.scalar-multiplication-matrices.html#478" class="Bound">m</a> <a id="520" href="linear-algebra.scalar-multiplication-matrices.html#480" class="Bound">n</a> <a id="522" class="Symbol">→</a> <a id="524" href="linear-algebra.matrices.html#839" class="Function">matrix</a> <a id="531" href="linear-algebra.scalar-multiplication-matrices.html#466" class="Bound">A</a> <a id="533" href="linear-algebra.scalar-multiplication-matrices.html#478" class="Bound">m</a> <a id="535" href="linear-algebra.scalar-multiplication-matrices.html#480" class="Bound">n</a>
<a id="537" href="linear-algebra.scalar-multiplication-matrices.html#415" class="Function">scalar-mul-matrix</a> <a id="555" href="linear-algebra.scalar-multiplication-matrices.html#555" class="Bound">μ</a> <a id="557" class="Symbol">=</a> <a id="559" href="linear-algebra.scalar-multiplication-vectors.html#527" class="Function">scalar-mul-vec</a> <a id="574" class="Symbol">(</a><a id="575" href="linear-algebra.scalar-multiplication-vectors.html#527" class="Function">scalar-mul-vec</a> <a id="590" href="linear-algebra.scalar-multiplication-matrices.html#555" class="Bound">μ</a><a id="591" class="Symbol">)</a>
</pre>