Kubernetes Spring Stuff
===

Ray Tsang
---

GoogleCloud Platform Developer Advocate

@saturnism
saturnism.me

spring.io/projects/spring-cloud-gcp
gcplab.me/spring

flickr.com/saturnism

[Youtube of 4 years ago](https://www.youtuble.comwatch?v=Bcs-inRnLDc)

AN: This looks like it's a bit more advanced on Kubernetes for me. 

Follow app dev best practices: Stateless, etc.

[12 Factor App](12factor.net)

Test, Test, Test
----

Local, Wiremock, Contract, Mock, TestContainers


Memory management in containers
---

Native Memory Tracking enabled in JVM, gives you cool memory stats when shut down successfully (not OOMKilled)

Docker best practices, use them.

Jib plugin for gradle & maven
  * Specify dest image
  * Specify source image
  * Don't run as root, specify nobody:nogroup when possible

Splits your code into good layers: dependencies, properites/config, app code thin jar. 

Don't write to the filesystem, especially logs.

Kubernetes
---

BAD!

```bash
$ kubectl create deployment demo-app --image=gcr.io/wise-coyote-827/jib-demo
```

Not as bad, but still bad. 
```
$ kubectl rollout
```

build your yaml files, check them in, and deploy via CI/CD

```bash
$ kubectl create deployment demo-app --image=gcr.io/wise-coyote-827/jib-demo --dry-run -oyaml
```

Skaffold
--- 
Similar to Docker-Compose for Kubernetes?
(I thought Kubernetes was basically Docker-compose for docker?)

Kubernetes has LivenessProbe (SHould I kill the app and restart?) and ReadinessProbe (Should I accept requests for processing?)
Those are *NOT* the same.  

Liveness Probe shouldn't be the actuator endpoint

```yaml
livenessProbe:
  httpGet:
    initialDelaySeconds: 60
    port: 8080
    path: /alive
readinessProbe:
  periodSecionds: ? #
  failureThreshold: ? #
  initialDelaySeconds: ? # 
  httpGet:
    port: 8080
    path: /actuator/health
```

Graceful Shutdown
1) Receive SIGTERM
2) Fail the readiness probe 
3) Receive new requests, until they stop coming in,
4) Wait for requests to finish
5) *then* die. 

ch.sbb:spring-boot-graceful-shutdown

```java
static void main(Stringp[] args) {
  GracefulShutdownSpringApplication.run(DemoApplication.class, args)
}
```

Different environments
--- 
* Helm
* Custom Templating engines (Jinja/Python)
* Kustomize

/kustomize/base/deployment.yaml, /kustomize/base/service.yaml
/kustomize/base/kustomize.yaml

/kustomize/qa/kustomization.yaml
```

```
