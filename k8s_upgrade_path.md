---


---

<h1 id="k8s-upgrade">k8S upgrade</h1>
<h3 id="current-version">Current version:</h3>
<p>1.29.8</p>
<h2 id="related-componetes-to-consider">related componetes to consider</h2>
<ol>
<li>
<p>Calico<br>
Deployed via tigera operator</p>
</li>
<li>
<p>Api’s not v1beta or beta<br>
possible problem:</p>
<p>kubectl api-versions|grep -i alp<br>
==     <a href="http://k8s.nginx.org/v1alpha1">k8s.nginx.org/v1alpha1</a> ==<br>
==      <a href="http://monitoring.coreos.com/v1alpha1">monitoring.coreos.com/v1alpha1</a> == (Seems related to alertmanager, part of Prometheus)</p>
</li>
<li></li>
</ol>
<h2 id="k8s-versions-are">k8s versions are:</h2>
<p>Releases:<br>
<a href="https://kubernetes.io/releases/">https://kubernetes.io/releases/</a></p>
<h3 id="current-v1.35">Current v1.35</h3>
<p>EOL:<br>
<a href="https://kubernetes.io/releases/#end-of-life-releases">https://kubernetes.io/releases/#end-of-life-releases</a></p>
<h2 id="order-of-upgrade">Order of upgrade</h2>
<h3 id="calico-update-to-v3.29">1. calico update to v3.29</h3>
<p>Need to find out which tigera operator provides it.<br>
tigera-operator one of the releases:<br>
<a href="https://github.com/tigera/operator/releases/tag/v1.36.11">v1.36.11</a><br>
<a href="https://github.com/tigera/operator/releases/tag/v1.36.8">v1.36.8</a></p>
<h3 id="k8s-upgrade-to-v1.32-still-eol">2. k8s upgrade to v1.32 (still EOL)</h3>
<h3 id="calico-update-to-v3.30-pre-latest-version">3. calico update to v3.30 (pre-latest version)</h3>
<p>tigera-operator:<br>
related releases, one of :<br>
<a href="https://github.com/tigera/operator/releases/tag/v1.38.2">v1.38.2</a> - Calico version: v3.30.1<br>
<a href="https://github.com/tigera/operator/releases/tag/v1.38.5">v1.38.5</a> - Calico version: v3.30.2</p>
<p>it supports v1.31 -  v1.35</p>
<h3 id="k8s-upgrade-to-v1.35">4. k8s upgrade to v1.35</h3>
<h3 id="ideally-5.-calico-update-to-latest-v3.31">ideally 5. calico update to latest v3.31</h3>

