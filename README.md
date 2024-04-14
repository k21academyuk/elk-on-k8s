<ol>
    <li>
        Change the Storage Class Name according to your Storage Class Name available in the K8s cluster in <code>elasticsearch.yaml</code>, and create a StatefulSet and its service:
        <pre><code>kubectl apply -f elasticsearch.yaml
kubectl apply -f elasticsearch-svc.yaml
        </code></pre>
    </li>
    <li>
        Create a ConfigMap using <code>logstash-config.yaml</code>:
        <pre><code>kubectl apply -f logstash-config.yaml
        </code></pre>
    </li>
    <li>
        Create a Logstash deployment:
        <pre><code>kubectl apply -f logstash-deployment.yaml
            kubectl apply -f logstash-svc.yaml
        </code></pre>
    </li>
    <li>
        Create a Filebeat DaemonSet Controller using <code>filebeat-agent.yaml</code>:
        <pre><code>kubectl apply -f filebeat-agent.yaml
        </code></pre>
    </li>
    <li>
        Apply <code>kibana-elk.yaml</code> to create the Kibana dashboard:
        <pre><code>kubectl apply -f kibana-elk.yaml
        </code></pre>
    </li>
</ol>

<p>Access the Kibana Dashboard using <code>&lt;publicip&gt;:32010</code>.</p>
