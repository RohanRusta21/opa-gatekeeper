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
2. Constraints are used to inform Gatekeeper that the admin wants a ConstraintTemplate to be enforced, and how.
