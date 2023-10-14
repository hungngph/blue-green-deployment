# Blue/Green Deployment on Kubernetes

## Command lines

> 1. Blue deployment
> - 1.1 <code>skaffold run -f go/services/example/blue-green-helm-deploy/skaffold.yaml -p prod-blue --tail</code>
> - 1.2 <code>kubectl apply -f go/services/example/blue-green-helm-deploy/manifest/example-virtual-service-blue-test.yaml</code>
> - 1.3 <code>curl --cookie 'test=true' --location 'https://your-domain.com/example/get'</code>
> - 1.4 <code>kubectl apply -f go/services/example/blue-green-helm-deploy/manifest/example-virtual-service-blue.yaml</code>
> - <code>kubectl delete deployments/example-prod-green -n test</code>

> 2. Green deployment
> - 2.1 <code>skaffold run -f go/services/example/blue-green-helm-deploy/skaffold.yaml -p prod-green --tail</code>
> - 2.2 <code>kubectl apply -f go/services/example/blue-green-helm-deploy/manifest/example-virtual-service-green-test.yaml</code>
> - 2.3 <code>curl --cookie 'test=true' --location 'https://your-domain.com/example/get'</code>
> - 2.4 <code>kubectl apply -f go/services/example/blue-green-helm-deploy/manifest/example-virtual-service-green.yaml</code>
> - <code>kubectl delete deployments/example-prod-blue -n test</code>
