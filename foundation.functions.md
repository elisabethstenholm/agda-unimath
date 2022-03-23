# Functions

<pre class="Agda"><a id="22" class="Symbol">{-#</a> <a id="26" class="Keyword">OPTIONS</a> <a id="34" class="Pragma">--without-K</a> <a id="46" class="Pragma">--exact-split</a> <a id="60" class="Pragma">--safe</a> <a id="67" class="Symbol">#-}</a>

<a id="72" class="Keyword">module</a> <a id="79" href="foundation.functions.html" class="Module">foundation.functions</a> <a id="100" class="Keyword">where</a>

<a id="107" class="Keyword">open</a> <a id="112" class="Keyword">import</a> <a id="119" href="foundation-core.functions.html" class="Module">foundation-core.functions</a> <a id="145" class="Keyword">public</a>

<a id="153" class="Keyword">open</a> <a id="158" class="Keyword">import</a> <a id="165" href="foundation.universe-levels.html" class="Module">foundation.universe-levels</a> <a id="192" class="Keyword">using</a> <a id="198" class="Symbol">(</a><a id="199" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="204" class="Symbol">;</a> <a id="206" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a><a id="208" class="Symbol">)</a>
</pre>
## Idea

Functions are primitive in Agda. Here we construct some basic functions

### Swapping the order of two variables

<pre class="Agda"><a id="Π-swap"></a><a id="346" href="foundation.functions.html#346" class="Function">Π-swap</a> <a id="353" class="Symbol">:</a> <a id="355" class="Symbol">{</a><a id="356" href="foundation.functions.html#356" class="Bound">i</a> <a id="358" href="foundation.functions.html#358" class="Bound">j</a> <a id="360" href="foundation.functions.html#360" class="Bound">k</a> <a id="362" class="Symbol">:</a> <a id="364" href="Agda.Primitive.html#597" class="Postulate">Level</a><a id="369" class="Symbol">}</a> <a id="371" class="Symbol">{</a><a id="372" href="foundation.functions.html#372" class="Bound">A</a> <a id="374" class="Symbol">:</a> <a id="376" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="379" href="foundation.functions.html#356" class="Bound">i</a><a id="380" class="Symbol">}</a> <a id="382" class="Symbol">{</a><a id="383" href="foundation.functions.html#383" class="Bound">B</a> <a id="385" class="Symbol">:</a> <a id="387" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="390" href="foundation.functions.html#358" class="Bound">j</a><a id="391" class="Symbol">}</a> <a id="393" class="Symbol">{</a><a id="394" href="foundation.functions.html#394" class="Bound">C</a> <a id="396" class="Symbol">:</a> <a id="398" href="foundation.functions.html#372" class="Bound">A</a> <a id="400" class="Symbol">→</a> <a id="402" class="Symbol">(</a><a id="403" href="foundation.functions.html#383" class="Bound">B</a> <a id="405" class="Symbol">→</a> <a id="407" href="foundation-core.universe-levels.html#222" class="Primitive">UU</a> <a id="410" href="foundation.functions.html#360" class="Bound">k</a><a id="411" class="Symbol">)}</a> <a id="414" class="Symbol">→</a>
  <a id="418" class="Symbol">((</a><a id="420" href="foundation.functions.html#420" class="Bound">x</a> <a id="422" class="Symbol">:</a> <a id="424" href="foundation.functions.html#372" class="Bound">A</a><a id="425" class="Symbol">)</a> <a id="427" class="Symbol">(</a><a id="428" href="foundation.functions.html#428" class="Bound">y</a> <a id="430" class="Symbol">:</a> <a id="432" href="foundation.functions.html#383" class="Bound">B</a><a id="433" class="Symbol">)</a> <a id="435" class="Symbol">→</a> <a id="437" href="foundation.functions.html#394" class="Bound">C</a> <a id="439" href="foundation.functions.html#420" class="Bound">x</a> <a id="441" href="foundation.functions.html#428" class="Bound">y</a><a id="442" class="Symbol">)</a> <a id="444" class="Symbol">→</a> <a id="446" class="Symbol">((</a><a id="448" href="foundation.functions.html#448" class="Bound">y</a> <a id="450" class="Symbol">:</a> <a id="452" href="foundation.functions.html#383" class="Bound">B</a><a id="453" class="Symbol">)</a> <a id="455" class="Symbol">(</a><a id="456" href="foundation.functions.html#456" class="Bound">x</a> <a id="458" class="Symbol">:</a> <a id="460" href="foundation.functions.html#372" class="Bound">A</a><a id="461" class="Symbol">)</a> <a id="463" class="Symbol">→</a> <a id="465" href="foundation.functions.html#394" class="Bound">C</a> <a id="467" href="foundation.functions.html#456" class="Bound">x</a> <a id="469" href="foundation.functions.html#448" class="Bound">y</a><a id="470" class="Symbol">)</a>
<a id="472" href="foundation.functions.html#346" class="Function">Π-swap</a> <a id="479" href="foundation.functions.html#479" class="Bound">f</a> <a id="481" href="foundation.functions.html#481" class="Bound">y</a> <a id="483" href="foundation.functions.html#483" class="Bound">x</a> <a id="485" class="Symbol">=</a> <a id="487" href="foundation.functions.html#479" class="Bound">f</a> <a id="489" href="foundation.functions.html#483" class="Bound">x</a> <a id="491" href="foundation.functions.html#481" class="Bound">y</a>
</pre>