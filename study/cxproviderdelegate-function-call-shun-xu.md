# CXProviderDelegate function call 順序

[CXProviderDelegate官方文件](https://developer.apple.com/documentation/callkit/cxproviderdelegate)

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x60C5;&#x5883;</th>
      <th style="text-align:left">handle call &#x9806;&#x5E8F;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">&#x64A5;&#x6253;</td>
      <td style="text-align:left">
        <p><b><code>performStartCallAction</code></b>
        </p>
        <p>&#x2B07;&#xFE0E;</p>
        <p><code>didActivateAudioSession</code>
        </p>
        <p>&#x2B07;&#xFE0E;</p>
        <p><code>didDeactivateAudioSession (&#x5C0D;&#x65B9;&#x639B;&#x65B7;)</code>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">&#x64A5;&#x6253;</td>
      <td style="text-align:left">
        <p><b><code>performStartCallAction</code></b>
        </p>
        <p>&#x2B07;&#xFE0E;</p>
        <p><code>didActivateAudioSession</code>
        </p>
        <p>&#x2B07;&#xFE0E;</p>
        <p><code>performEndCallAction (&#x81EA;&#x5DF1;&#x639B;&#x65B7;)</code>
          <br
          />&#x2B07;&#xFE0E;</p>
        <p><code>didDeactivateAudioSession </code>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">&#x63A5;&#x807D;</td>
      <td style="text-align:left">
        <p><b><code>performAnswerCallAction</code></b>
          <br />&#x2B07;&#xFE0E;</p>
        <p><code>didActivateAudioSession</code>
        </p>
        <p>&#x2B07;&#xFE0E;</p>
        <p><code>didDeactivateAudioSession (&#x5C0D;&#x65B9;&#x639B;&#x65B7;)</code>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">&#x63A5;&#x807D;</td>
      <td style="text-align:left">
        <p><b><code>performAnswerCallAction</code></b>
        </p>
        <p>&#x2B07;&#xFE0E;</p>
        <p><code>didActivateAudioSession</code>
        </p>
        <p>&#x2B07;&#xFE0E;</p>
        <p><code>performEndCallAction (&#x81EA;&#x5DF1;&#x639B;&#x65B7;)</code>
          <br
          />&#x2B07;&#xFE0E;</p>
        <p><code>didDeactivateAudioSession</code>
        </p>
      </td>
    </tr>
  </tbody>
</table>