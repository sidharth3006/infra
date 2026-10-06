helm upgrade --install aws-load-balancer-controller eks/aws-load-balancer-controller `
  --namespace kube-system `
  --set clusterName=pharma-dev-cluster `
  --set region=us-east-1 `
  --set vpcId=vpc-0421bd7411ff81ec3`
  --set serviceAccount.create=true `
  --set serviceAccount.name=aws-load-balancer-controller `
  --set "serviceAccount.annotations.eks\.amazonaws\.com/role-arn=arn:aws:iam::312892679890:role/pharma-dev-alb-controller-role" `
  --wait --timeout 5m 


  helm upgrade --install argocd argo/argo-cd `
  --namespace argocd `
  --create-namespace `
  --wait --timeout 10m