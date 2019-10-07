# jQ 常用Selectors

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x8A9E;&#x6CD5;</th>
      <th style="text-align:left">&#x63CF;&#x8FF0;</th>
      <th style="text-align:left">&#x7BC4;&#x4F8B;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><code>$(&quot;*&quot;)</code>
      </td>
      <td style="text-align:left">&#x6240;&#x6709;&#x7684;elements</td>
      <td style="text-align:left"><a href="https://www.w3schools.com/jquery/tryit.asp?filename=tryjquery_sel_all2">Try it</a>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>$(this)</code>
      </td>
      <td style="text-align:left">&#x73FE;&#x5728;&#x7684;HTML element</td>
      <td style="text-align:left"><a href="https://www.w3schools.com/jquery/tryit.asp?filename=tryjquery_sel_this">Try it</a>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>$(&quot;p.intro&quot;)</code>
      </td>
      <td style="text-align:left">&#x6240;&#x6709;&lt;p&gt;&#x5305;&#x542B;class=&quot;intro&quot;</td>
      <td
      style="text-align:left"><a href="https://www.w3schools.com/jquery/tryit.asp?filename=tryjquery_sel_pclass">Try it</a>
        </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>$(&quot;p:first&quot;)</code>
      </td>
      <td style="text-align:left">&#x7B2C;&#x4E00;&#x500B;&lt;p&gt;</td>
      <td style="text-align:left"><a href="https://www.w3schools.com/jquery/tryit.asp?filename=tryjquery_sel_pfirst">Try it</a>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>$(&quot;ul li:first&quot;)</code>
      </td>
      <td style="text-align:left">&#x7B2C;&#x4E00;&#x500B;&lt;ul&gt;&#x7684;&#x7B2C;&#x4E00;&#x500B;&lt;li&gt;</td>
      <td
      style="text-align:left"><a href="https://www.w3schools.com/jquery/tryit.asp?filename=tryjquery_sel_ullifirst">Try it</a>
        </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>$(&quot;ul li:last&quot;)</code>
      </td>
      <td style="text-align:left">&#x6700;&#x5F8C;&#x4E00;&#x500B;&lt;ul&gt;&#x7684;&#x6700;&#x5F8C;&#x4E00;&#x500B;&lt;li&gt;</td>
      <td
      style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><code>$(&quot;ul li:first-child&quot;)</code>
      </td>
      <td style="text-align:left">&#x6BCF;&#x4E00;&#x500B;&lt;ul&gt;&#x7684;&#x7B2C;&#x4E00;&#x500B;&lt;li&gt;</td>
      <td
      style="text-align:left"><a href="https://www.w3schools.com/jquery/tryit.asp?filename=tryjquery_sel_ullifirstchild">Try it</a>
        </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>$(&quot;[href]&quot;)</code>
      </td>
      <td style="text-align:left">&#x6240;&#x6709;&#x6709;href&#x5C6C;&#x6027;&#x7684;&#x6A19;&#x7C64;</td>
      <td
      style="text-align:left"><a href="https://www.w3schools.com/jquery/tryit.asp?filename=tryjquery_sel_hrefattr">Try it</a>
        </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>$(&quot;a[target=&apos;_blank&apos;]&quot;)</code>
      </td>
      <td style="text-align:left">&#x6240;&#x6709;&lt;a&gt;&#x4E14;&#x5C6C;&#x6027;&#x6709;target=&quot;_blank&quot;</td>
      <td
      style="text-align:left"><a href="https://www.w3schools.com/jquery/tryit.asp?filename=tryjquery_sel_hrefattrblank">Try it</a>
        </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>$(&quot;a[target!=&apos;_blank&apos;]&quot;)</code>
      </td>
      <td style="text-align:left">&#x6240;&#x6709;&lt;a&gt;&#x4E14;&#x5C6C;&#x6027;&#x6C92;&#x6709;target=&quot;_blank&quot;</td>
      <td
      style="text-align:left"><a href="https://www.w3schools.com/jquery/tryit.asp?filename=tryjquery_sel_hrefattrnotblank">Try it</a>
        </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><code>$(&quot;:button&quot;)</code>
        </p>
        <p><code>$(&quot;button&quot;)</code>
        </p>
      </td>
      <td style="text-align:left">&#x6240;&#x6709;&#x7684;&lt;button&gt;</td>
      <td style="text-align:left"><a href="https://www.w3schools.com/jquery/tryit.asp?filename=tryjquery_sel_button2">Try it</a>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>$(&quot;tr:even&quot;)</code>
      </td>
      <td style="text-align:left">&#x6240;&#x6709;&#x70BA;&#x5076;&#x6578;&#x7684;&lt;tr&gt;</td>
      <td style="text-align:left"><a href="https://www.w3schools.com/jquery/tryit.asp?filename=tryjquery_sel_even">Try it</a>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>$(&quot;tr:odd&quot;)</code>
      </td>
      <td style="text-align:left">&#x6240;&#x6709;&#x70BA;&#x5947;&#x6578;&#x7684;&lt;tr&gt;</td>
      <td style="text-align:left"><a href="https://www.w3schools.com/jquery/tryit.asp?filename=tryjquery_sel_odd">Try it</a>
      </td>
    </tr>
  </tbody>
</table>## Ref.

{% embed url="https://www.w3schools.com/jquery/jquery\_selectors.asp" %}



