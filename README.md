# opa-gatekeeper

### Install OPA GateKeeper

```bash
kubectl apply -f https://raw.githubusercontent.com/open-policy-agent/gatekeeper/master/deploy/gatekeeper.yaml
```

### Validate you installations

```bash
kubectl get all -n gatekeeper-system
```

### Validate gatekeeper CRDs

```bash
kubectl get crd | grep -i gatekeeper
```

Note : “constrainttemplates.templates.gatekeeper.sh” using that we can create Constraints and Constraint Templates to work with gatekeeper.

1. ConstraintTemplates define a way to validate some set of Kubernetes objects in Gatekeeper’s Kubernetes admission controller.
2. Constraints are used to inform Gatekeeper that the admin wants a ConstraintTemplate to be enforced.

### Apply/Create your constraint template

```bash
kubectl create -f ConstraintTemplate.yaml
kubectl get ConstraintTemplate
```

### Apply/Create your constraint

```bash
kubectl create -f pod-must-have-label.yaml
```

```bash 
kubectl get constraints
```

### Apply our custom application

```bash
kubectl run weather-app --image=wededo4644/weather-app:88
kubectl expose pod weather-app --type=NodePort --port=3000 --target-port=3000 --name=weather-app-service
```
