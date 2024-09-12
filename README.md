**Install cert-manager**

<code>
  kubectl apply -f https://github.com/cert-manager/cert-manager/releases/latest/download/cert-manager.yaml 
</code>

Ref: https://cert-manager.io/docs/installation/kubectl/

**Verify cert-manager installation**

https://cert-manager.io/docs/installation/verify/ (manual verification)

**Install otel-operator**

<code>kubectl apply -f https://github.com/open-telemetry/opentelemetry-operator/releases/latest/download/opentelemetry-operator.yaml </code>
https://github.com/open-telemetry/opentelemetry-operator

**Install otel-collector as deployment**
<code> 
  curl –LO https://raw.githubusercontent.com/dt-wv/otel/main/collector/otel-collector-deployment.yml	
  vi otel-collector-deployment.yml
  kubectl apply –f otel-collector-deployment.yml  </code>
 
Ref: https://github.com/open-telemetry/opentelemetry-operator/tree/main 

**Install the instrumentation CRD (customer resource definition)**
<code> 
  kubectl apply -f https://raw.githubusercontent.com/dt-wv/otel/main/instrumentation/instrumentation.yml
</code>  
The instrumentation needs to be deployed in the namespace of the running application

**Available annotations:**

.NET: <code> instrumentation.opentelemetry.io/inject-dotnet: "true" </code>

Java: <code> instrumentation.opentelemetry.io/inject-java: "true" </code>

Node.js: <code> instrumentation.opentelemetry.io/inject-nodejs: "true" </code>

Python: <code> instrumentation.opentelemetry.io/inject-python: "true" </code>
