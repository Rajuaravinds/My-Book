# Dashboard

Input bar !

```xml
<dashboard version="1.1" theme="dark">
<label>input tab test</label>
 <row id="tabs">
    <panel>
      <html>
        <ul id="tabs" class="nav nav-tabs">
          <li class="active"> <a href="#files" class="toggle-tab" data-toggle="tab" data-elements="file_charts,files" data-token="files_tab" style="font-weight:1000;color:green;background-color:black" >Files</a> </li>
          <li> <a href="#domains" class="toggle-tab" data-toggle="tab" data-elements="domain_charts,domains" data-token="domains_tab" style="font-weight:1000;color:orange;background-color:black" >Domains</a> </li>
          <li> <a href="#urls" class="toggle-tab" data-toggle="tab" data-elements="url_charts,urls" data-token="urls_tab" style="font-weight:1000;color:pink;background-color:black" >URLs</a> </li>
          <li> <a href="#ips" class="toggle-tab" data-toggle="tab" data-elements="ip_charts,ips" data-token="ips_tab" style="font-weight:1000;color:yellow;background-color:black" >IPs</a> </li>
          <li> <a href="#iptags" class="toggle-tab" data-toggle="tab" data-elements="iptags_charts,iptags" data-token="iptags_tab" style="font-weight:1000;color:purple;background-color:black" >VPN, Tor and Proxy IPs</a> </li>
        </ul>
      </html>
    </panel>
  </row>
</dashboard>
```

<figure><img src=".gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>
