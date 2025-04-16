---


---

<hr>
<h2 id="🧠-interview-question-credit-card-filtering-system">🧠 <strong>Interview Question: Credit Card Filtering System</strong></h2>
<h3 id="part-1-data-parsing-and-structuring"><strong>Part 1: Data Parsing and Structuring</strong></h3>
<p>You’re working on a system that processes raw payment data. You receive a single string of comma-separated values, each representing a 21-digit number. The first 16 digits represent the <strong>credit card number</strong>, and the last 5 digits represent the <strong>CVC</strong>.</p>
<p><strong>Example Input:</strong></p>
<pre><code>"123456789012345612345,987654321098765498765,111122223333444455555"

</code></pre>
<p><strong>Task:</strong></p>
<ol>
<li>
<p>Parse the input string.</p>
</li>
<li>
<p>Extract the credit card number and the CVC for each entry.</p>
</li>
<li>
<p>Store the information in a suitable data structure.</p>
</li>
<li>
<p>Print each entry in the following format:</p>
</li>
</ol>
<pre><code>&lt;credit_card_number&gt; : &lt;CVC&gt;

</code></pre>
<p><strong>Note:</strong> The format and data structure you choose in this step will directly affect the next parts. Make sure it allows efficient lookups or filtering.</p>
<hr>
<h3 id="part-2-filtering-blocked-cards"><strong>Part 2: Filtering Blocked Cards</strong></h3>
<p>Now, you are given a list of blocked credit card numbers. Your task is to <strong>filter out</strong> any blocked cards from your previously stored data and print only the <strong>allowed</strong> ones.</p>
<p><strong>Example Input (Blocked Cards):</strong></p>
<pre class=" language-python"><code class="prism  language-python"><span class="token punctuation">[</span><span class="token string">"1234567890123456"</span><span class="token punctuation">,</span> <span class="token string">"1111222233334444"</span><span class="token punctuation">]</span>

</code></pre>
<p><strong>Expected Output:</strong></p>
<pre><code>&lt;credit_card_number&gt; : &lt;CVC&gt;  # for all cards NOT in the blocked list

</code></pre>
<hr>
<h3 id="part-3-masking-and-exporting"><strong>Part 3: Masking and Exporting</strong></h3>
<p>For reporting and security purposes, your company now requires you to <strong>mask</strong> the credit card numbers before printing or exporting them. Only the <strong>last 4 digits</strong> of each credit card number should be visible; the rest should be replaced with asterisks (<code>*</code>). The CVC should remain fully visible.</p>
<p>Also, you must export this masked data into a list of strings with this format:</p>
<pre><code>"************3456 : 12345"

</code></pre>
<p><strong>Expected Output (as a list):</strong></p>
<pre class=" language-python"><code class="prism  language-python"><span class="token punctuation">[</span>
  <span class="token string">"************8765 : 98765"</span><span class="token punctuation">,</span>
  <span class="token string">"************5678 : 45678"</span>
<span class="token punctuation">]</span>

</code></pre>
<p>Only include non-blocked cards in this final list.</p>
<hr>

