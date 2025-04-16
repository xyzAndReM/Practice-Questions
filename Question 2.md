---


---

<p>Absolutely! Here’s the updated version of the interview question with a <strong>clearer intro</strong> to set the stage and a smooth transition when introducing multipliers later on.</p>
<hr>
<h2 id="🎮-interview-question-game-event-tracker">🎮 Interview Question: Game Event Tracker</h2>
<p>You’re building a tracking system for a <strong>live competitive game</strong>.</p>
<ul>
<li>
<p>Multiple <strong>players</strong> are participating.</p>
</li>
<li>
<p>Throughout the game, players will <strong>gain</strong> or <strong>lose</strong> points based on their performance.</p>
</li>
<li>
<p>Your task is to <strong>process these events</strong> in real-time, track scores, and print out relevant game updates in a clear and informative way.</p>
</li>
</ul>
<p>As the game progresses, <strong>new mechanics will be introduced</strong> (such as score multipliers and leader tracking), and your solution will need to adapt.</p>
<hr>
<h2 id="📦-input-format">📦 Input Format</h2>
<p>You will receive an array of <strong>score events</strong>, each represented as:</p>
<pre class=" language-json"><code class="prism  language-json"><span class="token punctuation">{</span>
  name<span class="token punctuation">:</span> String<span class="token punctuation">,</span>
  points<span class="token punctuation">:</span> int<span class="token punctuation">,</span>
  time<span class="token punctuation">:</span> int
<span class="token punctuation">}</span>

</code></pre>
<ul>
<li>
<p><code>name</code>: Name of the player.</p>
</li>
<li>
<p><code>points</code>: Number of points gained (positive) or lost (negative).</p>
</li>
<li>
<p><code>time</code>: Time of the event (integer).</p>
</li>
</ul>
<hr>
<h2 id="🧩-part-1-display-point-events-sorted-by-time">🧩 Part 1: Display Point Events (Sorted by Time)</h2>
<p>Print each score event in <strong>chronological order</strong>, sorted by <code>time</code>.</p>
<ul>
<li>If the player <strong>gains</strong> points:</li>
</ul>
<pre><code>&lt;time&gt; : &lt;name&gt; scored &lt;points&gt; points

</code></pre>
<ul>
<li>If the player <strong>loses</strong> points:</li>
</ul>
<pre><code>&lt;time&gt; : &lt;name&gt; lost &lt;points&gt; points

</code></pre>
<p><strong>Note:</strong> You can assume <code>points</code> is never exactly 1 or -1.</p>
<h4 id="✅-example-input">✅ Example Input:</h4>
<pre class=" language-json"><code class="prism  language-json"><span class="token punctuation">[</span>
  <span class="token punctuation">{</span> <span class="token string">"name"</span><span class="token punctuation">:</span> <span class="token string">"Alice"</span><span class="token punctuation">,</span> <span class="token string">"points"</span><span class="token punctuation">:</span> <span class="token number">10</span><span class="token punctuation">,</span> <span class="token string">"time"</span><span class="token punctuation">:</span> <span class="token number">2</span> <span class="token punctuation">}</span><span class="token punctuation">,</span>
  <span class="token punctuation">{</span> <span class="token string">"name"</span><span class="token punctuation">:</span> <span class="token string">"Bob"</span><span class="token punctuation">,</span> <span class="token string">"points"</span><span class="token punctuation">:</span> <span class="token operator">-</span><span class="token number">5</span><span class="token punctuation">,</span> <span class="token string">"time"</span><span class="token punctuation">:</span> <span class="token number">1</span> <span class="token punctuation">}</span>
<span class="token punctuation">]</span>

</code></pre>
<p><strong>Expected Output:</strong></p>
<pre><code>1 : Bob lost 5 points
2 : Alice scored 10 points

</code></pre>
<hr>
<h2 id="🧩-part-2-track-player-totals">🧩 Part 2: Track Player Totals</h2>
<p>Now let’s enhance the output by <strong>tracking and displaying each player’s total points</strong> after every event.</p>
<p>Update the printout to:</p>
<pre><code>&lt;time&gt; : &lt;name&gt; scored/lost &lt;points&gt; points. &lt;name&gt; has &lt;total_points&gt; points

</code></pre>
<h4 id="✅-updated-output">✅ Updated Output:</h4>
<pre><code>1 : Bob lost 5 points. Bob has -5 points
2 : Alice scored 10 points. Alice has 10 points

</code></pre>
<hr>
<h2 id="🧩-part-3-introducing-score-multipliers">🧩 Part 3: Introducing Score Multipliers</h2>
<p>Let’s add a new rule to the game!<br>
Players can now receive <strong>score multipliers</strong>, which change how many points they gain or lose from that point forward.</p>
<p>You will receive a <strong>second array of multiplier events</strong>:</p>
<pre class=" language-json"><code class="prism  language-json"><span class="token punctuation">{</span>
  name<span class="token punctuation">:</span> String<span class="token punctuation">,</span>
  multiplier<span class="token punctuation">:</span> int<span class="token punctuation">,</span>
  time<span class="token punctuation">:</span> int
<span class="token punctuation">}</span>

</code></pre>
<h3 id="rules">Rules:</h3>
<ul>
<li>
<p>All players <strong>start with a multiplier of 1</strong>.</p>
</li>
<li>
<p>If a multiplier changes at time <code>T</code>, the <strong>new multiplier applies starting at time <code>T+1</code></strong>.</p>
</li>
<li>
<p>Print a line when the multiplier changes:</p>
</li>
</ul>
<pre><code>&lt;time&gt; : &lt;name&gt;'s multiplier changed to &lt;multiplier&gt;

</code></pre>
<ul>
<li>From the moment a multiplier is active, the actual points applied should be:</li>
</ul>
<pre><code>points * current_multiplier

</code></pre>
<p>Update your printouts to reflect the <strong>multiplied points</strong>, and update the player’s total accordingly.</p>
<hr>
<h4 id="✅-example">✅ Example:</h4>
<h5 id="score-events">Score Events:</h5>
<pre class=" language-json"><code class="prism  language-json"><span class="token punctuation">[</span>
  <span class="token punctuation">{</span> <span class="token string">"name"</span><span class="token punctuation">:</span> <span class="token string">"Bob"</span><span class="token punctuation">,</span> <span class="token string">"points"</span><span class="token punctuation">:</span> <span class="token operator">-</span><span class="token number">5</span><span class="token punctuation">,</span> <span class="token string">"time"</span><span class="token punctuation">:</span> <span class="token number">1</span> <span class="token punctuation">}</span><span class="token punctuation">,</span>
  <span class="token punctuation">{</span> <span class="token string">"name"</span><span class="token punctuation">:</span> <span class="token string">"Alice"</span><span class="token punctuation">,</span> <span class="token string">"points"</span><span class="token punctuation">:</span> <span class="token number">10</span><span class="token punctuation">,</span> <span class="token string">"time"</span><span class="token punctuation">:</span> <span class="token number">2</span> <span class="token punctuation">}</span><span class="token punctuation">,</span>
  <span class="token punctuation">{</span> <span class="token string">"name"</span><span class="token punctuation">:</span> <span class="token string">"Alice"</span><span class="token punctuation">,</span> <span class="token string">"points"</span><span class="token punctuation">:</span> <span class="token number">10</span><span class="token punctuation">,</span> <span class="token string">"time"</span><span class="token punctuation">:</span> <span class="token number">3</span> <span class="token punctuation">}</span>
<span class="token punctuation">]</span>

</code></pre>
<h5 id="multiplier-events">Multiplier Events:</h5>
<pre class=" language-json"><code class="prism  language-json"><span class="token punctuation">[</span>
  <span class="token punctuation">{</span> <span class="token string">"name"</span><span class="token punctuation">:</span> <span class="token string">"Alice"</span><span class="token punctuation">,</span> <span class="token string">"multiplier"</span><span class="token punctuation">:</span> <span class="token number">2</span><span class="token punctuation">,</span> <span class="token string">"time"</span><span class="token punctuation">:</span> <span class="token number">2</span> <span class="token punctuation">}</span>
<span class="token punctuation">]</span>

</code></pre>
<h5 id="output">Output:</h5>
<pre><code>1 : Bob lost 5 points. Bob has -5 points
2 : Alice scored 10 points. Alice has 10 points
2 : Alice's multiplier changed to 2
3 : Alice scored 20 points. Alice has 30 points

</code></pre>
<hr>
<h2 id="🧩-part-4-tracking-the-leader">🧩 Part 4: Tracking the Leader</h2>
<p>Let’s spice it up! We now want to track who is <strong>in the lead</strong>.</p>
<h3 id="new-rules">New Rules:</h3>
<ul>
<li>Whenever a player becomes the <strong>sole leader</strong> (they have more points than anyone else), print:</li>
</ul>
<pre><code>&lt;time&gt; : &lt;name&gt; has taken the lead!

</code></pre>
<ul>
<li>From that point forward, whenever the leader is mentioned in an event, add a <code>*</code> after their name:</li>
</ul>
<pre><code>&lt;time&gt; : &lt;name&gt;* scored/lost X points. &lt;name&gt;* has Y points
&lt;time&gt; : &lt;name&gt;*'s multiplier changed to Z

</code></pre>
<ul>
<li>At the end of all events, print:</li>
</ul>
<pre><code>&lt;name&gt; is the champion!

</code></pre>
<hr>
<h4 id="✅-final-output-example">✅ Final Output Example:</h4>
<pre><code>1 : Bob lost 5 points. Bob has -5 points
2 : Alice scored 10 points. Alice has 10 points
2 : Alice's multiplier changed to 2
2 : Alice has taken the lead!
3 : Alice* scored 20 points. Alice* has 30 points
4 : Bob scored 20 points. Bob has 15 points
5 : Alice* lost 4 points. Alice* has 22 points
6 : Bob scored 5 points. Bob has 20 points
7 : Bob scored 10 points. Bob has 30 points
7 : Bob has taken the lead!
8 : Bob* scored 5 points. Bob* has 35 points
8 : Bob*'s multiplier changed to 3
...
Bob is the champion!

</code></pre>
<hr>
<p>Let me know if you’d like this wrapped into a downloadable <code>.md</code>, <code>.txt</code>, or Google Doc version — or if you want to expand this into a full coding test with function signatures and test cases!</p>

